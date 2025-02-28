#### Description

Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/158/challenge.zip)

*Solución*

1. *Explorar el contenido del repositorio*
    
    - Nos movemos al directorio drop-in/:
        cd Downloads/challenge_extracted/drop-in/
        
    - Listamos los archivos disponibles:
        ls
        message.py
        
2. *Revisar el historial de Git*
    
    - Ejecutamos el siguiente comando para ver los commits anteriores:
        git log
        
    - Se muestran múltiples commits con el mensaje *"important business work"*, pero sin más información útil.
3. **Buscar cambios en el archivo message.py**

    - Para ver qué cambios ocurrieron en el archivo a lo largo del tiempo, usamos:
        git log -p -- message.py
        
    - Si la bandera fue eliminada en algún commit, esto nos mostrará exactamente cuándo y cuál era su contenido.
4. *Restaurar una versión anterior del archivo*
    
    - Si encontramos un commit donde la bandera estaba presente, podemos restaurarlo con:
        git checkout <commit_id> -- message.py
        
    - Luego, verificamos el contenido con:
        cat message.py
        
5. *Extraer la bandera*
    
    - Una vez que encontramos la versión del archivo que contenía la bandera, la copiamos y la enviamos como respuesta.

---

 *Respuesta en el formato del concurso:*
picoCTF{@sk_th3_1nt3rn_2c6bf174}

 *Referencias*

- Uso de git log -p para ver cambios en archivos.
- git checkout para restaurar versiones antiguas de archivos.
- Métodos para recuperar archivos eliminados en Git