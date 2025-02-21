##### Descripción

Ejecute el script de Python y convierta el número dado de decimal a binario para conseguir la bandera.

##### Archivos proporcionados:

- `convertme.py`: Script en Python que realiza la conversión.
    

##### Solución

1. **Abrir una terminal en Windows**
    
    Iniciar Python en Windows desde el símbolo del sistema:
    
    ```
    python
    ```
    
    Para salir de la consola interactiva de Python, usa `exit()`. Para ejecutar el script directamente:
    
2. **Ejecutar el script**
    
    ```
    python convertme.py
    ```
    
3. **Convertir el número decimal a binario**
    
    - El script mostrará un número en decimal y pedirá su conversión a binario.
        
    - Se puede convertir manualmente dividiendo entre 2 o usando Python:
        
        ```
        bin(NUMERO_DECIMAL)[2:]
        ```
        
    - Ingresar el resultado **solo con 1s y 0s** en la terminal cuando lo solicite el script.
        
4. **Obtener la bandera**
    
    Si la conversión es correcta, el script mostrará la bandera en formato `picoCTF{4ll_y0ur_b4535_722f6b39}`.


##### Notas adicionales

- Si `python` no funciona, probar `python3`.
    
- Se puede usar la calculadora de Windows en modo programador para hacer la conversión.

##### Referencias

- [Documentación de Python](https://docs.python.org/3/)