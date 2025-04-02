#### Descripción

La marca se encuentra en algún lugar de esta aplicación web, no necesariamente en el sitio web. Encuéntralo. Echa un vistazo [a esto](http://saturn.picoctf.net:56866/).

> **Solución:**

En cuanto al nombre del desafío, es posible que este desafío tenga algo que ver con el robots.txt que forma parte del protocolo de exclusión de robots. Robots.txt es un archivo de texto creado para instruir a los robots web sobre cómo rastrear páginas en su sitio web. El robots.txt puede indicar si ciertos agentes de usuario (software de rastreo web) pueden o no rastrear partes de un sitio web.

1. Entonces, entendiendo que los sitios web tienen un robots.txt, veamos si este sitio web tiene uno yendo a: /robots.txt

![](https://miro.medium.com/v2/resize:fit:875/1*OqgPtESEidsQZw0htsNKVw.png)

robots.txt

2. Ahora viendo que lo hace, hay información en el archivo que no permite "/cgi-bin/" y "/wp-admin/", Ir a cada ruta devuelve un 404:

3. También teniendo en cuenta que hay una cadena que es codificación base64 y si decodificamos en [base64decode](https://www.base64decode.org/) obtenemos una ruta que no debería estar en la cadena robots.txt:  
Base64:  
ZmxhZzEudHh0; anMvbXlmaW

Cadena decodificada:  
flag1.txtjs/myfi

Base64 string:  
svssshjweuiwl; oiho.bsvdaslej

Cadena decodificada:  
, z谖/u%z

Base64 string:  
anMvbXlmaWxlLnR4dA==

Cadena decodificada:  
js/myfile.txt

4. Al ver que "js/myfile.txt" podría ser una ruta en el servidor así que vamos a donde se encuentra ese archivo y obtenemos nuestra bandera:

Bandera:

`picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}`

