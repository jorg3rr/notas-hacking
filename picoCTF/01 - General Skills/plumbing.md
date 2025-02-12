#### Descripción

A veces es necesario manejar datos de proceso fuera de un archivo. ¿Puede encontrar una manera de mantener la salida de este programa y buscar la bandera?
`jupiter.challenges.picoctf.org 7480`

#### Solución

El objetivo es conectarse al servidor y buscar la bandera en la salida del programa.
##### Métodos:

- **Usar `netcat` en la terminal y redirigir la salida a un archivo:**
    `nc jupiter.challenges.picoctf.org 7480 > output.txt`

    Luego, se puede buscar la bandera en el archivo con:    
    `cat output.txt | grep picoCTF`

##### Resultado esperado

Al conectarse correctamente, la bandera aparecerá en la salida en formato:

`picoCTF{digital_plumb3r_06e9d954}`

#### Notas adicionales

- `>` redirige la salida a un archivo, mientras que `| grep` permite buscar palabras clave.
- `tee` guarda la salida y la muestra en pantalla al mismo tiempo.
- Si la conexión falla, se puede intentar de nuevo más tarde.

#### Referencias

- [Comando nc - Linux](https://linux.die.net/man/1/nc)