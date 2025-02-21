##### Descripción

El uso de un Secure Shell (SSH) va a ser bastante importante. ¿Se puede llegar a puerto para conseguir la bandera?

**Detalles de conexión:**

- **Servidor:** titan.picoctf.net
    
- **Puerto:** 63241
    
- **Usuario:** ctf-player
    
- **Contraseña:** (proporcionada en el reto)

Si se solicita, acepte la huella digital con:

```
yes
```

Si tu dispositivo no tiene shell, puedes usar la terminal web: [Webshell de picoCTF](https://webshell.picoctf.org)

##### Solución

El objetivo es conectarse al servidor SSH y encontrar la bandera.

##### Pasos:

1. **Conectarse al servidor SSH**
    
    ```
    ssh ctf-player@titan.picoctf.net -p 63241
    ```
    
    Ingresar la contraseña cuando se solicite.
    
2. **Verificación de autenticidad**
    
    Al conectarnos, aparecerá un mensaje sobre la autenticidad del servidor. Escribimos `yes` para continuar.
    
3. **Ingresar la contraseña**
    
    Se nos pedirá la contraseña. Luego de ingresarla correctamente, se nos dará acceso al sistema.
    
4. **Obtener la bandera**
    
    Una vez dentro, el sistema nos da la bandera directamente:
    
    ```
    Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_65a7a106}
    ```
    
5. **Desconexión automática**
    
    Después de mostrar la bandera, la conexión se cierra automáticamente.
    

##### Resultado

Se obtiene la bandera directamente tras la autenticación:

```
picoCTF{s3cur3_c0nn3ct10n_65a7a106}
```

##### Notas adicionales

- Si la contraseña no es aceptada, verificar que se está ingresando correctamente sin errores tipográficos.

##### Referencias

- [Guía de SSH](https://linux.die.net/man/1/ssh)
    
- [Introducción a la shell](https://primer.picoctf.com/#_the_shell)