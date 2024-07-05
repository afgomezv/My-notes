---
sidebar_position: 9
---

# 9. Normalizacion de un Modelo

- Modelo desnormalizado

| Venta | Fecha | Cliente     | Correo                | Teléfono   | Dirección                 | Ciudad      | País   | Producto  | Precio    | Cantidad |
| ----- | ----- | ----------- | --------------------- | ---------- | ------------------------- | ----------- | ------ | --------- | --------- | -------- |
| 1     | 1-ene | Juan Perez  | juan.perez@gmail.com  | 5512345678 | Calle 1 No. 58-1 CP 03100 | CDMX        | México | Laptop    | 25.000,00 | 2        |
| 2     | 2-ene | Pedro Gomez | pedro.gomez@gmail.com | 3387654321 | Calle 2 No. 85-6 CP 44100 | Guadalajara | México | Celular   | 12.000,00 | 3        |
| 3     | 3-ene | Ana Silva   | ana.silva@gmail.com   | 8109128734 | Calle 3 No. 33-3 CP 64000 | Monterrey   | México | Micrófono | 2.500,00  | 1        |
| 4     | 4-ene | Ana Silva   | ana.silva@gmail.com   | 8109128734 | Calle 3 No. 33-3 CP 64000 | Monterrey   | México | Laptop    | 25.000,00 | 1        |
| 5     | 5-ene | Juan Perez  | juan.perez@gmail.com  | 5512345678 | Calle 4 45-3 03920        | CDMX        | México | Micrófono | 2.500,00  | 3        |

- Modelo en 1FN

| Venta | Fecha | Nombre | Apellido | Correo                | Teléfono   | Calle   | Número | CP    | Ciudad      | País   | Producto  | Precio    | Cantidad |
| ----- | ----- | ------ | -------- | --------------------- | ---------- | ------- | ------ | ----- | ----------- | ------ | --------- | --------- | -------- |
| 1     | 1-ene | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 | Calle 1 | 58-1   | 3100  | CDMX        | México | Laptop    | 25.000,00 | 2        |
| 2     | 2-ene | Pedro  | Gomez    | pedro.gomez@gmail.com | 3387654321 | Calle 2 | 85-6   | 44100 | Guadalajara | México | Celular   | 12.000,00 | 3        |
| 3     | 3-ene | Ana    | Silva    | ana.silva@gmail.com   | 8109128734 | Calle 3 | 33-3   | 64000 | Monterrey   | México | Micrófono | 2.500,00  | 1        |
| 4     | 4-ene | Ana    | Silva    | ana.silva@gmail.com   | 8109128734 | Calle 3 | 33-3   | 64000 | Monterrey   | México | Laptop    | 25.000,00 | 1        |
| 5     | 5-ene | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 | Calle 4 | 45-3   | 3920  | CDMX        | México | Micrófono | 2.500,00  | 3        |

- Modelo en 2FN - Parte 1

| Venta | Fecha | Cliente | Producto  | Precio    | Cantidad |
| ----- | ----- | ------- | --------- | --------- | -------- |
| 1     | 1-ene | 1       | Laptop    | 25.000,00 | 2        |
| 2     | 2-ene | 2       | Celular   | 12.000,00 | 3        |
| 3     | 3-ene | 3       | Micrófono | 2.500,00  | 1        |
| 4     | 4-ene | 3       | Laptop    | 25.000,00 | 1        |
| 5     | 5-ene | 1       | Micrófono | 2.500,00  | 3        |

| Cliente | Nombre | Apellido | Correo                | Teléfono   | Calle   | Número | CP    | Ciudad      | País   |
| ------- | ------ | -------- | --------------------- | ---------- | ------- | ------ | ----- | ----------- | ------ |
| 1       | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 | Calle 1 | 58-1   | 3100  | CDMX        | México |
| 2       | Pedro  | Gomez    | pedro.gomez@gmail.com | 3387654321 | Calle 2 | 85-6   | 44100 | Guadalajara | México |
| 3       | Ana    | Silva    | ana.silva@gmail.com   | 8109128734 | Calle 3 | 33-3   | 64000 | Monterrey   | México |
| 1       | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 | Calle 4 | 45-3   | 3920  | CDMX        | México |

- Modelo en 2FN - Parte 2

| Cliente | Fecha | Cliente | Dirección | Producto  | Precio    | Cantidad |
| ------- | ----- | ------- | --------- | --------- | --------- | -------- |
| 1       | 1-ene | 1       | 1         | Laptop    | 25.000,00 | 2        |
| 2       | 2-ene | 2       | 2         | Celular   | 12.000,00 | 3        |
| 3       | 3-ene | 3       | 3         | Micrófono | 2.500,00  | 1        |
| 4       | 4-ene | 3       | 3         | Laptop    | 25.000,00 | 1        |
| 5       | 5-ene | 1       | 4         | Micrófono | 2.500,00  | 3        |

| Cliente | Nombre | Apellido | Correo                | Teléfono   |
| ------- | ------ | -------- | --------------------- | ---------- |
| 1       | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 |
| 2       | Pedro  | Gomez    | pedro.gomez@gmail.com | 3387654321 |
| 3       | Ana    | Silva    | ana.silva@gmail.com   | 8109128734 |

| Dirección | Cliente | Calle   | Número | CP    | Ciudad      | País   |
| --------- | ------- | ------- | ------ | ----- | ----------- | ------ |
| 1         | 1       | Calle 1 | 58-1   | 3100  | CDMX        | México |
| 2         | 2       | Calle 2 | 85-6   | 44100 | Guadalajara | México |
| 3         | 3       | Calle 3 | 33-3   | 64000 | Monterrey   | México |
| 4         | 1       | Calle 4 | 45-3   | 3920  | CDMX        | México |

- Modelo en 3FN

| Venta | Fecha | Cliente | Dirección | Producto | Cantidad |
| ----- | ----- | ------- | --------- | -------- | -------- |
| 1     | 1-ene | 1       | 1         | 1        | 2        |
| 2     | 2-ene | 2       | 2         | 2        | 3        |
| 3     | 3-ene | 3       | 3         | 3        | 1        |
| 4     | 4-ene | 3       | 3         | 1        | 1        |
| 5     | 5-ene | 1       | 4         | 3        | 3        |

| Producto | Nombre    | Precio    |
| -------- | --------- | --------- |
| 1        | Laptop    | 25.000,00 |
| 2        | Celular   | 12.000,00 |
| 3        | Micrófono | 2.500,00  |

| Cliente | Nombre | Apellido | Correo                | Teléfono   |
| ------- | ------ | -------- | --------------------- | ---------- |
| 1       | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 |
| 2       | Pedro  | Gomez    | pedro.gomez@gmail.com | 3387654321 |
| 3       | Ana    | Silva    | ana.silva@gmail.com   | 8109128734 |

| Dirección | Cliente | Calle   | Número | CP    | Ciudad      | País   |
| --------- | ------- | ------- | ------ | ----- | ----------- | ------ |
| 1         | 1       | Calle 1 | 58-1   | 3100  | CDMX        | México |
| 2         | 2       | Calle 2 | 85-6   | 44100 | Guadalajara | México |
| 3         | 3       | Calle 3 | 33-3   | 64000 | Monterrey   | México |
| 4         | 1       | Calle 4 | 45-3   | 3920  | CDMX        | México |

- Modelo 4FN

| Venta | Fecha | Cliente | Dirección | Producto | Cantidad |
| ----- | ----- | ------- | --------- | -------- | -------- |
| 1     | 1-ene | 1       | 1         | 1        | 2        |
| 2     | 2-ene | 2       | 2         | 2        | 3        |
| 3     | 3-ene | 3       | 3         | 3        | 1        |
| 4     | 4-ene | 3       | 3         | 1        | 1        |
| 5     | 5-ene | 1       | 4         | 3        | 3        |

| Producto | Nombre    | Precio    |
| -------- | --------- | --------- |
| 1        | Laptop    | 25.000,00 |
| 2        | Celular   | 12.000,00 |
| 3        | Micrófono | 2.500,00  |

| Cliente | Nombre | Apellido | Correo                | Teléfono   |
| ------- | ------ | -------- | --------------------- | ---------- |
| 1       | Juan   | Perez    | juan.perez@gmail.com  | 5512345678 |
| 2       | Pedro  | Gomez    | pedro.gomez@gmail.com | 3387654321 |
| 3       | Ana    | Silva    | ana.silva@gmail.com   | 8109128734 |

| Dirección | Cliente | Calle   | Número | CP    | Ciudad      | País |
| --------- | ------- | ------- | ------ | ----- | ----------- | ---- |
| 1         | 1       | Calle 1 | 58-1   | 3100  | CDMX        | 1    |
| 2         | 2       | Calle 2 | 85-6   | 44100 | Guadalajara | 1    |
| 3         | 3       | Calle 3 | 33-3   | 64000 | Monterrey   | 1    |
| 4         | 1       | Calle 4 | 45-3   | 3920  | CDMX        | 1    |

| País | Nombre | Dominio |
| ---- | ------ | ------- |
| 1    | México | mx      |
