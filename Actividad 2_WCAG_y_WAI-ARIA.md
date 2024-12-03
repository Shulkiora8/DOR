# Ejercicios de Mejora de Accesibilidad Web

## Ejercicio 1: Imagen sin texto alternativo

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <title>Galería de Fotos</title>
</head>
<body>
  <h1>Galería de Fotos</h1>
  <img src="playa.jpg" alt="Playa tropical con arena y mar">
  <img src="montana.jpg" alt="Montaña nevada al atardecer">
</body>
</html>
```

Comentario:
Se añadió el atributo alt para describir las imágenes, mejorando la accesibilidad para usuarios de lectores de pantalla.

## Ejercicio 2: Formulario sin etiquetas y mensajes de error
```
<form>
  <div>
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" placeholder="Nombre" required>
    <span id="nombreError" style="color:red;"></span>
  </div>
  <div>
    <label for="correo">Correo electrónico:</label>
    <input type="email" id="correo" placeholder="Correo electrónico" required>
    <span id="correoError" style="color:red;"></span>
  </div>
  <button>Enviar</button>
</form>

<script>
  document.querySelector('form').addEventListener('submit', function(event) {
    let valid = true;
    if (!document.getElementById('nombre').value) {
      document.getElementById('nombreError').textContent = "El nombre es obligatorio.";
      valid = false;
    }
    if (!document.getElementById('correo').value) {
      document.getElementById('correoError').textContent = "El correo es obligatorio.";
      valid = false;
    }
    if (!valid) event.preventDefault();
  });
</script>
```

Comentario:
Se añadieron etiquetas <label> para asociar los campos con su descripción y mejorar la accesibilidad.
También se incluyó una validación de formulario con mensajes de error.

## Ejercicio 3: Botón que no es accesible para lectores de pantalla

Modificación: Usar un <button> en lugar de un div y añadir un aria-label para describir la acción.
```
<button onclick="alert('¡Botón presionado!')" aria-label="Presionar botón">Presionar</button>
```
Comentario:
Se reemplazó el <div> por un <button> para mejorar la accesibilidad.
También se añadió un atributo aria-label para describir la acción del botón a los lectores de pantalla.

## Ejercicio 4: Navegación sin estructura semántica
Modificación: Usar etiquetas semánticas como nav y ul para la lista de navegación.
```
<nav>
  <ul>
    <li><a href="#">Inicio</a></li>
    <li><a href="#">Servicios</a></li>
    <li><a href="#">Contacto</a></li>
  </ul>
</nav>
```
Comentario:
Se añadió una estructura semántica usando <nav> para la navegación y <ul> para las listas.

## Ejercicio 5: Tabla sin encabezados

Modificación: Añadir etiquetas <th> para los encabezados de la tabla.
```
<table>
  <thead>
    <tr>
      <th>Producto</th>
      <th>Precio</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Producto 1</td>
      <td>10 USD</td>
    </tr>
    <tr>
      <td>Producto 2</td>
      <td>20 USD</td>
    </tr>
  </tbody>
</table>
```
Comentario:
Se añadieron etiquetas <th> para los encabezados de la tabla, mejorando la accesibilidad y la comprensión de los datos.

## Ejercicio 6: Contenido dinámico sin notificación

Modificación: Añadir un aria-live para notificar cambios dinámicos.
```
<div id="notificacion" aria-live="polite"></div>
```
Comentario:
Se añadió el atributo aria-live="polite" para notificar el cambio dinámico a los lectores de pantalla sin interrumpir otras interacciones.

## Ejercicio 7: Contraste bajo

Modificación: Cambiar los colores para un mejor contraste.
```
<style>
  body {
    background-color: #ffffff;
    color: #000000;
  }
</style>
```
Comentario:
Se mejoró el contraste del texto con el fondo cambiando los colores a blanco y negro.

## Ejercicio 8: Lista desplegable sin indicar su estado

Modificación: Añadir atributos aria-expanded y aria-controls para indicar el estado del menú.
```
<div class="menu" aria-haspopup="true" aria-expanded="false">
  Opciones
  <div class="submenu" aria-hidden="true">
    <p>Opción 1</p>
    <p>Opción 2</p>
  </div>
</div>

<script>
  document.querySelector('.menu').addEventListener('click', function() {
    const submenu = document.querySelector('.submenu');
    const isExpanded = submenu.style.display === 'block';
    submenu.style.display = isExpanded ? 'none' : 'block';
    this.setAttribute('aria-expanded', !isExpanded);
    submenu.setAttribute('aria-hidden', isExpanded);
  });
</script>
```
Comentario:
Se añadió el atributo aria-expanded para indicar si el menú está desplegado y aria-hidden para los elementos ocultos.

## Ejercicio 9: Página con contenido multimedia

Modificación: Añadir subtítulos y un texto alternativo en el video.
```
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="subtitulos_en.vtt" kind="subtitles" srclang="en" label="Inglés">
  Tu navegador no soporta el elemento de video.
</video>
```
Comentario:
Se añadió una pista de subtítulos para mejorar la accesibilidad del contenido multimedia.

## Ejercicio 10: Página dinámica sin accesibilidad

Modificación: Añadir aria-live a la notificación.
```
<div id="mensaje" aria-live="assertive"></div>
```
Comentario:
Se añadió el atributo aria-live="assertive" para notificar el mensaje dinámicamente.

## Ejercicio 11: Página web de un producto

Modificación: Añadir un aria-label al botón.
```
<button class="boton" onclick="alert('Producto añadido al carrito')" aria-label="Añadir al carrito">Añadir al carrito</button>
```
Comentario:
Se añadió el atributo aria-label al botón para describir mejor la acción a los usuarios de lectores de pantalla.

## Ejercicio 12: Blog con múltiples secciones

Modificación: Añadir una estructura semántica con <article> y <section>.
```
<article>
  <h2>Artículo Reciente</h2>
  <p>Este es el contenido del artículo...</p>
</article>
<article>
  <h2>Otro Artículo</h2>
  <p>Contenido del segundo artículo...</p>
</article>
```
Comentario:
Se reorganizó el contenido en artículos utilizando <article> para una mejor organización semántica.

## Ejercicio 13: Formulario de inscripción

Modificación: Añadir label para los campos.
```
<form>
  <div>
    <label for="nombre">Nombre completo:</label>
    <input type="text" id="nombre" placeholder="Nombre completo">
  </div>
  <div>
    <label for="correo">Correo electrónico:</label>
    <input type="email" id="correo" placeholder="Correo electrónico">
  </div>
  <div>
    <label for="pais">Seleccionar país:</label>
    <select id="pais">
      <option>México</option>
      <option>España</option>
      <option>Colombia</option>
    </select>
  </div>
  <button>Enviar</button>
</form>
```
Comentario:
Se añadieron etiquetas <label> para asociar los campos del formulario con su descripción.

## Ejercicio 14: Tabla de datos compleja

Modificación: Añadir encabezados de tabla <th> y una descripción para la tabla con caption.
```
<table border="1">
  <caption>Reporte Mensual de Ventas</caption>
  <thead>
    <tr>
      <th>Producto</th>
      <th>Enero</th>
      <th>Febrero</th>
      <th>Marzo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Zapatos</td>
      <td>100</td>
      <td>150</td>
      <td>200</td>
    </tr>
    <tr>
      <td>Camisas</td>
      <td>200</td>
      <td>250</td>
      <td>300</td>
    </tr>
  </tbody>
</table>
```
Comentario:
Se añadió un <caption> para describir el contenido de la tabla y se incorporaron encabezados <th>.

## Ejercicio 15: Menú interactivo

Modificación: Añadir un aria-expanded para indicar si el submenú está visible.
```
<div class="menu" aria-haspopup="true" aria-expanded="false">
  Opciones
  <div class="submenu" aria-hidden="true">
    <p>Opción 1</p>
    <p>Opción 2</p>
    <p>Opción 3</p>
  </div>
</div>

<script>
  document.querySelector('.menu').addEventListener('click', function() {
    const submenu = document.querySelector('.submenu');
    const isExpanded = submenu.style.display === 'block';
    submenu.style.display = isExpanded ? 'none' : 'block';
    this.setAttribute('aria-expanded', !isExpanded);
    submenu.setAttribute('aria-hidden', isExpanded);
  });
</script>
```
Comentario:
Se añadió el atributo aria-expanded para indicar si el submenú está visible.
