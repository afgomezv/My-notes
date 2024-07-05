---
sidebar_position: 8
---

# 8. Normalizacion de una base de datos

La normalización es un proceso que se utiliza para organizar y optimizar la estructura de la base para asegurar su integridad evitar `redundancia` y por ende mejorar el rendimiento consiste en la división de las entidades en varias entidades más pequeñas y irlas relacionando mediante las llaves foráneas

- `Primera Forma Normal 1FN`: Cada atributo de una entidad debe contener un solo valor atómico es decir los valores deben de ser indivisibles no pueden ser divididos en atributos más pequeños
- `Segunda Forma Normal 2FN`: Además de cumplir con lo que te pide la primer forma normal cada atributo no dependiente funcionalmente de la llave principal debe estar en una entidad
- `Tercera Forma Normal 3FN`: Además de cumplir con las dos formas normales anteriores todas las dependencias funcionales deben ser eliminadas es decir no debe insistir dependencias funcionales transitorias
- `Cuarta Forma Normal 4FN (Boyce-Codd)`: Requiere de cada dependencia funcional sea una clave candidata única.
- `Quinta Forma Normal 5FN (Domino-Clave)` : Garantizar que no haya dependencias múltiples de conjuntos de entidades.
