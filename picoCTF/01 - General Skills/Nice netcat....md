#### Descripción

Hay un buen programa con el que puedes hablar usando este comando en un shell, pero no habla inglés...
`$ nc mercury.picoctf.net 22342`

#### Solución

El objetivo es conectarse al servidor y entender qué idioma está usando para poder interpretar la respuesta y encontrar la bandera.
##### Métodos:

- **Usar `netcat` para conectarse:**
    
    `nc mercury.picoctf.net 22342`
    
    Esto iniciará una conexión con el servidor.

Resultado:
`picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}`

### Notas adicionales

- Se usó la conversión de ASCII a texto.

#### Referencias

- [Comando nc - Linux](https://linux.die.net/man/1/nc)
- [CyberChef](https://gchq.github.io/CyberChef/)
