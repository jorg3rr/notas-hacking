### Descripción

En RSA, un valor pequeño puede ser problemático, pero ¿qué pasa con ? ¿Puedes descifrar esto? [valores](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)`e``N`

## Solución
`n` es pequeño y se puede tener en cuenta y:`p``q`

```python
from factordb.factordb import FactorDB
import gmpy2

c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684
n = 631371953793368771804570727896887140714495090919073481680274581226742748040342637
e = 65537

f = FactorDB(n)
f.connect()
p, q = f.get_factor_list()
ph = (p-1)*(q-1)
d = gmpy2.invert(e, ph)
plaintext = pow(c, d, n)
print("Flag: {}".format(bytearray.fromhex(format(plaintext, 'x')).decode()))
```

Salida:

```shell
C:\Users\jorg3\Downloads>python solve.py
Flag: picoCTF{sma11_N_n0_g0od_55304594}
```
### Bandera
picoCTF{sma11_N_n0_g0od_55304594}
