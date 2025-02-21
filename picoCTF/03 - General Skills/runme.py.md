#### Descripción

Ejecute el script para obtener la marca. Descargue el script con su navegador o con en la webshell.runme.pywget[Descargar runme.py script de Python](https://artifacts.picoctf.net/c/34/runme.py)

*Solución*

1. *Ejecutar el script*  
    En la terminal, corremos el siguiente comando:
    python3 runme.py
    
    Esto imprimirá la bandera en pantalla.
    
2. *Analizar el contenido del script*  
    Si queremos ver el código sin ejecutarlo, usamos:
    cat runme.py
    
3. *Ver la bandera en el código*  
    El script contiene la siguiente línea que almacena la bandera:
    flag = 'picoCTF{run_s4n1ty_run}' print(flag)
    
    Por lo que ya tenemos la bandera sin necesidad de ejecutar el código.
    

 *Respuesta en el formato del concurso*
picoCTF{run_s4n1ty_run}


*Notas adicionales*

- *No es necesario ejecutar el script*, ya que la bandera está visible en el código fuente.