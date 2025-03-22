##### Descripción

La fábrica está ocultando cosas a todos sus usuarios. ¿Puedes iniciar sesión como Joe y encontrar lo que han estado mirando?

##### Solución

El objetivo es iniciar sesión como Joe y encontrar la bandera.

##### Pasos:

1. **Abrir el sitio web**
    
    - Abrir el enlace proporcionado en el navegador.
        
    - Aparece una pantalla de inicio de sesión donde puedes ingresar como Joe.
        
2. **Iniciar sesión como Joe**
    
    - Utiliza las credenciales de Joe para iniciar sesión.
        
    - El sistema mostrará el mensaje: `Success: You logged in! Not sure you'll be able to see the flag though.`
        
3. **Abrir el código fuente de la página**
    
    - Si las herramientas de desarrollo están bloqueadas, intenta abrirlas mediante el menú o el inspector del navegador.
        
4. **Editar cookies usando Cookie Editor**
    
    - Abre el complemento `Cookie Editor` en el navegador.
        
    - Busca las cookies relacionadas con el sitio web.
        
    - Identifica una cookie llamada `admin` que tiene el valor `False`.
        
    - **Cambia el valor de** `**admin**` **de** `**False**` **a** `**True**` y guarda los cambios.
        
5. **Refrescar la página**
    
    - Después de modificar la cookie, actualiza la página.
        
    - La bandera aparecerá en pantalla.
        

##### Resultado

La bandera encontrada es:
picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}
##### Notas adicionales

- Si las herramientas de desarrollo están bloqueadas, intenta abrir las cookies desde la configuración del navegador.
    
- Si el valor de `admin` vuelve a cambiar a `False`, intenta establecerlo nuevamente antes de actualizar la página.
    

##### Referencias

- Uso de Cookie Editor