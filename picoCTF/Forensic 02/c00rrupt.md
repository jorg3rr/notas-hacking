### Descripción

> Encontramos este archivo. Recupera la bandera. También puede encontrar el archivo en /problems/c0rrupt_0_1fcad1344c25a122a00721e4af86de13.

- [El archivo](https://github.com/HHousen/PicoCTF-2019/tree/24b0981c72638c12f9a8572f81e1abbcf8de306d/Forensics/c0rrupt/mystery/README.md)
    

### Solución

1. Marcar el no indica nada. Sin embargo, al ver el archivo misterioso se muestra que parece una imagen PNG:`file mystery``head`

2. La [especificación PNG](https://www.w3.(los primeros ocho bytes de un flujo de datos PNGdebe ser (decimal) o (hexadecimal).`137 80 78 71 13 10 26 10``89 50 4E 47 0D 0A 1A 0A`
    
3. Así que vamos a reemplazar la firma usando [un editor hexadecimal](https://hexed.it/)    ```
    
4. Después del encabezado vienen una serie de trozos. Cada fragmento comienza con 4 bytes para la longitud del fragmento, 4 bytes para el tipo, luego el contenido del fragmento en sí (con la longitud declarada anteriormente) y 4 bytes de una suma de comprobación. Consulte la sección "Diseño de fragmentos 5.3" de [esta página](https://www.w3.org/TR/2003/REC-PNG-20031110/#5Chunk-layout) para obtener más información.
    
5. El primer fragmento se llama y tiene la longitud de , por lo que sabemos que los siguientes 8 bytes son (hexadecimales):`IHDR``0xD``00 00 00 0D 49 48 44 52`
    
    
    
    ```
     $ xxd -g 1 mystery.png | head
     00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 49 48 44 52  .PNG........IHDR
     00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
     00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
     00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
     00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
     00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
     00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
     00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
     00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
     00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
    ```
6. Ahora el archivo se identifica como un archivo PNG:

    
    ```
     $ file fixed.png
     fixed.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
    ```
    
7. `pngcheck` enumera dos errores más para resolver:
    
    ```
     pngcheck -vf mystery.png
     File: mystery.png (202940 bytes)
     chunk IHDR at offset 0x0000c, length 13
         1642 x 1095 image, 24-bit RGB, non-interlaced
     chunk sRGB at offset 0x00025, length 1
         rendering intent = perceptual
     chunk gAMA at offset 0x00032, length 4: 0.45455
     chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
     CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
     :  invalid chunk length (too large)
    ```
    
    Necesitamos corregir el error CRC (suma de comprobación) en el fragmento y encontrar un fragmento con una longitud no válida.`pHYs`
    
8. El error CRC significa que la suma de comprobación (valor CRC) está dañada o que los datos lo están. Para resolver este error en chunk, simplemente podemos reemplazar el valor CRC (esperado) con el valor calculado. El propósito de la sección CRC es verificar la corrupción de los datos. Básicamente, es una suma de comprobación de ese fragmento. Si bien reemplazar el CRC funcionará, el método más "correcto" es corregir el contenido para obtener el mismo CRC, solucionando así la corrupción que ocurrió. La siguiente tabla muestra el diseño del fragmento:`pHYs``pHYs``pHYs`
    

    Dado que los píxeles por unidad difieren en solo un byte, y el eje para X hace que el valor sea muy grande, tiene sentido colocar un cero en su lugar. Esto corrige la suma de comprobación.`0xaa`
    

9. El error no especifica un fragmento, por lo que debemos comenzar desde el principio y verificar cada fragmento, con el conocimiento del formato de los fragmentos y la longitud de cada campo: 4 bytes (longitud) - 4 bytes (tipo de fragmento) - lengthbytes (datos) - 4 bytes (CRC).`invalid chunk length (too large)`
    
10. El fragmento siguiente tiene un tamaño de , que es muy grande, y un tipo del cual no existe. El tipo de fragmento más cercano es [IDAT.](https://www.w3.org/TR/2003/REC-PNG-20031110/#11IDAT) Vamos a arreglar eso reproduciendo el nombre del fragmento con (hexadecimal).`pHYs``0xaaaaffa5``\xabDET``49 44 41 54`
    
11. Para resolver la longitud del trozo grande, necesitamos calcular la longitud del trozo y actualizar su valor. Los trozos deben ser consecutivos, así que busquemos el siguiente. Encontramos el siguiente IDAT en offset . El primer IDAT estaba en offset . La diferencia es FFB1. Debemos restar 4 bytes para el campo de longitud del segundo IDAT, restar 4 bytes para el CRC del primer IDAT y restar 4 bytes nuevamente para el chunktype del primer IDAT. Restando 12 en total, obtenemos FFA5. Reemplace el campo de longitud por (hexadecimal). El valor original era, por lo que solo necesitábamos sobrescribir el archivo con .`IDAT``0x10008``0x57``00 00 FF A5``0xAAAAFFA5``AAAA``0000`
    
12. La ejecución muestra, lo que significa que no hay errores y podemos abrir la imagen: `pngcheck mystery.png``mystery.png (1642x1095, 24-bit RGB, non-interlaced, 96.3%).`![Imagen misteriosa corregida usando el método anterior](
    

### Bandera

`picoCTF{c0rrupt10n_1847995}`