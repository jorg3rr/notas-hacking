**Descripción**  
Nuestro servicio de impresión de banderas ha comenzado a fallar. Se proporciona el siguiente comando para interactuar con el servicio:

`$ nc saturn.picoctf.net 49574`

### **Solución**

El servidor devuelve una cadena que contiene valores hexadecimales representando caracteres en ASCII. Para obtener la bandera, es necesario convertir estos valores a texto legible.

Pasos:

- Conectar al servicio con el comando
   `nc saturn.picoctf.net 49574`
- Recibir la cadena de salida del servidor.
- Identificar los valores en formato hexadecimal y convertirlos a ASCII.

Resultado:
`picoCTF{gl17ch_m3_n07_a4392d2e}`

### **Notas adicionales**

- Se pueden usar herramientas en línea para la conversión de hexadecimal a ASCII, como CyberChef.
- También se puede realizar la conversión directamente en un intérprete de Python con la función `chr()`.

### **Referencias**

- [Conversión de Hex a ASCII](https://www.rapidtables.com/convert/number/hex-to-ascii.html)
- [CyberChef - Herramienta de conversión](https://gchq.github.io/CyberChef/)
