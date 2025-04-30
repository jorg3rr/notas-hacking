#### Description

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/5ef2e9103d55972d975437f68175b9ab/dolls.jpg)

*Solución*

1. El problema sugiere que los archivos se colocan dentro de otros archivos, así que ejecutemos .binwalk dolls.jpg
    
    Copiar
    
    
    DECIMAL       HEXADECIMAL     DESCRIPTION
    --------------------------------------------------------------------------------
    0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
    3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
    272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378956, uncompressed size: 383938, name: base_images/2_c.jpg
    651614        0x9F15E         End of Zip archive, footer length: 22
    
    
    Efectivamente, hay varios archivos.
    
2. Podemos extraer los archivos ejecutando y luego .binwalk --dd='.*' dolls.jpgcd _dolls.jpg.extracted
    
3. Después de un poco de prueba y error, la solución correcta es extraer el archivo zip, y luego repetir el paso 3 en .cd base_images2_c.jpg
    
4. Ahora que está en , extraiga el archivo zip y repita el paso 3._2_c.jpg.extracted
    
5. Repita los pasos anteriores de extracción e ing hasta que termine en este camino: . Hay un archivo en este directorio que contiene la bandera.binwalk_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted/136DA-(1)flag.txt
    

*Respuesta en el formato del concurso:*
picoCTF{336cf6d51c9d9774fd37196c1d7320ff}