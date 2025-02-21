### Descripción

Ejecute el script de Python e ingrese la contraseña correcta para descifrar la bandera. La bandera cifrada debe estar en el mismo directorio que el script.

### Archivos proporcionados:

- `level2.py`: Script en Python que solicita una contraseña y descifra la bandera si es correcta.
- `level2.flag.txt.enc`: Archivo con la bandera cifrada.

### Solución

1. **Abrir una terminal en Windows o Linux**
    
    Para ejecutar el script, usa el siguiente comando en la terminal:

    `python level2.py`
    
    Si `python` no funciona, prueba con `python3`.
    
2. **Ingresar la contraseña correcta**
    
    - El script solicita una contraseña.
        
    - La contraseña correcta está codificada en valores hexadecimales dentro del código fuente:
                
        `chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)`
        
        - `0x34` → `"4"`
        - `0x65` → `"e"`
        - `0x63` → `"c"`
        - `0x39` → `"9"`
        
        **Contraseña:** `"4ec9"`
        
3. **Obtener la bandera**
    
    - Si la contraseña es correcta, el script descifrará la bandera usando la función `str_xor` y la mostrará en pantalla.

##### Resultado:
picoCTF{tr45h_51ng1ng_9701e681}

### Notas adicionales

- La función `str_xor` se usa para descifrar la bandera con la contraseña proporcionada.
- Asegúrate de que el archivo `level2.flag.txt.enc` esté en el mismo directorio que `level2.py` al ejecutar el script.

### Referencias

- [Documentación de Python](https://docs.python.org/3/)
- [Concepto de XOR en criptografía](https://en.wikipedia.org/wiki/XOR_cipher)
- [Conversión de valores hexadecimales en Python](https://docs.python.org/3/library/functions.html#chr)