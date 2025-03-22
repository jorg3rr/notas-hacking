#### Descripción

¿Puedes entrar en este portal súper seguro? (enlace)

#### Solución

El objetivo es burlar la autenticación que se realiza en el lado del cliente para obtener la bandera.

#### Pasos

1. **Acceder al sitio web**
    
    - Abrir el enlace proporcionado en el navegador.
        
2. **Inspeccionar el código fuente y analizar la función de validación**
    
    - Hacer clic derecho y seleccionar **"Ver código fuente de la página"** o presionar `Ctrl + U`.
        
    - En el código HTML, se encuentra una función JavaScript `verify()` que verifica la contraseña por fragmentos.
        
    - La contraseña esperada se encuentra divida en partes usando `split = 4`, y se organiza de la siguiente manera:
        
        - `'pico'`
            
        - `'CTF{'`
            
        - `'no_c'`
            
        - `'lien'`
            
        - `'ts_p'`
            
        - `'lz_b'`
            
        - `'706c'` (hexadecimal que se convierte a `pl`)
            
        - `'5}'`
            
    - La contraseña reconstruida es:
        
        ```
        picoCTF{no_clients_plz_b706c5}  
        ```
        
3. **Ingresar la contraseña**
    
    - Volver al portal de inicio de sesión.
        
    - Introducir la contraseña completa y hacer clic en **"verify"**.
        
    - La página mostrará la bandera.
        

#### Resultado

La bandera encontrada es:

```
picoCTF{no_clients_plz_b706c5}
```

#### Notas adicionales

- La validación en el lado del cliente es insegura porque cualquier usuario puede inspeccionar el código y extraer datos sensibles directamente.
    
- Para asegurar el proceso de autenticación, la validación debe realizarse en el servidor.
    

#### Referencias

- Validación de seguridad en el lado del servidor