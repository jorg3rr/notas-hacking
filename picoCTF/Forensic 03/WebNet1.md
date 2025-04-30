Descripción

Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) y [clave](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recupera la bandera.

*Solución*

1. Abrir en Wireshark
    
2. Vaya a Editar > Preferencias > la lista de protocolos > claves TLS > RSA
    
3. Agregue la clave a la lista (no se preocupe por la ip y otras columnas)
    
4. La bandera está en la sección SSL reensamblado del paquete JPEG JFIF


TTP/1.1 200 OK
Date: Fri, 23 Aug 2019 16:27:04 GMT
Server: Apache/2.4.29 (Ubuntu)
Last-Modified: Fri, 23 Aug 2019 16:26:33 GMT
ETag: "112fb-590cb44f2cbe6"
Accept-Ranges: bytes
Content-Length: 70395
Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
Keep-Alive: timeout=5, max=99
Connection: Keep-Alive
Content-Type: image/jpeg

ÿØÿàJFIFÿáExifMM*JR(;ZpicoCTF{honey.roasted.peanuts}ÿâICC_PROFILElcmsmntrRGB XYZ Ü)9acspAPPLöÖÓ-lcms


*Respuesta en el formato del concurso:*
`picoCTF{honey.roasted.peanuts}`