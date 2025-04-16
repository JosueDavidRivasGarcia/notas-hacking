## Reto: findme
### Descripción
Ayúdenos a probar el formulario enviando el nombre de usuario como `test` y contraseña como `test!`El sitio web en ejecución [aquí](http://saturn.picoctf.net:60524/).
### Solución
Iniciamos visitando el sitio web haciendo clic en el enlace proporcionado en la descripción del reto.

Entonces abrimos la herramienta Burp y ponemos a funcionar el proxy para atrapar los encabezados HTML, de ahí se destacan un GET y un POST, en el caso del GET tenemos que:
```html
HTTP/1.1 302 Found
X-Powered-By: Express
Location: /next-page/id=cGljb0NURntwcm94aWVzX2Fs
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 120
Date: Wed, 16 Apr 2025 01:21:26 GMT
Connection: keep-alive
Keep-Alive: timeout=5

<p>Found. Redirecting to <a href="/next-page/id=cGljb0NURntwcm94aWVzX2Fs">/next-page/id=cGljb0NURntwcm94aWVzX2Fs</a></p>
```

Y en el caso del POST, tenemos lo siguiente:
```html
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 264
ETag: W/"108-/7O7VTeecocneZ8ZrGW1rxPrD4s"
Date: Wed, 16 Apr 2025 01:23:08 GMT
Connection: keep-alive
Keep-Alive: timeout=5

<!DOCTYPE html>
<head>
    <title>flag</title>
</head>
<body>
    <script>
        setTimeout(function () {
           // after 2 seconds
           window.location = "/next-page/id=bF90aGVfd2F5XzAxZTc0OGRifQ==";
        }, 0.5)
      </script>
    <p></p>
</body>
```

Por lo que se puede ver, estas dos códigos contienen en el apartado de id una cadena codificada en base64, procedemos a juntar las dos partes.

Y obtenemos la bandera:
```
picoCTF{proxies_all_the_way_01e748db}
```

### Notas adicionales
### Referencias

 
