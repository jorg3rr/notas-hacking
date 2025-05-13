##### Descripción

¡Mi equipo ha estado trabajando muy duro en nuevas características para nuestro programa de impresión de banderas! Me pregunto cómo trabajarán juntos.

##### Archivos proporcionados:

- `challenge.zip`: Archivo comprimido que contiene los datos del reto.

##### Solución

El objetivo es analizar el desarrollo colaborativo del código y recuperar la bandera.

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
    
3. **Explorar** `**drop-in/**` **en busca de archivos relevantes**
    
    ```
    cd challenge_extracted/drop-in/
    ls -la
    ```
    
    Se encontró un archivo `flag.py`.
    
4. **Verificar las ramas del repositorio**
    
    ```
    git branch -a
    ```
    
    Se encontraron varias ramas:
    
    ```
    feature/part-1
    feature/part-2
    feature/part-3
    main
    ```
    
5. **Explorar cada rama para reconstruir la bandera**
    
    - **Rama** `**feature/part-1**`
        
        ```
        git checkout feature/part-1
        cat flag.py
        ```
        
        Contenido del archivo:
        
        ```
        print("Printing the flag...")
        print("picoCTF{t3@mw0rk_", end='')
        ```
        
    - **Rama** `**feature/part-2**`
        
        ```
        git checkout feature/part-2
        cat flag.py
        ```
        
        Contenido del archivo:
        
        ```
        print("Printing the flag...")
        print("m@k3s_th3_dr3@m_", end='')
        ```
        
    - **Rama** `**feature/part-3**`
        
        ```
        git checkout feature/part-3
        cat flag.py
        ```
        
        Contenido del archivo:
        
        ```
        print("Printing the flag...")
        print("w0rk_2c91ca76}")
        ```
        
6. **Reconstruir la bandera**
    
    Concatenando las partes encontradas en cada rama, obtenemos:
    
    ```
    picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
    ```
##### Resultado

La bandera encontrada es:

```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
```

##### Notas adicionales

- Si la bandera no aparece en los commits, revisar los `stash` con:
    
    ```
    git stash list
    ```
    
    Y restaurarlos con:
    
    ```
    git stash apply
    ```
    
- Buscar en archivos de configuración y logs de desarrollo.
    
##### Referencias

- [Comandos avanzados de Git](https://git-scm.com/docs)