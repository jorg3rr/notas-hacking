#### Description

We found this [file](https://mercury.picoctf.net/static/da18eed3d15fd04f7b076bdcecf15b27/tunn3l_v1s10n). Recover the flag.

Solución

1. Hay un problema al abrir el archivo. Correr produce , lo cual no es útil. Podemos verificar una [lista de firmas de archivos](https://en.wikipedia.org/wiki/List_of_file_signatures) y ver si hay una coincidencia entre los bytes mágicos. Podemos ver los primeros bytes en el archivo usando :file tunn3l_v1s10ntunn3l_v1s10n: datatunn3l_v1s10nxxd -g 1 tunn3l_v1s10n | head
    
    Copiar
    
    
    00000000: 42 4d 8e 26 2c 00 00 00 00 00 ba d0 00 00 ba d0  BM.&,...........
    00000010: 00 00 6e 04 00 00 32 01 00 00 01 00 18 00 00 00  ..n...2.........
    00000020: 00 00 58 26 2c 00 25 16 00 00 25 16 00 00 00 00  ..X&,.%...%.....
    00000030: 00 00 00 00 00 00 23 1a 17 27 1e 1b 29 20 1d 2a  ......#..'..) .*
    00000040: 21 1e 26 1d 1a 31 28 25 35 2c 29 33 2a 27 38 2f  !.&..1(%5,)3*'8/
    00000050: 2c 2f 26 23 33 2a 26 2d 24 20 3b 32 2e 32 29 25  ,/&#3*&-$ ;2.2)%
    00000060: 30 27 23 33 2a 26 38 2c 28 36 2b 27 39 2d 2b 2f  0'#3*&8,(6+'9-+/
    00000070: 26 23 1d 12 0e 23 17 11 29 16 0e 55 3d 31 97 76  &#...#..)..U=1.v
    00000080: 66 8b 66 52 99 6d 56 9e 70 58 9e 6f 54 9c 6f 54  f.fR.mV.pX.oT.oT
    00000090: ab 7e 63 ba 8c 6d bd 8a 69 c8 97 71 c1 93 71 c1  .~c..m..i..q..q.
    
    
2. La coincidencia con una imagen BMP. Podemos abrir esta imagen en [Photopea](https://www.photopea.com/), ya que es capaz de cargar la imagen. Sin embargo, todo lo que vemos es una extraña imagen deformada y una bandera falsa.42 4d

3. Podemos cambiar la altura del mapa de bits usando un editor hexadecimal como [HexEd.it](https://hexed.it/). El ancho comienza en el desplazamiento hexadecimal , dura 4 bytes y es seguido por la altura en el desplazamiento , que también es de 4 bytes. La información se encuentra en la [página de Wikipedia de BMP](https://en.wikipedia.org/wiki/BMP_file_format) en "Windows ".1216BITMAPINFOHEADER
    
4. Establezcamos la altura en el mismo número que el ancho (), ya que la imagen parece que parte de ella se extendió hacia afuera. Hacemos el cambio en el editor hexadecimal reemplazando en offset a , guardamos la imagen, y luego la cargamos en [Photopea](https://www.photopea.com/).6e 0432 01166e 04

*Respuesta en el formato del concurso:*
picoCTF{qu1t3_a_v13w_2020}