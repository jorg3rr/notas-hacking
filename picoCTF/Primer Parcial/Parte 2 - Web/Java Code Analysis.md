#### Descripción

BookShelf Pico, mi servicio premium de lectura de libros en línea.Creo que mi sitio web es súper seguro. ¡Te reto a que demuestres que estoy equivocado leyendo el libro 'Flag'!Estas son las credenciales para comenzar:

- Nombre de usuario: "usuario"
- Contraseña: "usuario"

El código fuente se puede descargar [aquí](https://artifacts.picoctf.net/c/480/bookshelf-pico.zip).Se puede acceder al sitio web [aquí](http://saturn.picoctf.net:59508/).

### Solución
Al descargar el código fuente nos dio el cual podíamos descomprimir para poder analizarlo.`bookshelf-pico.zip`

También se nos proporcionaron las credenciales para iniciar sesión en el sitio web, que después de iniciar sesión, se nos presentó lo siguiente:`user:user`


Parece que el sitio web está generando y utilizando tokens JWT, lo que significa que potencialmente podríamos crear nuestro propio token JWT para cambiar nuestro nivel de autorización al del rol.`Admin`

A continuación, tenemos que echar un vistazo al código fuente.`JwtService.java`

## JwtService

El código fuente de JwtService parece bastante sencillo, y rápidamente detectamos la línea 27, que es donde se está generando:`SECRET_KEY`

Esto es algo que necesitaremos saber para codificar nuestros propios tokens JWT, por lo tanto, debemos echar un vistazo al código fuente de la clase a continuación.`SecretGenerator`

En este código fuente, parece que primero intenta leer la clave de un archivo local, pero si el archivo no existe, entonces usa una cadena "aleatoria" codificada de instead.`server_secret.txt``1234`

Es probable que podamos hacer una suposición segura aquí de que no podremos acceder a este archivo y que tampoco existirá en el servidor, por lo que podemos continuar bajo la premisa de que el va a ser .`SECRET_KEY``1234`

Ahora, podemos usar esto para intentar codificar nuestro propio token JWT, pero primero debemos decodificar el que ya tenemos.

## Decodificación JWT

Podemos utilizar el sitio web [jwt.io](https://jwt.io/) para decodificar y codificar tokens JWT.

Copiando y pegando nuestro token de portador actual de la solicitud de Burp Suite que capturamos anteriormente, podemos ver la carga útil del token JWT.

![decodificación-jwt](https://brandon-t-elliott.github.io/screenshots/picoctf2023/jwt-decode.png)

## La carga útil modificada

Ya sabemos por el mensaje de error que necesitamos que el rol sea .`Admin`

Sin embargo, es probable que también tengamos que modificar los campos y, que actualmente no conocemos.`userId``email`

Un grep recursivo del código fuente de la palabra muestra un comentario dentro del cual puede ser lo suficientemente bueno...`admin``Role.java`

Inspeccionar el código fuente nos da una pista de que cuanto mayor sea el valor, mayor será el privilegio:`Role.java`

Inferiremos en función de este comentario e incrementaremos el campo a .`userId``2`

En nuestro grep recursivo, también vemos una línea, por lo que seguiremos adelante y estableceremos el campo en caso de que esto también sea necesario.`.setEmail("admin")``email``admin`

También ya sabemos desde antes que deberíamos poder usar como el archivo .`1234``SECRET_KEY`

Con toda esta información, ahora podemos codificar un nuevo token JWT usando [jwt.io](https://jwt.io/) nuevamente.

## Codificación JWT

Con nuestro nuevo token JWT, deberíamos poder reemplazar esto fácilmente inspeccionando la página y navegando a la sección, luego:`Storage``Local Storage`

Ahora solo tenemos que copiar y pegar nuestro token JWT recién creado en la sección y también reemplazarlo con nuestros nuevos detalles de carga útil.`auth-token``token-payload`

Con esto en su lugar, todo lo que queda por hacer ahora es actualizar la página y leer
### Bandera
Great job! Here’s your flag:picoCTF{w34k_jwt_n0t_g00d_7745dc02}