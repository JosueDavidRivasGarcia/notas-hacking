## Reto
### Descripción
Descargue la imagen del disco y use `mmls` en él para encontrar el tamaño del Linux partición. Conéctese al servicio de control remoto para verificar su respuesta y obtener la bandera.Nota: si está utilizando el webshell, descargue y extraiga la imagen del disco `/tmp` no es su directorio de inicio.[Descargar imagen de disco](https://artifacts.picoctf.net/c/164/disk.img.gz)Programa de verificación de acceso: `nc saturn.picoctf.net 49823`
### Solución
Primero descargamos la imagen:
```shell
 wget https://artifacts.picoctf.net/c/164/disk.img.gz
```

Ahora descomprimimos el archivo:
```shell
gzip -d disk.img.gz
```

Vemos las particiones que hay:
```shell
mmls disk.img
```

Entramos al servidor remoto:
```shell
nc saturn.picoctf.net 49823
```

Y nos pregunta por la longitud, al contestar, es lo que hay en la ultima partición:
```c
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
```

y nos regresa la bandera:
```flag
picoCTF{mm15_f7w!}
```

### Notas adicionales
### Referencias

