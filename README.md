# Rueda Libre

Proyecto de práctica de HTML, CSS y Tailwind CSS que hice en Riwi. La idea es mostrar el alquiler de bicicletas y recorridos en Medellín. **Es una demostración académica**, no una empresa con reservas reales.

## Enlaces

- Repositorio: https://github.com/Ramael-L/Rueda-Libre
- Sitio configurado en GitHub Pages: https://ramael-l.github.io/Rueda-Libre/
- Rueda Nocturna: https://ramael-l.github.io/Rueda-Libre/nocturna/

## Páginas

- `index.html`: inicio, servicios, bicicletas y rutas.
- `paginas/tarifas.html`: precios de alquiler y recorridos.
- `paginas/reservas.html`: formulario de reserva de demostración.
- `nocturna/index.html`: landing de recorridos nocturnos, planes e inscripción.
- `nocturna/componentes.html`: ejemplos de botones, tarjetas, avisos y campos.
- `nocturna/prototipo.html`: primera versión de la portada nocturna.
- `css/styles.css` e `img/`: estilos e imágenes.
- `bitacora.txt`: registro de trabajo y pruebas.

## Tecnologías

- HTML semántico para ordenar el contenido.
- CSS, Flexbox y Grid en las páginas principales.
- Tailwind CSS por CDN en Rueda Nocturna: clases para colores, espacios, tarjetas, `sm:`, `md:`, `lg:` y `dark:`.
- Bootstrap: un pequeño `badge` de práctica en la landing, no todo el diseño.
- Git y GitHub para guardar los avances.

En clase utilizamos Tailwind por CDN, como indicó el profesor. En la versión final volvimos a ese método sencillo: el HTML carga Tailwind desde un enlace y usa las clases directamente, sin archivos CSS generados. Hubo una prueba temporal con `output.css`, documentada en la bitácora. Los colores del sitio principal y de la campaña nocturna comparten la identidad verde y azul; la landing agrega amarillo para destacar las acciones. Se usan Montserrat y Open Sans.

## Rueda Nocturna

Tiene tres rutas: Luces del Centro, Miradores de la Ciudad y Luna en Las Palmas.

Planes: Individual ($55.000 por persona), Pareja ($99.000 las dos personas) y Grupo de 4 a 8 ($45.000 por persona). El plan Pareja se muestra como «Más elegido».

La inscripción pide nombre, correo, celular, ruta, plan, día, acompañantes (0 a 3), experiencia, bicicleta propia y condiciones. Los campos tienen validación nativa del navegador. Para grupos de 5 a 8 hace falta coordinar el resto por separado, ya que el formulario limita los acompañantes a tres.

**El formulario no guarda ni envía información a un servidor**: muestra un aviso cuando los campos son válidos.

## ¿Qué aprendí?

Aprendí a separar las páginas por carpetas, crear enlaces relativos y elegir etiquetas HTML apropiadas. Lo más difícil fue organizar el formulario y conseguir que los elementos se acomodaran tanto en celular como en escritorio.

Elegí Tailwind para la landing porque me facilita poner espacios, colores y columnas directamente con clases. Para el resto del sitio mantuve CSS propio, que me permite practicar los selectores y las variables. Bootstrap se usa solo como ejemplo de componente listo para utilizar.

## Cómo abrirlo

1. Descarga o clona el repositorio.
2. Abre la carpeta en Visual Studio Code.
3. Abre `index.html` con Live Server.
4. Entra en Rueda Nocturna desde el menú.

Tailwind, Bootstrap y las fuentes utilizan enlaces externos, así que se necesita conexión a internet para ver todos los estilos.

## Comprobaciones finales

Los enlaces y la estructura pueden revisarse en el código. Antes de dar la entrega por comprobada todavía hay que verificar en navegador: modo claro/oscuro, teclado, campos válidos e inválidos, 360/768/1280 px, W3C y GitHub Pages. Las capturas y los resultados del cronómetro se añadirán solo después de realizarlos.

**Autor:** Ramael Gonzalez Florez — Clan Tesla, jornada AM — Riwi 2026.

## Cómo trabajé Tailwind

Primero usé el CDN de Tailwind y escribí clases directamente en los HTML. Al publicar apareció una página sin estilos y probamos un archivo CSS generado como solución temporal. Después decidí volver al CDN porque es el método que aprendí en Riwi y puedo explicarlo mejor.

El proyecto actual **no incluye `output.css`**. Si el diseño vuelve a desaparecer, revisaré la carga del script en Network y Console de las herramientas del navegador. No se ha confirmado la causa exacta de aquella falla.

## Segunda revisión del CDN (16 de noviembre de 2026)

Después de retirar output.css, comprobamos que el diseño podía seguir sin aparecer. Se cambió el enlace del CDN de Tailwind v3 al CDN oficial de Tailwind v4 alojado en jsDelivr. Todas las clases siguen en los HTML y no hay CSS compilado. La configuración de las fuentes Montserrat y Open Sans se conserva en un bloque pequeño @theme dentro del head de cada página.

El código queda preparado para descargar Tailwind desde esa dirección, pero sigue necesitando conexión. La causa exacta del error del navegador aún no está confirmada. También hay que comprobar el zoom de Chrome con Ctrl + 0 y revisar la pestaña Network si los estilos no aparecen.

## Corrección de los colores (16 de noviembre de 2026)

Al revisar la landing publicada, los fondos azul oscuro se veían, pero algunas letras eran negras, los enlaces salían azules y la parte de las rutas aparecía blanca. La causa fue un conflicto entre el CSS de Bootstrap y Tailwind v4. Bootstrap estaba cargado sin una capa CSS y algunas reglas se imponían a las clases de Tailwind.

Dejé Bootstrap únicamente para el pequeño badge «Jueves a sábado», pero lo cargué dentro de una capa llamada `bootstrap`, antes de las utilidades de Tailwind. Así las clases de Tailwind vuelven a controlar los colores y el modo oscuro. No cambié el formulario, los planes, las rutas ni las imágenes.

El HTML sigue usando Tailwind por CDN y **no hay `output.css`**. El orden de capas se definió dentro del `head`, sin crear archivos adicionales. Falta revisar la versión pública completa en Chrome, con los dos modos de color y las comprobaciones de accesibilidad.
