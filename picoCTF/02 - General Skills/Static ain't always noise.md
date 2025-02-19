#### Descripción

¿Puedes mirar los datos en este binario: `static`? ¡Este script BASH podría ayudar!
#### Solución

El objetivo es analizar el archivo binario sin ejecutarlo para encontrar información relevante, posiblemente una bandera.

##### Métodos:

1. **Desensamblado con `objdump` usando `ltdis.sh`**
    
    - El script `ltdis.sh` desensambla el archivo y extrae la sección `.text`:
    
        `./ltdis.sh static`
        
    - Genera el archivo `static.ltdis.x86_64.txt` con el código ensamblador.
2. **Extracción de cadenas de texto con `strings`**
    
    - El script también extrae cadenas de texto con sus offsets en hexadecimal:

        `strings -a -t x static > static.ltdis.strings.txt`
        
    - Esto genera `static.ltdis.strings.txt`, donde podríamos buscar patrones específicos como `picoCTF`.
3. **Búsqueda de la bandera**
    
    - Se puede buscar la bandera en las cadenas extraídas:
        
        `grep picoCTF static.ltdis.strings.txt`
        
    - Si no aparece directamente, revisar el archivo de desensamblado en busca de referencias a cadenas codificadas o funciones sospechosas.

##### Resultado:
picoCTF{d15a5m_t34s3r_1e6a7731}

#### Notas adicionales

- Si `strings` no muestra la bandera, puede estar ofuscada o cifrada. En tal caso, analizar `static.ltdis.x86_64.txt` para identificar funciones que manipulen cadenas.
- Herramientas como `radare2` o `Ghidra` pueden ayudar en análisis más profundos.

#### Referencias

- `objdump` en Linux
- `strings` en Linux
- [CyberChef](https://gchq.github.io/CyberChef/)
