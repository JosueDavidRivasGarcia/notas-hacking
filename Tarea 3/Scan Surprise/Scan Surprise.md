## Reto: Scan Surprise
### Descripción:
Me he aburrido de entregar banderas como texto. ¿No sería genial si fueran una imagen?Puede descargar los archivos de desafío aquí:

- [desafío.zip](https://artifacts.picoctf.net/c_atlas/3/challenge.zip)

Los mismos archivos son accesibles a través de SSH aquí:`ssh -p 58899 ctf-player@atlas.picoctf.net`Usando la contraseña `6dd28e9b`. Acepta la huella digital con `yes`, y `ls` una vez conectado para comenzar. ¡Recuerde, en un shell, las contraseñas están ocultas!
### Solución
Descargamos el archivo:
```shell
wget https://artifacts.picoctf.net/c_atlas/3/challenge.zip
```

Ahora descomprimimos el archivo:
```shell
unzip challenge.zip
```

Ahora buscamos en los archivos:
```shell
cd home
cd ctf-player/
cd drop-in/
```

Ahora encontramos una imagen llamada `flag.png` pero al abrirla es un QR, asi que usamos la herramienta `zbar:
```shell
 zbarimg flag.png
```

y nos devuelve la bandera:
```flag
picoCTF{p33k_@_b00_a81f0a35}
```

### Notas adicionales
### Referencias

