#### Descripción

Los archivos siempre se pueden cambiar de forma secreta. ¿Puedes encontrar la bandera? [cat.jpg](https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg)

### Solución

La tarea proporciona una imagen llamada "cat.jpg", que podemos descargar para verla un poco mejor. Después de descargarlo, podemos ejecutar los comandos para verificar que se trata de una imagen jpg. Estos son los resultados:`file, hexdump and binwak`

Por lo tanto, el archivo parece ser en realidad un archivo jpg válido. Cuando tenemos que trabajar con imágenes, siempre es buena idea abrirla y mirar sus metadatos, para buscar autores, propiedades y otros datos interesantes. Solo necesitamos abrir la imagen con un visor de imágenes (Gwenview en KDE Manjaro para mí) o un editor de imágenes como Photoshop o Gimp.

Hay algo realmente interesante aquí: el campo de licencia está lleno de una cadena interesante, que parece un poco extraña para un estándar de licencia real. Podría tratarse de una cadena que oculta algo. Dado el tipo de caracteres utilizados y la longitud de la cadena, podría tratarse de una cadena codificada en base64. Simplemente podemos comprobarlo abriendo nuestro terminal y ejecutando el comando, el cual esperará a que introduzcamos el texto. Después de insertar el texto, simplemente presionamos para salir del modo interactivo.`base64 -d``ctrl+d`

Una forma más rápida de decodificar la cadena es al texto copiado y canalizarlo a , de la siguiente manera:`echo``base64 -d`

echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 | base64 -d

Lo que nos impulsará la solución como:
picoCTF{the_m3tadata_1s_modified}

### Bandera
picoCTF{the_m3tadata_1s_modified}
