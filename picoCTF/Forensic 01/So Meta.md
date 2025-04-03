#### Descripción

Encuentra la bandera en esta [imagen](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png)

### Solución

1. La bandera está oculta en los datos EXIF de la imagen. Uso y :exiftoolgrep
    
     $ exiftool pico_img.png
    
*Respuesta en el formato del concurso:*
picoCTF{s0_m3ta_d8944929}


