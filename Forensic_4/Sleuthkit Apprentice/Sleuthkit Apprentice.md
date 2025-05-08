## Reto: Sleuthkit Apprentice
### Descripción:
Descargue esta imagen de disco y encuentre la bandera.Nota: si está utilizando el webshell, descargue y extraiga la imagen del disco `/tmp` no es su directorio de inicio.

- [Descargar imagen de disco comprimido](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)
### Solución:

Primero descargamos la imagen:
```shell
wget https://artifacts.picoctf.net/c/138/disk.flag.img.gz
```

Ahora descomprimimos la imagen:
```shell
 gzip -d disk.flag.img.gz
```

Vemos las particiones:
```shell
mmls disk.flag.img
```

Ahora buscamos el archivo de la bandera:
```shell
fls disk.flag.img -o 360448 -r | grep flag
```

Hacemos un `cat` en el archivo y nos regresa la bandera:
```flag
picoCTF{by73_5urf3r_2f22df38}
```


### Notas adicionales
### Referencias

