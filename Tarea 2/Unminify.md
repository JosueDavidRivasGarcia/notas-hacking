## Reto: Unminify
### Descripción
No me gusta desplazarme hacia abajo para leer el código de mi sitio web, así que lo he aplastado. ¡Como beneficio adicional, mis páginas se cargan más rápido!Navegar [aquí](http://titan.picoctf.net:54554/)¡y encuentra la bandera!
### Solución
Vemos que el código es demasiado largo, así que en la terminal de `kali`, hacemos un `curl` buscando la bandera.
```shell
curl -s http://titan.picoctf.net:54554 | grep picoCTF{.*}
```
Y esto nos regresa fácilmente la bandera:
```flag
picoCTF{pr3tty_c0d3_51d374f0}
```


### Notas adicionales
### Referencias

