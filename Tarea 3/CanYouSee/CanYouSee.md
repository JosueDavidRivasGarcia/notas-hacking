## Reto: CanYouSee
### Descripción:
¿Qué tal un poco de escondite?Descarga este archivo [aquí](https://artifacts.picoctf.net/c_titan/130/unknown.zip).
### Solución
Primero descargamos el archivo:
```shell
wget https://artifacts.picoctf.net/c_titan/130/unknown.zip
```

Ahora descomprimimos el archivo `.zip`
```shell
unzip unknown.zip
```

Al ver que es una imagen `.jpg` procedemos a revisar los metadatos con `exiftool`:
```shell
exiftool ukn_reality.jpg
```

Y vemos que hay una cadena en base 64:
```
cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==
```

La convertimos:
```
 echo 'cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==' | base64 -d
```

Esto nos regresa la bandera:
```flag
picoCTF{ME74D47A_HIDD3N_6a9f5ac4}
```
### Notas adicionales
### Referencias

