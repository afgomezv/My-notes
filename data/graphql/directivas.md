---
sidebar_position: 5
title: "Directivas y decoradores"
---

Una de las ventajas que tenemos con GraphQL es que no necesitamos mantener diferentes versiones de nuestro código ya que entre otras cosas podíamos gestionar la depreciación de diferentes elementos dentro de nuestro esquema para indicarle al usuario que nuevos campos, debe utilizar y de esta forma no necesitan generar nuevas versiones en nuestro contenido pues esto es una de esta es una de las de los ejemplos que podemos utilizar para aplicar directivas puesto que esta es una directiva en concreto que es la de **deprecate** Pero tenemos más las directivas al final no van a ser más que **decoradores**.

### deprecated

La función de la directiva @deprecated en GraphQL es indicar que un campo o valor de enumeración ya no es recomendado para su uso y que eventualmente puede ser eliminado en versiones futuras de la API. Es una forma de comunicar a los consumidores de la API que deben evitar usar dicho campo o valor y, en su lugar, utilizar una alternativa sugerida.

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
            userCount: Int! @deprecated(reason: "use userLength instead")
            userLength: Int!
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
`;
```

### include

@include(if: Boolean): Incluye el campo o fragmento solo si la condición es verdadera.

```javascript
query GetUser($includeDetails: Boolean!) {
  user(id: "1") {
    id
    name
    email @include(if: $includeDetails)
  }
}
```

### include

@skip(if: Boolean): Omite el campo o fragmento si la condición es verdadera.

```javascript
query GetUser($skipDetails: Boolean!) {
  user(id: "1") {
    id
    name
    email @skip(if: $skipDetails)
  }
}
```
