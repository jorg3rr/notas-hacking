#### Descripción

Hicimos muchas sustituciones para cifrar esto. ¿Se puede descifrar? Conéctese con .`nc jupiter.challenges.picoctf.org 39894`


### Solución

El texto cifrado proporcionado se muestra a continuación. Aparentemente, está codificado por encriptación de cifrado de sustitución. Para resolver esto, puede ser fácilmente la fuerza bruta mediante el uso de herramientas en línea como [esta](https://www.guballa.de/substitution-solver) o [esta](https://planetcalc.com/8047/).

### Texto cifrado

```
-------------------------------------------------------------------------------
vhweytfl bjyj ql ghxy sote - syjrxjwvg_ql_v_hpjy_otikmt_powbwtllfi 
-------------------------------------------------------------------------------
nj njyj whf ixvb ihyj fbtw t rxtyfjy hs tw bhxy hxf hs hxy lbqu fqoo nj ltn bjy lqwa, 
twm fbjw q xwmjylfhhm shy fbj sqylf fqij nbtf ntl ijtwf kg t lbqu shxwmjyqwe qw fbj ljt.  
q ixlf tvawhnojmej q btm btymog jgjl fh ohha xu nbjw fbj ljtijw fhom ij lbj ntl lqwaqwe; 
shy syhi fbj ihijwf fbtf fbjg ytfbjy uxf ij qwfh fbj khtf fbtw fbtf q iqebf kj ltqm fh eh qw, 
ig bjtyf ntl, tl qf njyj, mjtm nqfbqw ij, utyfog nqfb syqebf, utyfog nqfb bhyyhy hs iqwm, 
twm fbj fbhxebfl hs nbtf ntl gjf kjshyj ij.
```

### Clave de cifrado Fuerza bruta

> Este texto claro ... abcdefghijklmnopqrstuvwxyz

> se asigna a este texto cifrado... **`tkvmjsebqcaoiwhurylfxpnzgd`(Key)**

### Texto sin formato

```
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_vlnhnasstm 
-------------------------------------------------------------------------------
we were not much more than a quarter of an hour out of our ship till we saw her sink, 
and then i understood for the first time what was meant by a ship foundering in the sea.  
i must acknowledge i had hardly eyes to look up when the seamen told me she was sinking; 
for from the moment that they rather put me into the boat than that i might be said to go in, 
my heart was, as it were, dead within me, partly with fright, partly with horror of mind, 
and the thoughts of what was yet before me.
```

### Bandera
Nota: La bandera se debe de ingresar en el siguiente formato en la pagina de picoCTF:

frequency_is_c_over_lambda_agflcgtyue
