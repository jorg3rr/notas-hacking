#### Descripción

¿Puedes conseguir la bandera?Vaya a este [sitio web](http://saturn.picoctf.net:57208/) y vea lo que puede descubrir.

## Solución

Al abrir el sitio web, veo un portal de inicio de sesión simple. Escribí algunas cosas al azar, me dio una página fallida de inicio de sesión. Fui al modo de desarrollador y vi que el código que verifica la credencial es

```js
loggedIn = checkPassword(window.username, window.password);
```

Esta función se define en . Por lo tanto, fui a este [sitio](http://saturn.picoctf.net:55826/secure.js) y encontré el siguiente código.`checkPassword``secure.js`

```js
function checkPassword(username, password) {
  if (username === "admin" && password === "strongPassword098765") {
    return true;
  } else {
    return false;
  }
}
```

Por lo tanto, conocemos el nombre de usuario y la contraseña. Al ingresar a eso, le dará la bandera.

## Bandera

`picoCTF{j5_15_7r4n5p4r3n7_05df90c8}`