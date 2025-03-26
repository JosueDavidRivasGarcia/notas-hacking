## Reto: dont-use-client-side
### Descripción
¿Puedes entrar en este portal súper seguro? `https://jupiter.challenges.picoctf.org/problem/29835/` ([enlace](https://jupiter.challenges.picoctf.org/problem/29835/)) o http://jupiter.challenges.picoctf.org:29835
### Solución
Al entrar a la pagina que nos proporciona PicoCTF, nos encontramos a una pagina en la cual nos pide una contraseña para poder ingresar.
Para inspeccionar un poco mas, tecleamos click derecho y después ver código fuente.
Al ver el codigo fuente a simple vista podemos ver que ahi se encuentra la bandera:

```js
if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
```

Podemos ver que el orden de la bandera se encuentra en esta funcion, además esta organizada de manera numérica.

Al final la bandera seria:

```flag
picoCTF{no_clients_plz_7723ce}
```

### Notas adicionales
### Referencias

