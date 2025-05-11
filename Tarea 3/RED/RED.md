## Reto: RED
### Descripción:
RED, RED, RED, REDDownload the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)
### Solución
Descargamos la imagen:
```shell
wget https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png
```

Usamos el comando `strings` para ver si nos ayuda:
```shell
strings red.png
```

Vemos que al inicio de la cadena aparece `CHECKLSB` por lo que lo hacemos con `zteg`:
```shell
zteg -a red.png
```

Y vemos que hay una cadena en base64, asi que la convertimos:
```
cho "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d
```

Y nos regresa la bandera:
```flag
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```
### Notas adicionales
### Referencias

