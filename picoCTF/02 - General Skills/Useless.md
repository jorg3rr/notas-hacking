#### Descripción

Hay un script interesante en el directorio de inicio del usuarioEl equipo de trabajo está ejecutando SSH. Nos han dado un script que realiza algunos cálculos básicos, explora el script y encuentra una bandera.

### Solución

El objetivo es conectarse al servidor y ejecutar el script con los argumentos adecuados para obtener la bandera.

#### Métodos:

- **Conexión al servidor mediante SSH:**

    `ssh picoplayer@saturn.picoctf.net -p 63553`
    
- **Explorar el contenido del directorio:**
    
    Ejecutar el comando `ls` para ver el archivo `useless`.
    `ls`
- **Ejecutar el script:**
    
    Ejecutar el script sin argumentos para obtener una indicación sobre cómo usarlo:
    `./useless`
    
- **Ejemplo de uso del script:**
    
    Realizar operaciones con el script utilizando los comandos adecuados:
    
    - **Suma:**
                
        `./useless add 10 20 # Salida: The Sum is: 30`
        
    - **Multiplicación:**
                
        `./useless mul 10 20 # Salida: The product is: 200`
        
    - **Comando inválido:**
        
        `./useless xyz 10 20 # Salida: Read the manual`
        
- **Consultar la página de manual:**
    
    Utilizar el comando `man` para obtener más información sobre el script:
    `man useless`
    
    La página de manual proporciona ejemplos de uso y describe las operaciones disponibles.
### Resultado esperado

Al ejecutar el script correctamente con los argumentos deseados, obtendrás la bandera:

`picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_6194}`

#### Notas adicionales

- Es importante leer el código del script para entender cómo se procesan los argumentos y las operaciones.
- Asegúrate de seguir el formato correcto al proporcionar los argumentos al script.
- Si el script devuelve mensajes de error, revisa que los comandos y los parámetros sean correctos.

#### Referencias

- Manual de Bash
- Guía de uso de SSH