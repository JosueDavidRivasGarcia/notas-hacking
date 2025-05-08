## Reto: Operation Oni
### Descripción:
Descargue esta imagen de disco, busque la clave e inicie sesión en la máquina remota.Nota: si está utilizando el webshell, descargue y extraiga la imagen del disco `/tmp` no es su directorio de inicio.

- [Descargar imagen de disco](https://artifacts.picoctf.net/c/70/disk.img.gz)
- Máquina remota: `ssh -i key_file -p 58625 ctf-player@saturn.picoctf.net`
### Solución:
Primero descargamos la imagen.
```shell
wget https://artifacts.picoctf.net/c/70/disk.img.gz
```

Ahora descomprimimos el archivo:
```shell
gzip disk.img.gz
```

Vemos las particiones existentes:
```shell
mmls disk.img
```

Estas son las particiones:
```q
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
```

Los archivos se encuentran en la ultima partición, por lo que listamos los archivos:
```shell
fls -o 206848 disk.img
```

Vamos a abrir ahora un archivo shh, para poder ingresar de acceso remoto.
```shell
fls -o 206848 disk.img 470
```

Ahora abrimos el archivo:
```shell
fls -o 206848 disk.img 3916
```

Mandamos el archivo al nombre con el que ingresamos:
```shell
icat -o 206848 disk.img 2345 > key_file
```

Con el siguiente comando ingresamos:
```shell
cp key_file ~/.ssh/key_file
chmod 400 ~/.ssh/key_file
ssh -i ~/.ssh/key_file -p 57772 ctf-player@saturn.picoctf.net
```

Una vez que ingresamos, listamos los archivos:
```shell
ls
```

Y hacemos un `cat` para regresar la bandera:
```flag
picoCTF{k3y_5l3u7h_b5066e83}
```

### Notas adicionales
### Referencias

