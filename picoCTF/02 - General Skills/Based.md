#### Descripción 
Para obtener realmente 1337, debe comprender diferentes codificaciones de datos, como hexadecimal o binario. ¿Puedes obtener la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conéctese con .nc jupiter.challenges.picoctf.org 29956

#### Solución

El objetivo es conectarse al servidor y resolver los desafíos de conversión de bases numéricas para obtener la bandera.

##### Métodos:

- **Usar `netcat` para conectarse al servidor:**

    `nc jupiter.challenges.picoctf.org 29956`
    
    El servidor probablemente proporcionará números en **binario, hexadecimal, u otra base** y pedirá su conversión a decimal u otra base.
    
- **Usar Python para hacer conversiones rápidamente:**
    
    - **Binario a decimal:**
        `int("101010", 2)  # 42`
        
    - **Hexadecimal a decimal:**    
        `int("0x1f4", 16)  # 500`
        
    - **Decimal a binario:**
        `bin(42)  # '0b101010'`
        
    - **Decimal a hexadecimal:**
        `hex(500)  # '0x1f4'`

Resultado esperado:
picoCTF{learning_about_converting_values_b375bb16}

#### Notas adicionales

- Si el servidor da una serie de preguntas, responde rápido para no perder la conexión.
- Puedes escribir un pequeño script en Python para automatizar las conversiones si es necesario.
- Si el servidor deja de responder, intenta conectarte nuevamente.

#### Referencias

- [Comando nc - Linux](https://linux.die.net/man/1/nc)
- [CyberChef](https://gchq.github.io/CyberChef/)
- Convertidores de bases