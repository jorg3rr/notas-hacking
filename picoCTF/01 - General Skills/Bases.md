#### Descripción
¿Qué significa esto? Creo que tiene algo que ver con las bases.`bDNhcm5fdGgzX3IwcDM1`
#### Solución

El texto parece estar codificado en **Base64**, un sistema de codificación que convierte datos binarios en caracteres ASCII legibles.
Métodos para decodificar:
- **Usar una herramienta en línea:**
  -  Páginas como CyberChef o Base64 Decode.
 - **Usar comandos en la terminal (Linux/macOS):**
- `echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d`

El resultado al decodificar el texto es:
`picoCTF{l3arn_th3_r0p35}`

#### Notas adicionales

- Base64 se usa frecuentemente para codificar datos en sistemas web.
- Si un texto termina en `=` o `==`, es un indicio de que puede estar en Base64.
#### Referencias

- [Base64 Decode](https://www.base64decode.org/)
- [CyberChef](https://gchq.github.io/CyberChef/)
- [Python base64 module](https://docs.python.org/3/library/base64.html)