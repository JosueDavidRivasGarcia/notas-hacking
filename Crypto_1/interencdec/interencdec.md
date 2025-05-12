## Reto: interencdec
### Descripción
uede obtener el significado real de este archivo.Descarga el archivo [aquí](https://artifacts.picoctf.net/c_titan/2/enc_flag).
### Solución
Descargamos el archivo:
```shell
wget https://artifacts.picoctf.net/c_titan/2/enc_flag
```

Hacemos un `cat:`
```shell
cat enc_flag
```

Y nos muestra esto:
```
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg==
```

Vamos al cyberchef y aplicamos base 64, la cual nos regresa lo siguiente:
```
d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ==
```

Volvemos a aplicar base64 y este es el resultado:
```shell
wpjvJAM{jhlzhy_k3jy9wa3k_78250hmj}
```

Ahora aplicamos ROT19 y nos regresa la bandera:
```
picoCTF{caesar_d3cr9pt3d_78250afc}
```



### Notas adicionales
### Referencias

