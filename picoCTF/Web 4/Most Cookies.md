#### Descripción

Muy bien, basta de usar mi propio cifrado. ¡Las cookies de sesión de matraz deberían ser bastante seguras! [server.py](https://mercury.picoctf.net/static/1e4bd835ad3e7fe776d49e7b8cc280c1/server.py) [http://mercury.picoctf.net:35697/](http://mercury.picoctf.net:35697/)
### Solucion
Encontre la herramienta flask-unsign que podría usar para decodificar la cookie. Envié "snickerdoodle" en el campo de entrada, fui al inspector y obtuve la cookie de sesión.

En mi máquina virtual de Linux, usé flask-unsign para decodificar la cookie y la fuerza bruta de la clave secreta con una lista de palabras que creé basada en el código fuente. Para mí, el secreto era la 'fortuna'. Cambié el valor "very_auth" a "admin" y agregué la clave secreta para firmar una nueva clave.

Con la página web aún cargada, cambié la cookie en el inspector y actualicé la página para recibir la bandera.

### Bandera
picoCTF{pwn_4ll_th3_cook1E5_22fe0842}