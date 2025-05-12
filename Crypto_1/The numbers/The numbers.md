## Reto: Th3 numbers
### Descripción:
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
### Solución
Descargamos el archivo:
```shell
wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
```

Ahora al abrir la imagen encontramos esto:
```
16 9 3 15 3 20 6 { 20 8 5
14 21 13 2 2 5 18 19 13 1
19 15 14 }
```

Vamos al cyberchef y le decimos `A1Z26 Cipher Decode` y nos devuelve la bandera:
```flag
picoCTF{thenumbersmason}
```

### Notas adicionales
### Referencias

