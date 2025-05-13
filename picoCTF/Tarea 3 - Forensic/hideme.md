#### Descripción

Cada archivo recibe una marca.El analista de SOC vio que una imagen se enviaba de un lado a otro entre dos personas. Decidieron investigar y descubrieron que [aquí](https://artifacts.picoctf.net/c/261/flag.png) había más de lo que parece.
### Solución
La utilidad identificó un archivo zip adjunto al archivo de imagen de bandera original:binwalk

$ binwalk flag.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2997, uncompressed size: 3152, name: secret/flag.png
43036         0xA81C          End of Zip archive, footer length: 22


El archivo zip se extrajo mediante:binwalk


$ binwalk -e flag.png

Esto produjo otro dentro del cual cuando se vio con un editor de imágenes y se mostró la bandera (el valor real de la bandera se redactó para los fines de este artículo):flag.pnghideme/_flag.png.extracted/secret/flag.png

### Bandera
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_cda72af0}