## Reto: GET aHEAD
### Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)

### Solución
Usamos el comando `curl -I` para enviar una solicitud `HEAD` al servidor y obtener únicamente los encabezados HTTP sin descargar el cuerpo de la respuesta:

```bash
 curl -I http://mercury.picoctf.net:53554/
```

Al ejecutarlo , lo que nos muestra es lo siguiente:
```r
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
Content-type: text/html; charset=UTF-8
```

Como podemos observar, ya nos regresa la bandera.

```flag
 picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
```

### Notas adicionales
### Referencias

