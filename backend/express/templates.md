---
sidebar_position: 4
---

# Templates

## Template Engines

Nos permite crear multiples paginas desde express y que todas comparta una mismas interfaz o pueda compartir datos, estos es basicamente una tecnologia que se agrega al backend se denomina **template engines** o motor de plantillas. se instala modulo _ejs_.

```javascript
npm i ejs
```

### settings

```javascript
app.set("view engine", "ejs");
app.set("views", path.join(__dirname, "views"));
```

### routing

```javascript
router.all("/about", (req, res) => {
  const title = "Mi pagina creada desde express 2";
  res.render("index", { title });
});
```

## Plantilla HTML (.ejs)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Pagina con EJS</title>
  </head>
  <body>
    <h1><%=title%></h1>
  </body>
</html>
```

## EJS Partials

Las plantillas nos permite tener trozos de html y poder compartirlos en toda la aplicación ejemplo el **header** y **footer**.

```html
<%- include('partials/header'); %>
<h1><%=title%></h1>
<%- include('partials/footer'); %>
```

## EJS Syntax

La sintasis ejs nos permite ejecutar logica de javascript dentro de sus plantillas

```html
<%- include('partials/header'); %>
<h1><%=title%></h1>
<% if (isActive) { %>
<p>El servidor esta activo</p>
<% } else { %>
<p>El servidor esta inactivo</p>
<% } %> <%= new Date() %>
<p>Usuarios</p>
<ul>
  <% for(let i = 0; i < users.length; i++) { %>
  <li><%=users[i].id%> <%=users[i].name%> <%=users[i].lastName%></li>
  <% } %>
</ul>
<p>Colombia</p>
<%- include('partials/footer'); %>
```
