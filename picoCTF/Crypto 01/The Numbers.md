#### Descripción

Los [números](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... ¿Qué significan?

### Solución
La imagen muestra un montón de números alineados en el siguiente formato:

```
16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 } 
```

El número anterior está encriptado mediante un [cifrado de sustitución](https://www.dcode.fr/letter-number-cipher) basado en el número de letra (A1Z26) A = 1, B = 2, C = 3.....

> 16 9 3 15 3 20 6 => PICOCTF

> 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 => LOS NÚMEROSMASON

### Bandera

`PICOCTF{THENUMBERSMASON}`