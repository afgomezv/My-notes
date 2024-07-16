---
sidebar_position: 4
title: "Mutaciones"
---


En el siguiente ejemplo vamor subir la complejida para poder aplicar las mutaciones, campos no triviales y manejo de errores.

### Origén de datos

```javascript
const users = [
  {
    id: 1,
    name: "Catalina",
    surname: "Castaño",
    street: "Calle example 1",
    zipCode: "20010",
    city: "Madrid",
    phone: "+346003214587",
  },
  {
    id: 1,
    name: "Kathe",
    surname: "Higuita",
    street: "Calle example 2",
    zipCode: "22010",
    city: "Madrid",
    phone: "+3466003694587",
  },
];
```

### Definición de tipos

En esta sección definimos el tipo de usuario, la query y las mutaciones

```javascript
const typeDefs = `
    type User {
        id: ID!
        name: String!
        surname: String!
        street: String!
        zipCode: Int!
        city: String!
        phone: String
        address: String
    }
        type Query {
            allUsers: [User]
            userCount: Int!
            findUserByName(name:String!): User
            findUserByID(id:ID!): User
        }

        type Mutation {
            addUser(
                name: String!
                surname: String!
                street: String!
                zipCode: Int!
                city: String!
                phone: String
            ): User
        }

```

### Resolvers y Mutaciones

En resolver realizamos la construcción de los campos no triviales y la mutación en la creación del usuario con su manejo de error.

```javascript
import { GraphQLError } from "graphql";

const resolvers = {
  User: {
    address: (parent) => `${parent.street}, ${parent.zipCode}, ${parent.city}`,
  },
  Query: {
    allUsers: () => users,
    userCount: () => users.length,
    findUserByName: (parent, args) =>
      users.find((user) => user.name === args.name),
    findUserByID: (parent, args) => users.find((user) => user.id === args.id),
  },
  Mutation: {
    addUser: (parent, args) => {
      if (users.find((user) => user.name === args.name)) {
        throw new GraphQLError("The username already exists", {
          extensions: { code: "BAD_USER_INPUT" },
        });
      }
      const newUser = { ...args, id: uuid() };
      users.push(newUser);
      return newUser;
    },
  },
};
```

### Aplicado query en el servidor apollo

En la query consultamos a todos los usuarios y consultamos un usuario por su nombre.

```javascript
uery($name: String!) {
  allUsers {
    name,
    surname,
    address
  }
  findUserByName(name: $name) {
    name,
    surname
  }
}

```

```json
{
  "name": "Kathe"
}
```

En el siguiente paso es crear un usuario en Apollo server

```javascript
mutation($name: String!, $surname: String!, $street: String!, $zipCode: Int!, $city: String!) {
  addUser(name: $name, surname: $surname, street: $street, zipCode: $zipCode, city: $city) {
    id,
    name
  }
}
```

```json
{
  "name": "Danna",
  "surname": "Jaramillo",
  "street": "Car 53C #88-65",
  "zipCode": 50014,
  "city": "Bello"
}
```

Ya podemos consultar al nuevo usuario
