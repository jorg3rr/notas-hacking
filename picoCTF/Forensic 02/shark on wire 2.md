#### Descripción

Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recupere la marca que se robó de la red.

### Solución

1. Abra el archivo ".pcap" en wireshark.
    
2. Dado que el desafío anterior consistía en seguir el flujo UDP, ese es el primer paso que debemos dar para resolver esto. Vaya a y haga clic en las transmisiones.`Analyze -> Follow -> UDP Stream`
    
3. Una secuencia tiene un mensaje etiquetado como start y las siguientes secuencias son todas cadenas de varias longitudes que contienen el carácter "a".
    
4. Mirando en la columna de información, podemos ver que todas las solicitudes provienen de diferentes puertos de la misma IP.
    
5. Filtrar la IP: `ip.src == 10.0.0.66`
    
6. Podemos ver que el segundo mensaje se origina en el puerto de origen 5112. 112 es un número que debería alertarnos, ya que su representación ASCII es , que coincide con la plantilla de bandera.`p`
    
7. Ejecute el [script.py](https://github.com/HHousen/PicoCTF-2019/tree/24b0981c72638c12f9a8572f81e1abbcf8de306d/Forensics/shark%20on%20wire%202/script.py) para tomar todos los números de puerto y convertirlos a ASCII, que es la bandera.
    

### Bandera

`picoCTF{p1LLf3r3d_data_v1a_st3g0}`