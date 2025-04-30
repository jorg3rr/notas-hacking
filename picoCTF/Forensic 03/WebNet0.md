#### Descripción

Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) y [clave](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recupera la bandera.

*Solución*

1. Abrir en Wireshark
    
2. Vaya a Editar > Preferencias > la lista de protocolos > claves TLS > RSA
    
3. Agregue la clave a la lista (no se preocupe por la ip y otras columnas)
    
4. La bandera se encuentra en la sección TLS descifrada de los paquetes HTTP ahora visibles
    
    
    HTTP/1.1 200 OK
    Date: Fri, 23 Aug 2019 15:56:36 GMT
    Server: Apache/2.4.29 (Ubuntu)
    Last-Modified: Mon, 12 Aug 2019 16:50:05 GMT
    ETag: "5ff-58fee50dc3fb0-gzip"
    Accept-Ranges: bytes
    Vary: Accept-Encoding
    Content-Encoding: gzip
    *Pico-Flag: picoCTF{nongshim.shrimp.crackers}*
    Content-Length: 821
    Keep-Alive: timeout=5, max=100
    Connection: Keep-Alive
    Content-Type: text/html
    
    

*Respuesta en el formato del concurso:*
picoCTF{nongshim.shrimp.crackers}