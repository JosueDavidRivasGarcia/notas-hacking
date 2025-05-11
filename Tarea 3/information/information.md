## Reto: information
### Descripción
Los archivos siempre se pueden cambiar de forma secreta. ¿Puedes encontrar la bandera? [gato.jpg](https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg)
### Solución
Descargamos la imagen:
```shell
wget https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg
```

Vemos los metadatos:
```shell
exiftool cat.jpg
```

Vemos una cadena en base 64 que procedemos a convertir:
```shell
echo 'cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9' | base64 -d
```

Y nos devuelve la bandera:
```flag
picoCTF{the_m3tadata_1s_modified}
```


### Notas adicionales
### Referencias

