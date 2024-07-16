---
sidebar_position: 2
title: "Instalación"
---

### 1. Iniciar proyecto

```
npm init --yes
```

### 2. Instalar dependencias

- Instalar GraphQL

```
npm install graphql
```

- Instalar servidor Apollo

```
npm install @apollo-server
```

### 3. Instalar typescript

```
npm install --save-dev typescript @types/node
```

### 4. Crear archivo tsconfig.json

En esta archivo va toda la configuración de typescript del proyecto

```json
tsconfig.json
{
  "compilerOptions": {
    "rootDirs": ["src"],
    "outDir": "dist",
    "lib": ["es2020"],
    "target": "es2020",
    "module": "esnext",
    "moduleResolution": "node",
    "esModuleInterop": true,
    "types": ["node"]
  }
}
```

### 5. Configurar scripsts

Agregar la siguiente configuración al package.json

```json
"type": "module",
"scripts": {
    "compile": "tsc",
    "start": "npm run compile && node ./dist/index.js"
}

```

### 6. Instanciar servidor

```javascript
import { ApolloServer } from "@apollo/server";
import { startStandaloneServer } from "@apollo/server/standalone";

const server = new ApolloServer({
  typeDefs,
  resolvers,
});

const { url } = await startStandaloneServer(server, {
  listen: { port: 4000 },
});

console.log(`Server ready at ${url}`);
```

### 7. Crear Servidor Apollo

La configuración general del servidor

1. Origén de datos
2. Definición de tipos
3. Resolvers
4. Mutaciones
5. Subscripciones
