### Descripción
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `41120` to get the flag?

#### Solución

El objetivo es conectarse al servidor en el puerto especificado usando `netcat`.

##### Métodos:

- **Usar `netcat` en la terminal:**   
    `nc jupiter.challenges.picoctf.org 41120`
    Esto establecerá una conexión con el servidor y mostrará la bandera en la terminal.

##### Resultado esperado

Tras ejecutar el comando, la bandera debería aparecer en la salida de la terminal en formato:

`picoCTF{nEtCat_Mast3ry_3214be47}`

#### Notas adicionales

- `netcat` es una herramienta de red que permite establecer conexiones TCP y UDP.
- Se puede usar `nc -v` para obtener información adicional sobre la conexión.
- Si el puerto no responde, puede ser necesario intentar más tarde.
#### Referencias

- [Comando nc - Linux](https://linux.die.net/man/1/nc)