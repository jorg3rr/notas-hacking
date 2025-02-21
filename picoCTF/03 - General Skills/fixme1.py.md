##### Descripción

Corrija el error de sintaxis en este script de Python para imprimir la bandera.

##### Archivos proporcionados:

- `fixme1.py`: Script en Python con un error de sintaxis.
    

##### Solución

1. **Abrir el archivo** `**fixme1.py**`
    
    Se puede abrir con un editor de texto o un IDE como VS Code, Notepad++, o directamente en la terminal con:
    
    ```
    notepad fixme1.py
    ```
    
    o en Linux/Mac:
    
    ```
    nano fixme1.py
    ```
    
2. **Identificar el error de sintaxis**
    
    Al observar el código, se nota que la línea:
    
    ```
      print('That is correct! Here\'s your flag: ' + flag)
    ```
    
    está mal indentada. Python no permite espacios adicionales antes de `print` en este contexto.
    
3. **Corregir la indentación**
    
    Se debe eliminar la indentación incorrecta, dejando:
    
    ```
    flag = str_xor(flag_enc, 'enkidu')
    print('That is correct! Here\'s your flag: ' + flag)
    ```
    
4. **Ejecutar el script corregido**
    
    Guardar los cambios y ejecutar:
    
    ```
    python fixme1.py
    ```
    
    Si `python` no funciona, probar con:
    
    ```
    python3 fixme1.py
    ```
    
5. **Obtener la bandera**
    
    Si la corrección es correcta, el script imprimirá la bandera en la terminal.
    

##### Resultado

Ejecutar el script corregido mostrará la bandera en formato `picoCTF{...}`.

##### Notas adicionales

- Si el error persiste, verificar la versión de Python con:
    
    ```
    python --version
    ```
    
- Si el archivo tiene otros errores, revisar el código con cuidado y corregirlos antes de ejecutar.
    

##### Referencias

- [Documentación de Python](https://docs.python.org/3/)