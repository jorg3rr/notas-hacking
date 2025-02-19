#### Descripción

Can you make sense of this file?

#### Solución

El objetivo es analizar el archivo `enc_flag`, el cual parece contener una versión codificada de la bandera.

##### Métodos:

1. **Identificación del tipo de archivo**
    
    - Se utilizó el comando `file` para identificar el tipo de contenido:
        ```
        file enc_flag
        ```
    - El resultado indicó que es un archivo de texto ASCII.
        
2. **Visualización del contenido**
    
    - Se usó `cat` para ver el contenido del archivo:
        ```
        cat enc_flag
        ```
    - Mostró una cadena larga de caracteres que parecía estar codificada en Base64.
3. **Decodificación en múltiples niveles**
    - Se aplicó `base64 -d` repetidamente para decodificar el contenido:
        ```
        cat enc_flag | base64 -d
        ```
    - Se repitió este proceso varias veces hasta obtener la bandera en texto legible:
        ```
        cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
        ```
##### Resultado:

Después de varias decodificaciones en Base64, se obtuvo la bandera:

```
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
```

#### Notas adicionales

- Se identificó que la codificación Base64 estaba anidada varias veces.
- Herramientas en línea como [CyberChef](https://gchq.github.io/CyberChef/) pueden ayudar a automatizar el proceso de decodificación.
#### Referencias

- `base64` en Linux
    
- `file` en Linux
    
- `cat` en Linux