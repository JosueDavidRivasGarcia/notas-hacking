## Reto: First Grep
### Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.
### Solución
El nombre del ejercicio se llama mi primer grep, el cual es un comando que nos sirve para buscar e identificar caracteres.
El ejercicio nos proporciona un archivo en el cual esta oculta la bandera. Hay que recordar que las banderas inician siempre con picoCTF{}, por lo que ejecutamos el comando:

```
grep -r "pico" [ruta]
```

Y de inmediato nos da la bandera:
```
┌──(hackerjos㉿Joshue)-[~]
└─$ grep -r "pico" /mnt/c/Users/josue/Downloads/file
picoCTF{grep_is_good_to_find_things_5af9d829}
```

### Notas adicionales
**`-r`**: Busca recursivamente en subdirectorios
### Referencias
A, D. (2020, 15 octubre). Base64, codificación y decodificación desde la línea de comandos. _Ubunlog_. https://ubunlog.com/base64-codificacion-decodificacion-terminal/