#### Descripción

¿Por qué buscar la bandera cuando puedo hacer un bookmarklet para imprimirla por mí?¡Navega [aquí](http://titan.picoctf.net:49488/) y encuentra la bandera!

### Solución
Copiamos el codigo del sitio Web:
javascript:(function() {  
 var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓ¨ÍÕÄ¦í";  
 var key = "picoctf";  
 var decryptedFlag = "";  
 for (var i = 0; i < encryptedFlag.length; i++) {  
 decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);  
 }  
 alert(decryptedFlag);  
})();

Procedemos pegando este código en la consola y ejecutándolo. Como resultado, la bandera se revela con éxito:

> `picoCTF{p@g3_turn3r_6bbf8953}`

