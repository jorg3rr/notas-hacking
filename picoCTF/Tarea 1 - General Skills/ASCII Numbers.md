##### Descripción

Convierta la siguiente cadena de números ASCII en una cadena legible:

```
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x35 0x63 0x31 0x31 0x5f 0x6e 0x30 0x5f 0x71 0x75 0x33 0x35 0x37 0x31 0x30 0x6e 0x35 0x5f 0x31 0x6c 0x6c 0x5f 0x74 0x33 0x31 0x31 0x5f 0x79 0x33 0x5f 0x6e 0x30 0x5f 0x6c 0x31 0x33 0x35 0x5f 0x34 0x34 0x35 0x64 0x34 0x31 0x38 0x30 0x7d
```

##### Solución

El objetivo es convertir la secuencia hexadecimal en texto ASCII legible.

##### Pasos:

1. **Usar CyberChef para decodificar**
    
    - Ir a [CyberChef](https://gchq.github.io/CyberChef/)
        
    - En la sección "Recipe", agregar la operación "From Hex"
        
    - Ingresar la secuencia hexadecimal en el campo de entrada
        
    - Obtener la cadena decodificada
        
2. **Conversión manual usando Python (opcional)**
    
    ```
    hex_values = "70 69 63 6f 43 54 46 7b 34 35 63 31 31 5f 6e 30 5f 71 75 33 35 37 31 30 6e 35 5f 31 6c 6c 5f 74 33 31 31 5f 79 33 5f 6e 30 5f 6c 31 33 35 5f 34 34 35 64 34 31 38 30 7d"
    flag = ''.join(chr(int(h, 16)) for h in hex_values.split())
    print(flag)
    ```
    
    Esto imprimirá la bandera en texto legible.
    

##### Resultado

La bandera encontrada es:

```
picoCTF{45c11_n0_qu35710n5_1ll_t311_y3_n0_l135_445d4180}
```

##### Notas adicionales

- La conversión de hexadecimal a ASCII es una técnica común en desafíos CTF.
    
- CyberChef facilita la conversión con múltiples herramientas de manipulación de datos.
    
- Python proporciona métodos rápidos para la conversión con `chr()` y `int()`.
    

##### Referencias

- [CyberChef - From Hex](https://gchq.github.io/CyberChef/)
    
- Conversión de hex a ASCII en Python