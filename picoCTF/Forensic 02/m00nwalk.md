#### Descripción

Decodifica este [mensaje](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) desde la luna.

*Solución*

1. La pista sugiere que esto está relacionado con la forma en que las imágenes del alunizaje se transmitieron a la Tierra. Algunas investigaciones conducen a [la SSTV.](https://en.wikipedia.org/wiki/Slow-scan_television) Nota: Originalmente resolví este desafío usando [este programa para Windows](http://users.belgacom.net/hamradio/rxsstv.htm), pero desde entonces encontré una forma más fácil que funciona dentro de Kali Linux (ver siguiente paso).
    
2. [Este tutorial](https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04) ([Archivo](https://web.archive.org/web/20200602003341/https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04)) explica cómo convertir el archivo de audio en una imagen.
    
3. Instalar con qsstvapt-get install qsstv
    
4. Correr pactl load-module module-null-sink sink_name=virtual-cable
    
5. Correr. Aparecerá una GUI, vaya a la pestaña "Dispositivos de salida" para verificar que tiene el dispositivo "Salida nula".pavucontrol
    
6. Correr. Aparecerá la GUI del programa, vaya a "Opciones" > "Configuración" > "Sonido" y seleccione la interfaz de audio "PulseAudio"qsstv
    
7. De vuelta en la GUI, seleccione la pestaña "Grabación" y especifique que QSSTV debe capturar audio de la salida nula`pavucontrol`
    
8. La pista preguntaba "¿Cuál es la mascota de CMU?" - la respuesta es "Scotty the Scottie Dog". Esto insinuó que deberíamos seleccionar "Scottie 1" como el "Modo" de QSSTV. Seleccione "Inclinación automática" también.
    
9. Ejecute para crear la imagen: paplay -d virtual-cable message.wav!
    
10. Descargue el cable de audio virtual para que el audio se reproduzca normalmente:
    
    $ pactl list short modules | grep null
    25      module-null-sink        sink_name=virtual-cable
    $ pactl unload-module 25
    

*Respuesta en el formato del concurso:*
picoCTF{beep_boop_im_in_space}