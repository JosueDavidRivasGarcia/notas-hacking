## Reto: PW Crack 2
### Descripción
¿Puedes descifrar la contraseña para obtener la bandera?Descargue el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/14/level2.py) y lo harás necesito el cifrado [bandera](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) en el mismo directorio también.

### Solución
- Descargamos los archivos
- Mostramos el contenido del archivo `.py` con el comando `nano`
```
nano level2.py
```
Nos da la siguiente salida
```salida
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
```
Podemos ver que la contraseña esta cifrada con python por lo que procedemos a convertirlo:
- Abrimos python3
- Escribimos lo que esta en `if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) )` para convertirlo.
```python
python3
```
 Ahora ponemos la conversión:
```python
chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
```
Y nos da la siguiente salida:
```salida
4ec9
```
Esa es la contraseña.

Ejecutamos el programa
```python
 python3 level2.py
```

La salida es la siguiente
```salida
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
```

Y obtenemos la bandera
```flag
picoCTF{tr45h_51ng1ng_9701e681}
```

### Notas adicionales
### Referencias

