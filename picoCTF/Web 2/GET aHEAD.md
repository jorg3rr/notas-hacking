#### Descripción

Encuentra la bandera que se sostiene en este servidor para adelantarte a la competencia. [(enlace)](http://mercury.picoctf.net:15931/)

#### Solución

El objetivo es realizar una petición HTTP **HEAD** para obtener información oculta en los encabezados de la respuesta del servidor.

#### Pasos

1. **Acceder al sitio web**
    
    - Abre el enlace proporcionado en un navegador o inspecciona su código fuente (`Ctrl + U`).
        
2. **Realizar una petición GET**
    
    - Usamos `curl` para obtener el contenido de la página:
        
        ```
        curl -X GET http://mercury.picoctf.net:15931/index.php
        ```
        
    - Se observa un sitio web con opciones de "Red" y "Blue", pero no hay ninguna pista visible sobre la bandera.
        
3. **Realizar una petición HEAD**
    
    - La bandera podría estar en los encabezados de la respuesta, así que usamos `curl -I`:
        
        ```
        curl -I http://mercury.picoctf.net:15931/index.php
        ```
        
    - La respuesta del servidor muestra los encabezados, incluyendo uno llamado `flag` con la bandera:
        
        ```
        HTTP/1.1 200 OK
        flag: picoCTF{r3j3ct_th3_du4l1ty_82880908}
        Content-type: text/html; charset=UTF-8
        ```
        

#### Resultado

La bandera encontrada es:

```
picoCTF{r3j3ct_th3_du4l1ty_82880908}
```

#### Notas adicionales

- El método **HEAD** es útil para obtener metadatos sin descargar el cuerpo de la respuesta.
    
- Si un servidor es mal configurado, puede filtrar información sensible en los encabezados.
    

#### Referencias

- [Métodos HTTP: GET vs HEAD](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD)
    
- Uso de `curl` para análisis web