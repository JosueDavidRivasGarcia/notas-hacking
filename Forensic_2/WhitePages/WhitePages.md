## Reto: WhitePages
### Descripción
Dejé de usar YellowPages y me mudé a WhitePages.. [la página que me dieron](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) ¡está todo en blanco!
### Solución
Descargamos el archivo:
```shell
 wget https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
```

Al ver que tipo de archivo es con el siguiente comando, podemos ver que es un archivo de tipo UNICODE UTF-8.
```shell
file whitepages.txt
```

Ahora creamos el siguiente `script`:
```python
from pwn import *

file = open('whitepages.txt','rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)
print(data)
```

Este script **lee un archivo lleno de espacios raros**, interpreta esos espacios como **0s** y **1s**, **los reconstruye en datos binarios**, y luego **muestra el mensaje oculto**.

Y al ejecutarlo obtenemos la bandera:
```flag
picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}
```

### Notas adicionales
### Referencias

 
