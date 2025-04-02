#### Descripción

Encontré una aplicación web que puede ayudar a procesar imágenes: ¡solo imágenes PNG!¡Pruébalo [aquí](http://atlas.picoctf.net:54699/)!

### Solución
Podemos cargar cualquier archivo con formato PNG, por lo que creo que esto necesitará webshell para resolver el desafío, pero una cosa que necesitamos es acceso para la carga de la página de entrada.

Conseguí esto en el archivo robots.txt de este sitio web, y se ve así

/uploads/ es la página que necesitamos! Así que comenzaré a probar con mi archivo de formato PNG aleatorio.

Y sí!, así que ahora es que necesito un webshell, este es mi propio webshell, también puedes usarlo en GitHub https://github.com/baradika/simple-webshell.

agrego "PNG" en la parte superior para omitir el sistema, también cuando lo guardas, debes agregar .png formato como webshell.png.php. y ahora súbelo y revisa la página de cargas.

hay is, podemos usar ls / para mostrar el directorio

¡¡Tantos directorios!!
Solo usaré la sintaxis de Unix para buscar .txt archivo en esos muchos directorios donde hay picoCTF como texto en él.

Como puede ver, hay muchas salidas, pero dice permiso denegado, todavía lo busco, obtuve este archivo disponible.

Copié la ruta y uso cat para mostrar al archivo
### Bandera
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_73198bd9}

