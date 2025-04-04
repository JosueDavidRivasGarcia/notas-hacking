## Reto: Roboto Sans
### Descripción
La bandera está en algún lugar de esta aplicación web, no necesariamente en el sitio web. Encuéntralo.Comprobar [esto](http://saturn.picoctf.net:59922/) fuera.
### Solución
Entramos a la pagina que nos proporciona la plataforma y al estar hablando de robots, agregamos a la busqueda el archivo `robots.txt` y vemos que nos muestra lo siguiente.
```http
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```
Vemos que las 3 lineas estan en base 64, por lo que al pasarlas por el cyberchef encontramos la siguiente extension
```http
js/myfile.txt
```
Al adjuntarlo a la direccion original encontramos la bandera.
```flag
picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}
```

### Notas adicionales
### Referencias

