#### Descripción

Descomprima este archivo y busque la bandera.

#### Solución

El objetivo es analizar y extraer la información del archivo `big-zip-files.zip` para encontrar la bandera.

##### Métodos:

1. **Inspección del archivo ZIP**
    - Para verificar el contenido sin extraerlo:
        ```
        unzip -l big-zip-files.zip
        ```
    - Esto muestra una lista de los archivos comprimidos y sus ubicaciones.
2. **Extracción del contenido**
    - Para descomprimir todo el archivo:
        ```
        unzip big-zip-files.zip -d big_zip_extracted
        ```
    - Se crea un directorio `big_zip_extracted` con los archivos extraídos.
3. **Búsqueda de la bandera**
    - Usar `grep` para buscar directamente la bandera en los archivos extraídos:
        ```
        grep -r "picoCTF" big_zip_extracted
        ```
    - Si hay muchos archivos, se pueden priorizar los archivos de texto con:
        ```
        find big_zip_extracted -type f -exec grep -H "picoCTF" {} \;
        ```

##### Resultado:
`picoCTF{picoCTF{gr3p_15_m4g1c_ef8790dc}`
#### Notas adicionales

- Si `grep` no encuentra la bandera, revisar archivos sospechosos con `strings`:
    ```
    strings archivo_sospechoso | grep picoCTF
    ```
- En caso de archivos protegidos por contraseña, intentar métodos de recuperación como `zip2john` para extraer hashes y realizar fuerza bruta con `john the ripper`.
#### Referencias

- Comando `unzip` en Linux
    
- `grep` para búsqueda de patrones
    
- `strings` para extraer texto de binarios