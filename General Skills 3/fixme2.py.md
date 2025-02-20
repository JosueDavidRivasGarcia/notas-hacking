## Reto: fixme2.py
### Descripción
Corregir el error de sintaxis en el script de Python para imprimir el indicador.[Descargar script de Python](https://artifacts.picoctf.net/c/5/fixme2.py)
### Solución
- Descargamos el archivo adjunto
- Una vez descargado, ejecutamos el programa
```python
python3 fixme1.py
```

Podemos observar a la salida que hay un error de sintaxys
```salida
File "/mnt/c/users/josue/downloads/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

Podemos notar que la existe un error al momento de comparar.

Con el comando `nano`, podemos entrar a modificar el código del programa.
```
nano fixme2.py
```

Una vez dentro, identificamos el error y lo corregimos:
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


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + >

flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)

```

Una vez realizada la corrección, procedemos a guardar los cambios con `ctrl + o`, presionamos `enter`, para guardarlo con ese nombre y posteriormente `ctrl + x` para salir.

Al volver a ejecutar el programa, nos da la bandera
```flag
 picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

### Notas adicionales
### Referencias

