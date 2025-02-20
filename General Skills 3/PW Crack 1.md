## Reto: PW Crack 1
### Descripción
¿Puedes descifrar la contraseña para obtener la bandera? Descargue el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/12/level1.py) y lo harás necesito el cifrado [bandera](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) en lo mismo directorio también.
### Solución
- Descargamos los archivos
- Ahora mostramos el contenido del archivo `level1.flag.txt.enc`
```
cat level1.flag.txt.enc
```
La salida que nos muestra es algo confusa
```salida
[gE]__TgS^S

           J
```
Esa será la contraseña? 
- Ejecutamos el programa
```python
 python3 level1.py
```
Nos muestra la siguiente salida
```salida
Please enter correct password for flag:
```

Lo que pensamos que era la contraseña **`No es correcta`
Y que tal si vemos el contenido del archivo `.py` con el comando `nano`
```
nano level1.py
```
Al ejecutarlo nos muestra el código fuente del programa:
```
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
```

Podemos observar que nos esta mostrando la contraseña a simple vista en la condición `if (user_pw == "8713")` por lo que la contraseña es `8713`.

Al poner la contraseña  nos da la bandera
```salida
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
```

Por lo tanto la bandera es:
```flag
picoCTF{545h_r1ng1ng_1b2fd683}
```
### Notas adicionales
### Referencias

