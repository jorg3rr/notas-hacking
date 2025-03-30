### Descripción  
¿Puedes encontrar la bandera en este sitio web?  
Intenta encontrar la bandera aquí: [http://saturn.picoctf.net:58642/](http://saturn.picoctf.net:58642/).

---

**Proceso de resolución**

1. Accedemos al sitio web y observamos un formulario de inicio de sesión con los campos `username` y `password`.
    
2. Probamos una inyección SQL básica ingresando en `username`:
    
    ```
    admin' OR 1=1--
    ```
    
    Y dejando `password` en blanco.
    
3. Esto nos permite ingresar sin credenciales válidas debido a una consulta SQL vulnerable.
    
4. Una vez dentro, encontramos la bandera en la interfaz del sitio.
    

---

**Bandera**  
`picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_3b0fca37}`

___

**Notas adicionales**  
El reto se basa en una vulnerabilidad de inyección SQL (SQLi), permitiendo el acceso sin credenciales válidas.


---

**Referencias**

- Writeup de referencia: [GitHub - DanArmor](https://github.com/DanArmor/picoCTF-2023-writeup/blob/main/Web%20Exploitation/More%20SQLi/More-SQLi.md)