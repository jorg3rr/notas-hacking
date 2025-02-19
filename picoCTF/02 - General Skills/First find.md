##### Descripción
Descomprima este archivo y busque el archivo llamado `uber-secret.txt`.
##### Solución
El objetivo es extraer el contenido del archivo ZIP y localizar el archivo `uber-secret.txt`.
##### Pasos:

1. **Descargar y extraer el archivo ZIP**
    ```
    unzip files.zip -d first_find_extracted
    ```
    Esto extraerá los archivos en el directorio `first_find_extracted`.
2. **Buscar el archivo** `**uber-secret.txt**`
    ```
    find first_find_extracted -name "uber-secret.txt"
    ```
    Este comando buscará recursivamente dentro de la carpeta extraída.
3. **Verificar el contenido del archivo**
    
    ```
    cat first_find_extracted/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
    ```
    
    Esto mostrará el contenido del archivo, que probablemente contenga la bandera.
##### Resultado
Obtenemos la bandera `picoCTF{f1nd_15_f457_ab443fd1}`
##### Notas adicionales
- Si hay muchos archivos, el comando `grep` puede ser útil:
    ```
    grep -r "picoCTF" first_find_extracted
    ```
    Esto buscará dentro de todos los archivos del directorio extraído.
##### Referencias
- `unzip` en Linux
- `find` en Linux
- `grep` en Linux
