## **Solución:**

Conexión al primer servidor "telnet tethys.picoctf.net 51785"

El banner mostrará una contraseña "My_Passw@rd_@1234"

Ahora conectémonos al segundo servidor "nc tethys.picoctf.net 65139"

Solicita la contraseña que obtuvimos anteriormente del primer servidor,

luego pregunta: "¿Cuál es la conferencia de seguridad cibernética más importante del mundo?"

y la respuesta es "DEFCON"

Entonces, "el primer hacker de la historia era conocido por hacer phreaking (hacer llamadas telefónicas gratuitas), ¿quién era?"y la respuesta es "JOHN DRAPER"

Ahora tienes un shell en el servidor.
Buscando archivos en el directorio encontré "banner" y "text"

¿Has notado el "/home/player/banner" en el código?

Mirando la pista, dice: **"¿Conoces los enlaces simbólicos?"**

Los enlaces simbólicos son esencialmente accesos directos o referencias a otros archivos o directorios. Por lo tanto, puede hacer que cualquier archivo apunte a otro archivo mediante enlaces simbólicos.

Así que vamos a hacer que el "/home/player/banner" apunte a "/root/flag.txt" pero primero tienes que eliminar el original "/home/player/banner" para hacerlo, luego haciendo el enlace simbólico al flag.txt y volviendo a conectarte al servidor de nuevo encontrarás la bandera

### Bandera
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_68ca8b23}
