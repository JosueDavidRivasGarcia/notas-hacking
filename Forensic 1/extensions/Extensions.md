4## Reto: Extensions
### Descripción
Este es un archivo de texto realmente extraño [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)¿? ¿Puedes encontrar la bandera?
### Solución
Como primera pista dice que el archivo `TXT` esta algo extraño, así que analizaremos su contenido.

- Descargamos el archivo
```shell
wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
```
- Con el comando `cat` vemos el contenido.
```shell
cat flag.txt
```
Vemos que su contenido en verdad es extraño, sus caracteres no se reconocen.
- Comprobamos si realmente es un archivo `txt` con el comando `file`
```shell
file flag.txt
```
Y nos muestra lo siguiente:
```shell
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
```
Podemos observar que en realidad es un archivo `png`.
- Con el comando `mv` cambiamos la extensión del archivo.
```shell
mv flag.txt flag.png
```
Al abrir la imagen, podemos observar que se encuentra la bandera
```flag
picoCTF{now_you_know_about_extensions}
```

### Notas adicionales
### Referencias

