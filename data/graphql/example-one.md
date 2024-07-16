---
sidebar_position: 3
title: "Ejemplos"
---

## Query sin argumentos

### Origén de datos

```javascript
const books = [
  {
    title: "Titulo libro 1",
    author: "Autor libro 1",
  },
  {
    title: "Titulo libro 2",
    author: "Autor libro 2",
  },
];
```

### Definición de tipos

```javascript
const typeDefs = `
    # comentarios
    type Book {
        title: String
        author: String
    }
    type Query {
        books: [Book]
    }
`;
```

### Resolvers

```javascript
const resolvers = {
  Query: {
    books: () => books,
  },
};
```

## Query con argumentos argumentos

### Origén de datos

```javascript
const books = [
  {
    id: 1,
    title: "Titulo libro 1",
    author: "Autor libro 1",
  },
  {
    id: 2,
    title: "Titulo libro 2",
    author: "Autor libro 2",
  },
];
```

### Definición de tipos

```javascript
const typeDefs = `
    # comentarios
    type Book {
        id: ID!
        title: String
        author: String
    }
    type Query {
        books: [Book]
        book(id:ID!): Book
    }
`;
```

### Resolvers

```javascript
const resolvers = {
  Query: {
    books: () => books,
    book: (parent, args) => books.find((book) => book.id === parseInt(args.id)),
  },
};
```

Este es un ejemplo muy básico, no se necesita por las mutaciones
