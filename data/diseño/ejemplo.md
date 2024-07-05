---
sidebar_position: 11
---

# 11. Ejemplo Modelado datos

- Entidades, atributos y relaciones

## Maratones

#### Listado de entidades

#### Carreras **(ED)**

- carrera_id **(PK)**
- nombre
- tipo_Carrera **(FK)**
- fecha
- tiempo
- mejor_tiempo
- altitud
- lugar
- pais **(FK)**
- foto

#### Tipo de carreras **(EC)**

- tipo_carrera_id **(PK)**
- discripción
- distancia

#### Paises **(EC)**

- pais_id **(PK)**
- nombre

### Relaciones

1. Una **carrera** _pertenece_ a un **tipo de carrera** (_1 a M_)
2. Una **carrera** se _corre_ en un **país** (_1 a M_)

### Reglas del negocio

1. Crear el registro de una carrera
2. Leer el registro de una(s) carrera(s) dada una condicion en particular.
3. Leer todos los registros de la entidad carrera.
4. Actualizar los datos de una carrera dada una condicion particulas.
5. Eliminar los datos de una carrera dada una condición particular.

#### tipos_carreras

1. Crear el registro de un tipo de carrera
2. Leer el registro de un(os) tipo(s) de carrera(s) dada una condicion en particular.
3. Leer todos los registros de la entidad tipos carrera.
4. Actualizar los datos de un tipo de carrera dada una condicion particulas.
5. Eliminar los datos de un tipo de carrera dada una condición particular.

#### paises

1. Crear el registro de un país
2. Leer el registro de un(os) pais(es) dada una condición en particular.
3. Leer todos los registros de la entidad paises.
4. Actualizar los datos de un país dada una condición en particular.
5. Eliminar los datos de un páis dada una condición en particular.

### Modelo entidad relacional (E-R)

![modelo-entidad-relacion](./img/modelo-relacion-entidad.png)

### Modelo relacional de la base de datos

![modelo-relacional](./img/modelo-relacional.png)
