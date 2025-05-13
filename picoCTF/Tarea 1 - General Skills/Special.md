### Descripción

Interactúe con un shell especial que corrige automáticamente la ortografía y convierte las palabras en mayúsculas. Explore su comportamiento y recupere la bandera oculta en el sistema.

### Acceso al servidor

Se proporciona acceso a una instancia especial con las siguientes credenciales:

- **Servidor:** `saturn.picoctf.net`
- **Puerto:** `61833`
- **Usuario:** `ctf-player`
- **Contraseña:** `fd7746b4`

### Solución

1. **Abrir la terminal en Windows**
    
    Para conectarse al servidor, use el siguiente comando en la terminal de Windows:
        
    `ssh -p 61833 ctf-player@saturn.picoctf.net`
    
2. **Ingresar la contraseña**
    
    Cuando se le solicite, ingrese la contraseña:
        
    `fd7746b4`
    
3. **Explorar el entorno del shell especial**
    
    - Se intentó listar archivos usando `ls`, pero el shell modificó la entrada:
        
        `Special$ ls & ls -la Is & is la sh: 1: is: not found sh: 1: Is: not found`
        
    - Se intentó nuevamente usando `ls` con `find` y se detectó un directorio `blargh` con un archivo `flag.txt`:
        
        `Special$ ls & find . Is & find . sh: 1: Is: not found . ./blargh ./blargh/flag.txt`
        
4. **Leer el contenido del archivo `flag.txt`**
    
    - Se utilizó el comando `cat blargh/flag.txt`, pero el shell alteró la entrada:
        
        `Special$ apapun & cat blargh/flag.txt Apapun & cat blargh/flag.txt sh: 1: Apapun: not found picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}`
        
    - Se logró obtener la bandera:
        
        `picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}`
        
5. **Cierre de conexión**
    
    - Después de obtener la bandera, se pudo salir del shell utilizando:
        `exit`
### Notas adicionales

- El shell modificaba comandos automáticamente, lo que generaba errores en algunas ejecuciones.
- Se logró listar archivos usando `find` en lugar de `ls`.
- A pesar de las modificaciones en los comandos, `cat` funcionó correctamente para leer la bandera.

### Referencias

- Uso de `find` en Linux
- Comandos básicos de Linux