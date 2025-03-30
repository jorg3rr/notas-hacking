### Descripción

¡Revisa el bloc de notas del administrador!  
**Enlace:** [http://jupiter.challenges.picoctf.org:58210](http://jupiter.challenges.picoctf.org:58210)

---

### Proceso de resolución

1. Utilicé **Cookie Editor** para copiar el JWT.
    
2. Ingresé el JWT en [jwt.io](https://jwt.io/) y observé que la firma era inválida.
    
3. Utilicé **JohnTheRipper** para crackear la contraseña del token. La contraseña era `ilovepico`.
    
4. Modifiqué el usuario a `admin` y generé un nuevo JWT válido con la nueva firma.
    
5. Agregué el nuevo JWT a la página utilizando **Cookie Editor**.
    
6. Al actualizar la página, se mostró la bandera.


### Resultado de la bandera

**picoCTF{jawt_was_just_what_you_thought_44c752f5}**

---

### Notas adicionales

- La contraseña `ilovepico` fue obtenida mediante fuerza bruta.
    
- Un JWT modificado correctamente permite acceso a privilegios elevados.
    

---

### Referencias

- [jwt.io](https://jwt.io/) para analizar y modificar JWTs.
    
- **JohnTheRipper** para realizar la fuerza bruta sobre la firma del JWT.
    
- **Cookie Editor** para modificar las cookies en el navegador.
    