#### Descripción

Hay algo en el [edificio](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). ¿Puedes recuperar la bandera?

Solución

1. Se trata de un desafío [en el que la bandera está oculta en el bit menos significativo de cada valor de píxel](https://www.boiteaklou.fr/Steganography-Least-Significant-Bit.html).
    
2. La bandera se puede extraer con zsteg:
    
    
     zsteg buildings.png 
     B1, R, LSB, XY .. texto: "^5>R5YZrG"
     B1, RGB, LSB, XY .. texto: "picoCTF{h1d1ng_1n_th3_b1t5}"
     B1, ABGR, MSB, XY .. fichero: Subclave secreta PGP  -
     B2, B, LSB, XY .. texto: "XuH}p#8Iy="
     B3, ABGR, MSB, XY .. texto: "t@Wp-_tH_v\r"
     B4, R, LSB, XY .. texto: "fdD\"\"\"\" "
     b4,r,msb,xy .. texto: "%Q#gpSv0c05"
     B4, G, LSB, XY .. texto: "fDfffDD\"\""
     b4,g,msb,xy .. texto: "f\"fff\"\"DD"
     b4, b, lsb, xy .. texto: "\"$BDDDDf"
     b4,b,msb,xy .. texto: "wwBDDDfUU53w"
     B4, RGB, MSB, XY .. texto: "dUcv%F#A'"
     b4,bgr,msb,xy .. texto: " V\"c7Ga4"
     b4,abgr,msb,xy .. texto: "gOC_$_@o"
    
    
3. Visita [HackTricks](https://book.hacktricks.xyz/stego/stego-tricks) para más información. Steghide se usa para imágenes JPG y Zsteg se usa para PNG.
    
4. [Katana](https://github.com/JohnHammond/katana) puede resolver este desafío:
    
    
     Objetivo completado en 2,57 segundos después de 14215 cajas unitarias 
     zsteg(/datos/objetivos/buildings.png) ➜
     picoCTF{h1d1ng_1n_th3_b1t5} - (copiado)
    
    
*Respuesta en el formato del concurso:*
picoCTF{h1d1ng_1n_th3_b1t5}