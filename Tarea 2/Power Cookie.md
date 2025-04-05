## Reto: Power Cookie
### Descripción
¿Puedes conseguir la bandera?Ve a esto [sitio web](http://saturn.picoctf.net:49871/) y mira lo que puedes descubrir
### Solución
Inicié la página proporcionada, la cuál tiene un botón para entrar como *Guest*, sin embargo al ingresar como Guest, se muestra lo siguiente:
```
We apologize, but we have no guest services at the moment.
```

Por lo que abrimos nuestra herramienta de `Cookie editor`, la cual nos muestra una Cookie llamada isAdmin que tiene un valor de 0, cambiamos su valor a 1 (True) para logearnos como admin dado que no existen servicios para un invitado.

Al recargar la pagina, nos arroja la bandera:
```flag
picoCTF{gr4d3_A_c00k13_65fd1e1a}
```
### Notas adicionales
### Referencias

