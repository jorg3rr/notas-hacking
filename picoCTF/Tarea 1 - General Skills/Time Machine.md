##### Descripción

¿En qué estaba trabajando por última vez? Recuerdo que escribí una nota para ayudarme a recordar...

##### Archivos proporcionados:

- `challenge.zip`: Archivo comprimido que contiene los datos del reto.

##### Solución

El objetivo es recuperar la información perdida explorando archivos o el historial de modificaciones.

##### Pasos:

1. **Extraer el contenido del archivo ZIP**
    
    ```
    unzip challenge.zip -d challenge_extracted
    ```
    
    Esto extraerá los archivos en la carpeta `challenge_extracted`.
    
2. **Verificar los archivos disponibles**
    
    ```
    ls -la challenge_extracted
    ```
    
    Se encontró un directorio llamado `drop-in/`, lo que sugiere que contiene información relevante.
    
3. **Explorar** `**drop-in/**` **en busca de archivos ocultos o sospechosos**
    
    ```
    cd challenge_extracted/drop-in/
    ls -la
    ```
    
    Se encontraron los siguientes archivos:
    
    - `.git/` (directorio de un repositorio Git)
        
    - `message.txt` (posible pista)
        
4. **Buscar la bandera dentro del repositorio Git**
    
    ```
    grep -r "picoCTF" .
    ```
    
    Se encontró la bandera en archivos dentro de `.git/`:
    
    ```
    ./.git/COMMIT_EDITMSG:picoCTF{t1m3m@ch1n3_5cde9075}
    ./.git/logs/HEAD: commit (initial): picoCTF{t1m3m@ch1n3_5cde9075}
    ./.git/logs/refs/heads/master: commit (initial): picoCTF{t1m3m@ch1n3_5cde9075}
    ```
    

##### Resultado

La bandera encontrada es:

```
picoCTF{t1m3m@ch1n3_5cde9075}
```

##### Notas adicionales

- Si `grep` no encuentra la bandera, revisar archivos manualmente con `cat` o `nano`.
    
- Buscar archivos ocultos con `ls -la`.
    
- Si el repositorio Git tiene más commits, explorar con:
    
    ```
    git log --oneline
    ```
    
    Y revisar cambios previos con:
    
    ```
    git show <commit_id>
    ```
    

##### Referencias

- [Recuperación de archivos en Git](https://git-scm.com/docs)