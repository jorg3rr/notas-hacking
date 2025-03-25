#### Descripción

Hay información interesante escondida en este sitio. [(enlace)](http://mercury.picoctf.net:44070/)

#### Solución

El objetivo es buscar en distintas ubicaciones del sitio web para encontrar partes de la bandera.

#### Pasos

1. **Inspeccionar el código fuente**
    
    - Se accede a la página principal con `curl`:
        
        ```
        curl http://mercury.picoctf.net:44070/
        ```
        
    - En los comentarios HTML se encuentra la primera parte de la bandera:
        
        ```
        <!-- Here's the first part of the flag: picoCTF{t -->
        ```
        
2. **Consultar la hoja de estilos CSS**
    
    - Se obtiene con:
        
        ```
        curl http://mercury.picoctf.net:44070/mycss.css
        ```
        
    - En un comentario dentro del archivo CSS se encuentra la segunda parte:
        
        ```
        /* Here's part 2: h4ts_4_l0 */
        ```
        
3. **Revisar** `**robots.txt**`
    
    - Se obtiene con:
        
        ```
        curl http://mercury.picoctf.net:44070/robots.txt
        ```
        
    - Contiene la tercera parte de la bandera:
        
        ```
        # Part 3: t_0f_pl4c
        ```
        
4. **Revisar** `**.htaccess**`
    
    - Se obtiene con:
        
        ```
        curl http://mercury.picoctf.net:44070/.htaccess
        ```
        
    - Contiene la cuarta parte:
        
        ```
        # Part 4: 3s_2_lO0k
        ```
        
5. **Consultar** `**.DS_Store**`
    
    - Se obtiene con:
        
        ```
        curl http://mercury.picoctf.net:44070/.DS_Store
        ```
        
    - Contiene la última parte:
        
        ```
        Part 5: _7a46d25d}
        ```
        
6. **Construir la bandera**
    
    - Juntando todas las partes obtenemos:
        
        ```
        picoCTF{t h4ts_4_l0 t_0f_pl4c 3s_2_lO0k _7a46d25d}
        ```
        
    - Eliminando los espacios:
        
        ```
        picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}
        ```
        

#### Resultado

La bandera encontrada es:

```
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}
```

#### Notas adicionales

- Este reto demuestra cómo la información puede estar escondida en diferentes archivos del servidor web.
    
- Herramientas como `curl` o `wget` facilitan la exploración de estos archivos.
    

#### Referencias

- Exploración de servidores web con `curl`
    
- Uso de `robots.txt`