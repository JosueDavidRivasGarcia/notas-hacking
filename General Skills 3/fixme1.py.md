## Reto
### Descripción
Corregir el error de sintaxis en este script de Python para imprimir la bandera.[Descargar script de Python](https://artifacts.picoctf.net/c/27/fixme1.py)

## Solución
- Descargamos el archivo adjunto
- Una vez descargado, ejecutamos el programa
```python
python3 fixme1.py
```

Podemos observar que existe un error en la línea 20, por una mala identación.
```salida
  File "/mnt/c/users/josue/downloads/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
```

Con el comando `nano`, podemos entrar a modificar el código del programa.
```
nano fixme1.py
```

Una vez dentro, identificamos el error y lo corregimos
```python
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + >

flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)

```

La corrección fue eliminar 2 espacios de mas que se encontraban en la ultima línea de código.

Una vez realizada la corrección, procedemos a guardar los cambios con `ctrl + o`, presionamos `enter`, para guardarlo con ese nombre y posteriormente `ctrl + x` para salir.

Al volver a ejecutar el programa, nos da la bandera
```flag
picoCTF{1nd3nt1ty_cr1515_182342f7}
```

### Notas adicionales
### Referencias

