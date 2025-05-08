## Reto: Operation Orchid

### Descripción:
Descargue esta imagen de disco y encuentre la bandera.Nota: si está utilizando el webshell, descargue y extraiga la imagen del disco `/tmp` no es su directorio de inicio.

- [Descargar imagen de disco comprimido](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
### Solución
Primero descargamos la imagen:
```shell
wget https://artifacts.picoctf.net/c/213/disk.flag.img.gz
```

Ahora descomprimimos el archivo:
```shell
gzip -d disk.flag.img.gz
```

Mostramos las particiones que hay:
```shell
mmls disk.flag.img
```

Vemos que los archivos están en la ultima partición, así que buscamos el archivo.
```shell
fls disk.flag.img -o 411648 -r | grep flag
```

Vemos que el archivo esta encriptado, pero podemos ver los comandos anteriores, así que lo invertimos y desencriptamos para ver el archivo:
- Primero lo mandamos a un archivo:
```shell
icat disk.flag.img -o 411648 1782 > flag.txt.enc
```

- Ahora lo desencriptamos invirtiendo el programa:
```shell
openssl aes256 -salt -out flag.txt -in flag.txt.enc -k unbreakablepassword1234567 -d
```

Ahora solo hacemos un `cat` en el archivo de la bandera:
```shell
cat flag.txt
```

Y nos regresa la bandera:
```flag
picoCTF{h4un71ng_p457_5113beab}
```

### Notas adicionales
### Referencias

