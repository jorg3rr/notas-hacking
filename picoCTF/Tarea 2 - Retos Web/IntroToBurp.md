**Descripción**  
Intenta aquí encontrar la bandera:  
[http://titan.picoctf.net:55200/](http://titan.picoctf.net:55200/)

---

**Proceso de resolución**

1. Abrí la página web proporcionada en el enunciado del reto.
    
2. Observé que la página tenía un formulario de inicio de sesión.
    
3. Utilicé Burp Suite para interceptar la solicitud de inicio de sesión.
    
4. Eliminé la línea de OTP en la solicitud interceptada.
    
5. Modifiqué los parámetros de la petición para intentar saltar la autenticación.
    
6. Envié la solicitud modificada y obtuve acceso al sistema.
    
7. Localicé la bandera en la respuesta del servidor.
    

---

**Referencias**

- [Writeup en Medium](https://medium.com/@Bl4cky/picoctf-2024-web-exploitation-introtoburp-ecbcfc60272e)
    

---

**Notas adicionales**  
Burp Suite es una herramienta poderosa para pruebas de seguridad en aplicaciones web. En este caso, fue utilizada para interceptar y modificar solicitudes HTTP.

---

**Bandera**  
picoCTF{#0TP_Bypvss_SuCc3$S_b3fa4f1a}