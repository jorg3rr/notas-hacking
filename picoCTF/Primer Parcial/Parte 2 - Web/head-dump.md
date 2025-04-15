#### Descripción

¡Bienvenidos al reto! En este desafío, explorará una aplicación web y encontrará un punto de conexión que exponga un archivo que contenga una marca oculta.La aplicación es un simple sitio web de blog donde puede leer artículos sobre varios temas, incluido un artículo sobre la documentación de la API. Su objetivo es explorar la aplicación y encontrar el punto de conexión que genera los archivos que contienen la memoria del servidor, donde se oculta una marca secreta. El sitio web está publicando [picoCTF News](http://verbal-sleep.picoctf.net:49514/).

### Solución

**Paso 1: Exploración de la aplicación web**
El desafío comienza con un simple sitio web de blog. Después de lanzar la instancia, navegué por las páginas, prestando mucha atención a los enlaces y a los puntos de conexión ocultos. Un artículo titulado [_Documentación de API_](http://verbal-sleep.picoctf.net:59989/api-docs) se destacó. Al hacer clic en él, me redirigí a **/api-docs,** que alojaba Swagger UI, una herramienta para visualizar e interactuar con las API.

**Paso 2: Identificación del punto de conexión crítico**

Swagger reveló varias rutas de API, pero el punto **de conexión /heapdump** en la sección _Diagnóstico_ me llamó la atención. La descripción insinuaba la generación de un volcado de memoria, alineado con el nombre del desafío.

**Paso 3: Ejecución del punto de conexión**

Con la función "Pruébelo" de Swagger, activé el punto de conexión **/heapdump**. Esta acción descargó un archivo **.heapsnapshot** que contiene los datos de memoria del servidor.

**Paso 4: Extracción de la bandera**

Los volcados de memoria pueden ser masivos y difíciles de manejar. En lugar de examinar manualmente gigabytes de datos, utilicé **grep** para buscar el formato de firma de la bandera y rápidamente identificó la bandera:

cat heapdump-1742808189103.heapsnapshot | grep "picoCTF"

### Bandera
picoCTF{Pat!3nt_15_Th3_K3y_439bb394}