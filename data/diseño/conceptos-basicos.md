---
sidebar_position: 1
---

# 1. Conceptos Básicos

- **Dato:** Es la miníma unidad de información
- **Información:** son datos dentro de un contexto
- **Base de datos:** Es una colección de información
- **Sistema Gestión Base de datos:** Es un software que encapsula una base de datos

- **Tipos de bases de datos.**

  **Relacionales (SQL):**
  Se caracterizan por ser una colección ordenada de registros que se van a organizar en un conjunto de tablas una tabla es el elemento principal de una base de datos relacional y una tabla es muy parecida a una hoja de cálculo es decir los registros de información Se van a organizar en filas y columnas estas tablas se van a relacionar entre sí Y para acceder a los datos usamos el lenguaje de consulta estructurada mejor conocido por sus siglas en inglés SQL (Structure Query Language).

  **No Relacionales (NoSQL):**
  están diseñadas para modelar datos con estructuras un poco más específicas y que no necesitan ser relacionado unos datos con otros A diferencia de las relacionales cada entidad va a funcionar de forma independiente y son mucho más sencillas que las relacionales y esta sencillez de acceso y ordenación. Porque el objetivo de estas bases no relacionales lo que buscan es mejorar el rendimiento.

  **¿Cuando usar SQL o NoSQl?**

  - Cuándo vamos a utilizar SQL o bases de datos relacionales cuando necesitemos `relaciones estructuradas` es decir si tu aplicación depende de relaciones estructuradas y complejas entre tus datos es posible que consideremos este tipo de base de datos ya que nos van a permitir modelar relaciones complejas entre las tablas y utilizar en este caso el lenguaje de consulta estructurada SQL para ejecutar dichas consultas no también cuando requerimos datos estructurados es decir cuando recuerden sus datos van a tener todos la misma estructura y esta estructura va a estar bien definida y es poco probable que cambie con frecuencia.
  - Cuando un aspecto importante sea la `escalabilidad` es decir si tu aplicación está destinada a crecer rápidamente y manejar una gran cantidad de datos es posible que debas considerar este tipo de base de datos ya que son más escalables que las SQL y se adaptan mejor a grandes cantidades de datos no estructurados.
