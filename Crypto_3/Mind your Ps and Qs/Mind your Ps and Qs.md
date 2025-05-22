## Reto: Mind your Ps and Qs
---
### Descripción:
En RSA, un pequeño `e` el valor puede ser problemático, pero ¿qué pasa `N`¿? ¿Puedes descifrar esto? [valores](https://mercury.picoctf.net/static/3cfeb09681369c26e3f19d886bc1e5d9/values)

---
### Solución:
Primero descargamos el archivo:
```shell
wget https://mercury.picoctf.net/static/3cfeb09681369c26e3f19d886bc1e5d9/values
```

Vemos el contenido del archivo:
```shell
cat values
```

Y nos devuelve los valores de c, n y e:
```python
c: 8533139361076999596208540806559574687666062896040360148742851107661304651861689
n: 769457290801263793712740792519696786147248001937382943813345728685422050738403253
e: 65537
```

Hacemos el siguiente `script` para obtener la bandera:
```Python
c = 8533139361076999596208540806559574687666062896040360148742851107661304651861689
n = 769457290801263793712740792519696786147248001937382943813345728685422050738403253
e = 65537
p = 1617549722683965197900599011412144490161 
q = 475693130177488446807040098678772442581573
tn = (p-1) * (q-1)
d = pow(e, -1, tn)
m = pow(c, d, n)
bytes.fromhex(hex(m)[2:])
```

Y nos regresa la bandera:
```flag
picoCTF{sma11_N_n0_g0od_45369387}
```

---
### Notas adicionales

---
### Referencias

