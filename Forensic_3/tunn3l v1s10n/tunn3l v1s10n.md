## Reto: tunn3l v1s10n
### Descripción
We found this [file](https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n). Recover the flag.
### Solución
Descargamos el archivo
Preguntamos su tipo y son datos, la pista nos dice que esta algo ofuscado y no se puede desplegar, tentativamente es un `bmp`.

Veamos el enncabezado:
```shell
xxd tunn3l v1s10n | head
```

Es un archivo creado en windows, para nuestro caso.
Por lo tanto el encabezado es de 40 bytes en hexadecimal es 28, pero antes cambiamos la extension.

```shell
mv tunn3l_v1s10n tunn3l_v1s10n.bmp
```

Al querer abrirlo no lo hace, tal como lo dice la pista y abrimos el editor hexadecimal.
```shell
hexeditor tunn3l_v1s10n.bmp
```

El tamano del encabezado debe ser de 40 bytes.
Vamos a la posición 0E y 0A, tenemos que corregir los valores.

Al salir, abre la bandera pero no habre, con exiftool vamos a ver los metadatos y vemos que el ato de la imagen esta algo limitado. Asi que volvemos a entrar al editor hexadecimal.
```shell
hexeditor tunn3l_v1s10n.bmp
```

Vamos a localizar en que parte esta el tamano, esta en el offset 12, y el alto en el offset 16, en este offset le pondremos mas valor (40 04) para cambiar el alto de la imagen.
Y nos regresa la bandera:
```flag
picoCTF{qu1t3_a_v13w_2020}
```


### Notas adicionales
### Referencias

