## Reto: PW Crack 3
### Descripción
¿Puedes descifrar la contraseña para obtener la bandera?Descargue el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/16/level3.py) y lo harás necesito el cifrado [bandera](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) y el [hachís](https://artifacts.picoctf.net/c/16/level3.hash.bin) en el mismo directorio también.Hay 7 contraseñas potenciales con 1 siendo correcta. Puedes encontrarlos por examinar el script del verificador de contraseñas.
### Solución
- Descargamos los archivos
- Mostramos el código fuente del archivo `.py`
```
nano level3.py
```

Al ejecutar el comando, obtenemos la siguiente salida:
```salida
  GNU nano 8.2                                            level3.py                import hashlib

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()
    
def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)

    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password.
#   (Only 1 is correct)
pos_pw_list = [""6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]
```

Podemos observar en la siguiente lista, que aquí están las posibles contraseñas: `pos_pw_list = [""6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]`

Ejecutamos el programa y probamos la contraseña:
```python
python level3.py
```

Probamos alguna contrasena:
```salida
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
```

Afortunadamente al primer intento pudimos obtener la bandera:
```flag
picoCTF{m45h_fl1ng1ng_2b072a90}
```

### Notas adicionales
### Referencias

