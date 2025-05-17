#### Descripción

El teclado de un solo uso puede ser criptográficamente seguro, pero no cuando se conoce la clave. ¿Puedes resolver esto? Le hemos proporcionado la marca cifrada, la clave y una tabla para ayudar con la clave de . ¿Puedes usar esta [tabla](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) para resolverlo?. `UFJKXQZQUNB``SOLVECRYPTO`


### Solución:

Este es un [cifrado clásico de Vigenère](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher). Es fácilmente solucionable usando cualquier decodificador en línea, como [Cyberchef](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode\('SOLVECRYPTO'\)&input=VUZKS1hRWlFVTkI).

Para decodificar el mensaje manualmente, utilizamos el siguiente algoritmo:
- Para cada letra de la clave:
    - Encuentre la fila correspondiente a la letra
    - En la fila, busque la columna que contiene la letra de texto cifrado correspondiente
    - La letra de texto sin formato correspondiente se anota en la parte superior de la columna

En nuestro caso, el texto plano es .`CRYPTOISFUN`

### Bandera
picoCTF{CRYPTOISFUN}
