#### Descripción

Kishor Balan nos avisó de que el siguiente código puede necesitar inspección:

- [http://jupiter.challenges.picoctf.org:41511](http://jupiter.challenges.picoctf.org:41511)
    
- [https://jupiter.challenges.picoctf.org/problem/41511](https://jupiter.challenges.picoctf.org/problem/41511)
    

#### Archivos proporcionados

- No hay archivos proporcionados directamente; el reto se basa en el análisis del código en la página web.
    

#### Solución

El objetivo es inspeccionar el código fuente de la página web para encontrar la bandera.

#### Pasos:

1. **Abrir la página web**
    
    - Visitar el enlace:
        
        - [http://jupiter.challenges.picoctf.org:41511](http://jupiter.challenges.picoctf.org:41511)
            
2. **Inspeccionar el código fuente de la página**
    
    - Clic derecho en la página → **"Ver código fuente de la página"**
        
    - En el código fuente se encontró la primera parte de la bandera:
        
3. **Acceder a la hoja de estilos CSS**
    
    - Agregar `mycss.css` al final de la URL:
        
    - En `mycss.css` se encontró la segunda parte de la bandera:
        
4. **Acceder al archivo JavaScript**
    
    - Agregar `myjs.js` al final de la URL:
        
    - En `myjs.js` se encontró la última parte de la bandera:
        
5. **Unir las partes de la bandera**
    
    - La bandera completa es: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}
        

#### Resultado

La bandera encontrada es: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}

#### Notas adicionales

- Las herramientas de desarrollador son útiles para explorar el código fuente de una página web.
    
- Buscar en los comentarios o archivos CSS y JavaScript suele revelar pistas ocultas.
    

#### Referencias

- [Cómo usar las herramientas de desarrollador](https://developer.mozilla.org/es/docs/Tools)
    
- Documentación sobre inspección de código