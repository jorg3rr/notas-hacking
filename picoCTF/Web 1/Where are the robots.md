#### Descripción

¿Puedes encontrar a los robots? (enlace) o [http://jupiter.challenges.picoctf.org:36474](http://jupiter.challenges.picoctf.org:36474)


---

#### Solución

1. **Acceder a la página web del reto**  
    Abre el navegador y accede al siguiente enlace:
    
    `http://jupiter.challenges.picoctf.org:36474`  
    
2. **Buscar el archivo `robots.txt`**  
    Los archivos `robots.txt` son usados para indicar qué partes de un sitio web deben o no deben ser indexadas por motores de búsqueda.
    
    Intenta acceder directamente al archivo:
    
    `http://jupiter.challenges.picoctf.org:36474/robots.txt`  
    
    **Salida**:
	User-agent: *
	Disallow: /477ce.html
    
3. **Acceder a la ruta prohibida**  
    El archivo `robots.txt` revela que hay una ruta prohibida `/b3st-robots`. Accede directamente a esa URL:
        
    `http://jupiter.challenges.picoctf.org:36474/477ce.html`  
    
    **Salida**:
    
    picoCTF{ca1cu1at1ng_Mach1n3s_477ce}
    

---

#### Resultado

La bandera encontrada es:


`picoCTF{ca1cu1at1ng_Mach1n3s_477ce}`

---

#### Notas adicionales

- El archivo `robots.txt` suele contener rutas de directorios ocultos o sensibles que no deberían indexarse en buscadores.
- Las rutas bloqueadas en `robots.txt` pueden contener información sensible o archivos de configuración.

---

#### Referencias

- Documentación de `robots.txt`