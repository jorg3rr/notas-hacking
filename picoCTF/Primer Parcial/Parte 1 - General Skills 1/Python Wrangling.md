#### Descripción

Los scripts de Python se invocan como programas en la Terminal... ¿Puede ejecutar [este script de Python](https://mercury.picoctf.net/static/1b247b1631eb377d9392bfa4871b2eb1/ende.py) con [esta contraseña](https://mercury.picoctf.net/static/1b247b1631eb377d9392bfa4871b2eb1/pw.txt) para obtener [la bandera](https://mercury.picoctf.net/static/1b247b1631eb377d9392bfa4871b2eb1/flag.txt.en)?

### Solución
Paso 1:
Primero tenemos que descargar los archivos del reto. Habrá un script de Python, un archivo de texto codificado que contiene la marca y un archivo de contraseña. Podemos bajar fácilmente estos archivos con el comando como lo hicimos en la captura de pantalla a continuación:`wget`

Paso 2:
Dado que sabemos que los dos archivos de texto son la bandera codificada y la contraseña, echemos un vistazo al script de python mediante el uso para leer su contenido.`cat`

Paso 3:
Utilice el comando para copiar el archivo "flag.txt.en" y cambiarle el nombre a "pole.txt". NOTA: se acaba de agregar para mostrar el contenido del directorio para demostrar que el archivo fue copiado y renombrado, no es necesario agregarlo.`cp``&& l`

Paso 4:
Ahora que tenemos el nombre de archivo correcto y entendemos cómo funciona el programa de Python, podemos ejecutar para volcar la bandera. Cuando el programa te pida la contraseña, sólo tienes que copiar/pegar el contenido de "pw.txt" y pulsar enter. Las teclas de acceso rápido para copiar/pegar en el terminal son: ctrl+shift+c para copiar y ctrl+shift+v para pegar.`python3 ende.py -d pole.txt`

### Bandera
picoCTF{4p0110_1n_7h3_h0us3_dbd1bea4}