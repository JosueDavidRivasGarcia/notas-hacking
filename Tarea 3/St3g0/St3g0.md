## Reto: St3g0
### Descripción:
Descarga esta imagen y encuentra la bandera.

- [Descargar imagen](https://artifacts.picoctf.net/c/216/pico.flag.png)
### Solución

Descargamos la imagen:
```shell
wget https://artifacts.picoctf.net/c/216/pico.flag.png
```

Aplicamos zsteg:
```shell
zsteg -a pico.flag.png
```

Y nos devuelve la bandera:
```flag
picoCTF{7h3r3_15_n0_5p00n_a1062667}
```
### Notas adicionales
### Referencias

