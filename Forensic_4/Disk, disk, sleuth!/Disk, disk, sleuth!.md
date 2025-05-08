## Reto: Disk, disk, sleuth!
### Descripción
Utilice issrch_stringsr de la sleuthkit y algunos terminal-fu para encontrar una bandera en esta imagen de disco: [dds1-alpina.flag.img.gz](https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz)
### Solución
Primero descargamos el archivo
```shell
 wget https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz
```

Ya que descargamos el archivo, vemos que tipo de archivo es:
```shell
file dds1-alpine.flag.img.gz
```

Al ser un archivo comprido, procedemos a descomprimirlo con:
```
 unzip dds1-alpine.flag.img
```

Vamos que dentro hay una imagen, asi que con `strings` vamos a buscar la bandera.
```shell
strings dds1-alpine.flag.img | grep picoCTF{.*}
```

Y nos regresa la bandera:
```flag
picoCTF{f0r3ns1c4t0r_n30phyt3_a69a712c}
```
### Notas adicionales
### Referencias

