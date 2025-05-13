##### Descripción

Accidentalmente anoté la bandera. ¡Menos mal que lo borré!

##### Archivos proporcionados:

- `challenge.zip`: Archivo comprimido que contiene los datos del reto.

##### Solución

El objetivo es recuperar la bandera explorando el historial de cambios en los archivos.

##### Pasos:

1. **Extraer el contenido del archivo ZIP**
    
    ```
    unzip challenge.zip -d challenge_extracted
    ```
    
    Esto extraerá los archivos en la carpeta `challenge_extracted`.
    
2. **Verificar si hay un repositorio de Git**
    
    Entrar en la carpeta extraída:
    
    ```
    cd challenge_extracted
    ```
    
    Luego, listar archivos ocultos:
    
    ```
    ls -la
    ```
    
    Se encontró un repositorio Git dentro del directorio `drop-in/`.
    
3. **Explorar el historial de cambios**
    
    Acceder al directorio `drop-in/` y verificar el estado del repositorio:
    
    ```
    cd drop-in/
    git status
    ```
    
    Luego, revisar los commits anteriores:
    
    ```
    git log --oneline
    ```
    
    Se encontraron los siguientes commits:
    
    ```
    8dc5180 (HEAD -> master) remove sensitive info
    87b85d7 create flag
    ```
    
4. **Buscar la bandera en el historial de Git**
    
    Se utilizó el siguiente comando para buscar menciones a `picoCTF` en los commits:
    
    ```
    git log -p | grep "picoCTF"
    ```
    
    Se encontró la bandera:
    
    ```
    picoCTF{s@n1t1z3_ea83ff2a}
    ```
    
5. **Recuperar la versión anterior del archivo**
    
    Para restaurar la versión anterior de `message.txt`, se utilizó:
    
    ```
    git checkout HEAD~1 message.txt
    ```
    
    Luego, al revisar su contenido con `cat`, se confirmó la bandera.
    

##### Resultado

La bandera encontrada es:

```
picoCTF{s@n1t1z3_ea83ff2a}
```

##### Notas adicionales

- Si `git` no está instalado, se puede analizar manualmente los archivos dentro de `.git/`.
    
- También se puede revisar archivos ocultos con `ls -la`.
    
- Si la bandera no está en Git, buscar en `strings` o en `grep`:
    
    ```
    grep -r "picoCTF" challenge_extracted
    ```
    
##### Referencias

- [Comandos básicos de Git](https://git-scm.com/docs)