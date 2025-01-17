Mejoras de Accesibilidad con WAI-ARIA en Elementos de Bootstrap

Elementos Mejorados

Botón

Menú desplegable (Dropdown)

Alerta

Pestañas (Tabs)

Modal


Descripción de las Mejoras

Mejoras Implementadas:

role="button": Refuerza el propósito del elemento como un botón.

aria-label="Enviar formulario": Proporciona una descripción adicional para los usuarios que dependen de tecnologías de asistencia, explicando el propósito del botón de manera más específica.

2. Menú Desplegable (Dropdown)

Mejoras Implementadas:

aria-haspopup="true": Indica que el botón abre un menú.

aria-expanded="false": Representa el estado del menú (desplegado o colapsado).

role="menu" y role="menuitem": Define explícitamente los roles de los elementos del menú para mayor claridad.

3. Alerta

Mejoras Implementadas:

aria-live="assertive": Indica que el contenido de la alerta debe ser anunciado inmediatamente por los lectores de pantalla.

aria-atomic="true": Asegura que el mensaje de alerta sea anunciado como una unidad completa.

4. Pestañas (Tabs)

Mejoras Implementadas:

aria-live="polite": Asegura que los cambios de contenido sean anunciados de manera no intrusiva por los lectores de pantalla.

5. Modal

Mejoras Implementadas:

aria-hidden="true": Indica que el modal está inicialmente oculto.

aria-labelledby y aria-describedby: Asocian el título y la descripción del modal para proporcionar contexto.
