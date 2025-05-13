### Descripción

Explore cómo automatizar tareas para que se ejecuten a intervalos en servidores Linux utilizando `cron`.

### Acceso al servidor

El administrador del sistema ha aprovisionado una cuenta para usted en el servidor principal.

**Credenciales:**

- **Servidor:** `saturn.picoctf.net`
- **Puerto:** `64977`
- **Usuario:** `picoplayer`
- **Contraseña:** `kZx-HVJKu8`

### Solución

1. **Abrir la terminal en Windows**
    
    Para acceder al servidor, use el siguiente comando en la terminal de Windows:
        
    `ssh -p 64977 picoplayer@saturn.picoctf.net`
    
2. **Aceptar la clave del servidor**
    
    - Si es la primera vez que se conecta, verá un mensaje sobre la autenticidad del host.
    - Escriba `yes` y presione **Enter** para continuar.
3. **Ingresar la contraseña**
    
    Cuando se le solicite, ingrese la contraseña:
    
    `kZx-HVJKu8`
    
4. **Revisar las tareas programadas en `cron`**
    
    - `cron` es un servicio en Linux que permite la ejecución de tareas automáticas en intervalos regulares.
        
    - Para ver las tareas programadas en el sistema, se ejecutó el siguiente comando:
        
        `cat /etc/crontab`
        
    - Se obtuvo la bandera dentro del archivo:
        
        `# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}`
        
5. **Cierre de conexión**
    
    - La conexión se cerró automáticamente después de ejecutar el comando.

### Notas adicionales

- El archivo `/etc/crontab` contiene las tareas programadas del sistema y define qué comandos se ejecutan automáticamente en ciertos momentos.
    
- Para listar las tareas programadas de un usuario específico, se puede usar:
    `crontab -l`
    
- Para editar tareas programadas del usuario actual:    
    `crontab -e`
    
### Referencias

- [Uso de `cron` en Linux](https://help.ubuntu.com/community/CronHowto)
- Documentación de `crontab`