#### Descripción

Este sitio web solo puede ser renderizado por picobrowser, ¡vaya y atrape la bandera! (enlace)

#### Archivos proporcionados

- Ningún archivo proporcionado.
    

#### Solución

El objetivo es modificar el **User-Agent** del navegador para hacer que el servidor reconozca nuestra solicitud como si proviniera de "picobrowser".

#### Pasos

1. **Acceder al sitio web**
    
    - Abre el enlace proporcionado en Microsoft Edge o cualquier otro navegador.
        
2. **Abrir las herramientas de desarrollo**
    
    - Presiona `F12` o `Ctrl + Shift + I` para abrir las herramientas de desarrollo.
        
3. **Ir a la pestaña "Network conditions"**
    
    - Dentro de las herramientas de desarrollo, haz clic en `Más herramientas` > `Network conditions`.
        
    - Desmarca la opción **"Use browser default"** en "User-Agent".
        
    - Escribe **"picobrowser"** en el campo de User-Agent.
        
4. **Recargar la página**
    
    - Presiona `Ctrl + R` para volver a cargar la página con el nuevo User-Agent.
        
    - El servidor ahora debería aceptar la solicitud y mostrar la bandera.
        

#### Resultado

La bandera encontrada es:

```
picoCTF{user_ag3nt_m4n1pul4t10n}
```

#### Notas adicionales

- Si las herramientas de desarrollo están bloqueadas, puedes usar una extensión de User-Agent Switcher o realizar la petición con `cURL`:
    
    ```
    curl -A "picobrowser" http://jupiter.challenges.picoctf.org:28921
    ```
    
- Este tipo de reto demuestra la importancia de la validación en el servidor, ya que modificar el User-Agent en el lado del cliente es trivial.
    

#### Referencias

- [Cómo cambiar el User-Agent en Edge](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/network/)
    
- [User-Agent Switcher para Edge](https://microsoftedge.microsoft.com/addons/detail/epic-user-agent-switcher/kbhkedhlddbnmcohboeepncebmfnnnjf)