#### Descripción

¿Puedes ganar de manera convincente contra este bot de ajedrez? ¡No será fácil contigo!Puedes encontrar el reto [aquí](http://verbal-sleep.picoctf.net:51112/).

### Solución
Intentemos enviar algunos mensajes al servidor usando Developer Tools. Haga clic con el botón derecho y seleccione inspeccionar, o presione F12. Seleccione la pestaña de la consola.

Sabemos que el mensaje debe tener el formato "eval/mate [entero]". Empecemos por algo sencillo.

¡Enviando "eval 0" se actualizó el chatbox! Ahora que sabemos que esto funciona, intentemos decirle al servidor que Stockfish está a punto de perder.

Aquí vamos. Dado que la posición se evalúa desde la perspectiva de Stockfish, cuando la evaluación es positiva, Stockfish está ganando.

El servidor siguió enviando el mismo mensaje que cuando gané legalmente. Intentemos otra cosa.
Nada...
De acuerdo... Intentemos con un número mayor.

¡Ajá! ¡Eso funcionó! Decirle al servidor que Stockfish estaba perdiendo por -100,000 hizo que renunciara y nos diera la bandera.

### Bandera
picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_9b154ed7}