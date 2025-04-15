#### Descripción

Cookie Monster ha escondido su receta de galletas ultrasecreta en algún lugar de su sitio web. Como aspirante a detective de galletas, tu misión es descubrir este delicioso secreto. ¿Puedes ser más astuto que Cookie Monster y encontrar la receta oculta?Puedes acceder al Monstruo de las Galletas [aquí](http://verbal-sleep.picoctf.net:57968/) y ¡buena suerte

### Solución
Proporcione cualquier término aleatorio, es decir, **test**:**test**, como credenciales y haga clic en el botón **Iniciar sesión**. Mostrará el mensaje **de acceso denegado** con una sugerencia como '**_Sugerencia: ¿Ha revisado sus cookies últimamente?'_**  
Según la sugerencia dada, abra la pestaña **Cookies** en el navegador y observe que se ha generado una cookie con el nombre '**_secret_recipe_**' incluso para el intento de inicio de sesión fallido.

Copie el valor de la cookie y lo pegue en el **Decodificador de Burp**.  
Utilice **_Decode as URL > Decode as Base64_** para obtener el valor **Flag**.

### Bandera
picoCTF{c00k1e_m0nster_l0ves_c00kies_6E81FC1E}