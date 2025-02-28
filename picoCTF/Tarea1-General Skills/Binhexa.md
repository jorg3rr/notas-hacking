##### Descripción

¿Qué tan bien puedes realizar operaciones binarias básicas? Empieza a buscar la bandera aquí:

```
nc titan.picoctf.net 54154
```

##### Solución

El objetivo es realizar correctamente las operaciones binarias dadas en cada paso y convertir el resultado final a hexadecimal para obtener la bandera.

##### Pasos:

1. **Conectarse al servidor**
    
    ```
    nc titan.picoctf.net 54154
    ```
    
    Se presentan dos números binarios:
    
    - **Binary Number 1**: `11100110`
        
    - **Binary Number 2**: `11101010`
        
2. **Resolver cada operación paso a paso**
    
    - **Pregunta 1:**
        
        ```
        Operation: '>>' (Right Shift)
        Shift Binary Number 2 by 1 bit
        ```
        
        Resultado correcto:
        
        ```
        01110101
        ```
        
    - **Pregunta 2:**
        
        ```
        Operation: '&' (AND)
        Binary Number 1 & Binary Number 2
        ```
        
        Resultado correcto:
        
        ```
        11100010
        ```
        
    - **Pregunta 3:**
        
        ```
        Operation: '*' (Multiplication)
        Binary Number 1 * Binary Number 2
        ```
        
        Resultado correcto:
        
        ```
        1101001000111100
        ```
        
    - **Pregunta 4:**
        
        ```
        Operation: '|' (OR)
        Binary Number 1 | Binary Number 2
        ```
        
        Resultado correcto:
        
        ```
        11101110
        ```
        
    - **Pregunta 5:**
        
        ```
        Operation: '+' (Addition)
        Binary Number 1 + Binary Number 2
        ```
        
        Resultado correcto:
        
        ```
        111010000
        ```
        
    - **Pregunta 6:**
        
        ```
        Operation: '<<' (Left Shift)
        Shift Binary Number 1 by 1 bit
        ```
        
        Resultado correcto:
        
        ```
        111001100
        ```
        
3. **Convertir el último resultado a hexadecimal**
    
    ```
    111001100 (bin) -> 1CC (hex)
    ```
    
    Ingresando `1CC` como respuesta final se obtiene la bandera.
    

##### Resultado

La bandera encontrada es:

```
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_aeaf4b09}
```

##### Notas adicionales

- Se utilizó Binary Calculator de RapidTables para validar los cálculos.
    
- Las operaciones bit a bit (`AND`, `OR`, `XOR`, shifts) son fundamentales en ciberseguridad y criptografía.
    

##### Referencias

- Operaciones bit a bit en Python