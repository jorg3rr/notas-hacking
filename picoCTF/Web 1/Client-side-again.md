#### Descripción

¿Puedes entrar en este portal súper seguro? (enlace)

#### Solución

El objetivo es inspeccionar el código fuente de la página y encontrar la validación en el lado del cliente para descubrir la contraseña o la lógica de autenticación.

#### Pasos

1. **Acceder al sitio web**
    
    - Abre el enlace proporcionado en el navegador.
        
2. **Inspeccionar el código fuente**
    
    - Haz clic derecho y selecciona **"Ver código fuente de la página"** o presiona `Ctrl + U`.
        
    - Busca referencias a scripts de validación o mensajes ocultos en el código HTML y JavaScript.
        
3. **Desofuscar el código JavaScript**
    
    - Se encontró un script ofuscado que usa una función `_0x4b5b` para realizar la validación.
        
    - Para desofuscarlo, se usó [JSNice](http://www.jsnice.org/) y se identificó el array que contiene los fragmentos de la bandera:
        
        ```
        var _0x5a46 = ["f49bf}", "_again_e", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
        ```
        
    - Luego, en la consola del navegador, se ensamblaron las partes de la bandera ejecutando:
        
        ```
        _0x5a46[8] + _0x5a46[9] + _0x5a46[1] + _0x5a46[0]
        ```
        
4. **Obtener la bandera**
    
    - El resultado de la concatenación es:
        
        ```
        picoCTF{not_this_again_ef49bf}
        ```
        

#### Resultado

La bandera encontrada es:

```
picoCTF{not_this_again_ef49bf}
```

#### Notas adicionales

- Este reto demuestra cómo se pueden ocultar datos dentro de scripts ofuscados y cómo herramientas como JSNice pueden ayudar a revertirlos.
    
- En desafíos similares, se pueden usar otras técnicas como `console.log()` en la consola para imprimir valores o modificar variables en tiempo de ejecución.
    

#### Referencias

- [JSNice: Desofuscador de JavaScript](http://www.jsnice.org/)
    
- Validación de seguridad en el lado del cliente