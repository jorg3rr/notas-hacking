#### Descripción

¿Qué tal si intentamos hacer coincidir una expresión regular?El sitio web se está ejecutando [aquí](http://saturn.picoctf.net:50789/).

### Solución
Al inspeccionar la página para verificar el formulario html, se muestra que se llama a una función send_request() al enviar.

Podemos encontrar la función implementada en la misma página hacia la parte inferior, dentro de la

Se está realizando una solicitud GET a **/flag** con la entrada del parámetro que contiene el valor que ingresamos en el formulario

Encima de este código vemos un comentario que contiene la pista para la coincidencia

Aunque no está claro al principio, el comentario muestra un patrón de expresiones regulares

El primer carácter indica el inicio de la cadena. El primer carácter de la cadena es la letra 'p'

A continuación, el punto indica una coincidencia para cualquier carácter, lo que significa que cada uno de los 5 puntos puede ser reemplazado por cualquier carácter

A continuación, el punto indica una coincidencia para cualquier carácter, lo que significa que cada uno de los 5 puntos puede ser reemplazado por cualquier carácter

El patrón de expresiones regulares final es '**!?**', ya que **?** indica que el carácter anterior puede aparecer exactamente una vez o nunca, el **!** es opcional en la cadena

Al introducir algo como **paaaaaaF** se revela la bandera

### Bandera
`picoCTF{succ3ssfully_matchtheregex_0694f25b}`
