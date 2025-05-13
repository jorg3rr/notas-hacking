#### Description

A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their messageTry it [here](http://standard-pizzas.picoctf.net:55924/)!
# Solución

Una vez que inicie la instancia, puede ir a y si se desplaza por las "Banderas de países", se encontrará con "Upanzi, Republic The" y verá la imagen que dice Upanzi Network, que obviamente no es una bandera de país. La Red Upanzi es parte de CyLab-Africa.http://standard-pizzas.picoctf.net:56409/

También puede usar curl, wget o simplemente mirar a través de la fuente para ver la lista de países en html. Por ejemplo curl http://standard-pizzas.picoctf.net:56409/ > index.html

Esta es la línea de interés:

{ name: "Upanzi, Republic The",img: "flags/upz.png", style:"width: 120px!important; height: 90px!important;" },

Puede ver que tiene upz.png que se puede consultar y descargar con el siguiente comando: wget http://standard-pizzas.picoctf.net:56409/flags/upz.png

Si lo necesitas, puedes configurar un entorno virtual con python con los siguientes comandos: y luego .python3 -m venv venvsource venv/bin/activate

Una vez hecho esto, puede instalar el paquete stepic con pip: pip install stepic

Por último, ejecútelo con el indicador de decodificación. Otro método podría ser usar apt install para obtener el paquete: sudo apt install stepic

Utilice este comando para obtener la bandera: stepic -i upz.png -d

Bandera
picoCTF{fl4g_h45_fl4g1a2a9157}