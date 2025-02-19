#### Descripción

¿Puedes encontrar la bandera en el archivo sin ejecutarlo?

#### Solución

El objetivo es analizar el archivo en busca de la bandera sin ejecutarlo.

##### Métodos:

1. **Usar el comando `strings` en Linux:**    
    `strings strings | grep picoCTF`

    Esto buscará la palabra **"picoCTF"** en el archivo, lo que generalmente revela la bandera.

##### Resultado:
picoCTF{5tRIng5_1T_827aee91}

#### Notas adicionales

- Si el archivo es binario y `strings` no muestra nada útil, podría estar comprimido o cifrado.

#### Referencias

- Comando strings - Linux
- [CyberChef](https://gchq.github.io/CyberChef/)
