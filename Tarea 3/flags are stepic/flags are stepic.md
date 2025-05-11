## Reto: flags are stepic
### Descripción:
Un grupo de hackers subterráneos podría estar usando este sitio legítimo para comunicarse. Usa tus técnicas forenses para descubrir su mensajePruébalo [aquí](http://standard-pizzas.picoctf.net:60238/)¡!
### Solución:
Primero iniciamos la instancia.
Ahora vamos a la pagina que nos proporcionan, al entrar vemos que hay un listado de banderas y en el código no se encuentra nada raro.
Ahora al ver la lista, encontramos un pais que no existe llamado `Upanzi, Republic The`, asi que descargamos la imagen.
```shell
wget http://standard-pizzas.picoctf.net:60238/flags/upz.png
```

Ahora procedemos a aplicar `stepic` como se llama el desafío, así que es la herramienta a utilizar.
```shell
stepic -i upz.png -d
```

Y al hacerlo nos regresa la bandera:
```flag
picoCTF{fl4g_h45_fl4g16aa94cf}
```


### Notas adicionales
### Referencias

