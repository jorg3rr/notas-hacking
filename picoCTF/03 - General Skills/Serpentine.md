### Descripción

Ejecute el script de Python para interactuar con el programa y obtener la bandera oculta en el código fuente.

### Archivos proporcionados:

- `serpentine.py`: Script en Python que muestra mensajes de ánimo y contiene la bandera cifrada.
    

### Solución

1. **Abrir una terminal en Windows o Linux**
    
    Para ejecutar el script, usa el siguiente comando en la terminal:
    
    ```
    python serpentine.py
    ```
    
    Si `python` no funciona, prueba con `python3`.
    
2. **Analizar el código fuente**
    
    - El código incluye una opción de menú para imprimir la bandera (`b`), pero en su lugar muestra un mensaje indicando que la función `print_flag()` está perdida.
        
    - Sin embargo, la función `print_flag()` sí existe en el código y puede ejecutarse directamente.
        
3. **Ejecutar la función de forma manual**
    
    - Para obtener la bandera sin modificar el código, puedes ejecutar el script en una sesión interactiva de Python:
        
        ```
        python3
        ```
        
    - Luego, en la sesión interactiva de Python, escribe lo siguiente:
        
        ```
        from serpentine import print_flag
        print_flag()
        ```
        
4. **Entender la lógica de cifrado**
    
    - La bandera está almacenada en la variable `flag_enc` como una secuencia de caracteres codificados con valores en hexadecimal.
        
    - La función `str_xor(secret, key)` descifra la bandera utilizando la clave `"enkidu"` aplicando una operación XOR.
        
5. **Resultado**
    
    - Al ejecutar `print_flag()`, la bandera descifrada se mostrará en pantalla:
        
        `**picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}**`
        

### Notas adicionales

- La bandera está cifrada con una operación XOR y la clave `"enkidu"`.
    
- Puedes modificar el código para llamar directamente a `print_flag()` o usar una sesión interactiva de Python.
    
- La función `str_xor()` es utilizada para descifrar el texto almacenado en `flag_enc`.
    

### Referencias

- [Documentación de Python](https://docs.python.org/3/)
    
- [Concepto de XOR en criptografía](https://en.wikipedia.org/wiki/XOR_cipher)