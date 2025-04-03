#### Descripción

Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recupera la bandera.

Solución

1. Abra el archivo ".pcap" en wireshark.
    
2. Filtre las transmisiones UDP, ya que había una pista sobre las transmisiones.
    
3. Aplique el filtro y, a continuación, haga clic con el botón derecho en un paquete, seleccione seguir y, a continuación, siga udp.udp.stream eq 6
    


picoCTF{StaT31355_636f6e6e}