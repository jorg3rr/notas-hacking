#### Descripción

¿La saga de Rust continúa? Te pregunto, ¿puedo tomar prestado eso, pleeeeeaaaaasseeeee?Descarga el código de Rust [aquí](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

### Solución

Intente ejecutar el script y vea qué sucede

shell
┌──(kali㉿kali)-[/mnt/…/picoCTF/Beginner_picoMini_2022/General_Skills/Fixme2.py]
└─$ python fixme2.py 
  File "/mnt/hgfs/CTFs/picoCTF/Beginner_picoMini_2022/General_Skills/Fixme2.py/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?


Python es lo suficientemente amable como para sugerir posibles soluciones. Cambie el '=' a un '==' y guarde el script.  
'=' es el operador de asignación y '==' es el operador de comparación igual.

A continuación, intente ejecutar el script de nuevo

shell
┌──(kali㉿kali)-[/mnt/…/picoCTF/Beginner_picoMini_2022/General_Skills/Fixme2.py]
└─$ python fixme2.py
That is correct! Here's your flag: picoCTF{picoCTF{4r3_y0u_h4v1n5_fun_y31?}}

### Bandera
*Respuesta en el formato del concurso:*
picoCTF{4r3_y0u_h4v1n5_fun_y31?}