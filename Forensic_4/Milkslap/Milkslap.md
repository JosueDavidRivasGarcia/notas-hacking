## Reto:
### Descripción
[🥛](http://mercury.picoctf.net:16940/)
### Solución
Primero descargamos la imagen:
```shell
wget http://mercury.picoctf.net:16940/concat_v.png
```

Ahora utilizaremos la herramienta `zsteg` para ver los datos de la imagen:
```
zsteg -s all concat_v.png
```

y nos regresa la bandera:
```flag
picoCTF{imag3_m4n1pul4t10n_sl4p5}
```
### Notas adicionales
### Referencias

