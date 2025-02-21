### Descripción

Ejecute el script de Python e ingrese la contraseña correcta para descifrar la bandera. La bandera cifrada debe estar en el mismo directorio que el script.
### Solución

1. **Abrir una terminal en Windows o Linux**
    
    Para ejecutar el script, usa el siguiente comando en la terminal:
    
    ```
    python level3.py
    ```
    
    Si `python` no funciona, prueba con `python3`.
    
2. **Examinar el código fuente**
    
    - El script utiliza una lista de 7 contraseñas posibles:
        
        ```
        pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]
        ```
        
    - La contraseña ingresada por el usuario es convertida a un hash MD5 con la función `hash_pw()`:
        
        ```
        def hash_pw(pw_str):
            pw_bytes = bytearray()
            pw_bytes.extend(pw_str.encode())
            m = hashlib.md5()
            m.update(pw_bytes)
            return m.digest()
        ```
        
    - El hash generado se compara con el valor almacenado en `level3.hash.bin` para determinar si es correcto.
        
3. **Determinar la contraseña correcta**
    
    - Calculamos el hash MD5 de cada contraseña en `pos_pw_list` y lo comparamos con el contenido de `level3.hash.bin`.
        
    - La contraseña correcta encontrada es:
        `**865e**`
4. **Descifrar la bandera**
    
    - El script usa la función `str_xor()` para descifrar la bandera utilizando la contraseña correcta:
        
        ```
        def str_xor(secret, key):
            new_key = key
            i = 0
            while len(new_key) < len(secret):
                new_key = new_key + key[i]
                i = (i + 1) % len(key)        
            return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
        ```
    - Finalmente, la bandera descifrada es:
        `**picoCTF{m45h_fl1ng1ng_2b072a90}**`

### Notas adicionales

- Asegúrate de que los archivos `level3.flag.txt.enc` y `level3.hash.bin` estén en el mismo directorio que `level3.py` al ejecutar el script.
    
- La función `str_xor()` se usa para aplicar una operación XOR entre la bandera cifrada y la contraseña ingresada.
    
- Para calcular hashes MD5 en Python, se usa el módulo `hashlib`.

### Referencias

- [Documentación de Python](https://docs.python.org/3/)
    
- [Concepto de XOR en criptografía](https://en.wikipedia.org/wiki/XOR_cipher)
    
- [Hashing con MD5 en Python](https://docs.python.org/3/library/hashlib.html)