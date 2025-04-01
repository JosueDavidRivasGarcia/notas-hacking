## Reto:  Irish-Name-Repo 1
### Descripción
Hay un sitio web corriendo en `https://jupiter.challenges.picoctf.org/problem/50009/` ([enlace](https://jupiter.challenges.picoctf.org/problem/50009/)) o http://jupiter.challenges.picoctf.org:50009. ¿Crees que puedes iniciar sesión? ¡Intenta ver si puedes iniciar sesión!
### Solución
Ingresamos a la pagina, después de eso podemos ver que hay 3 apartados en la barra de menú, la cual una de ellas nos permite loguearnos, al inspeccionar la pagina de `support` vemos que hay un apartado que indica que da un error `SQL`, por lo que la pagina no puede estar bien protegida, asi que hacemos lo siguiente.

Ingresamos a la pagina de `login`:
En el apartado de `username` ingresamos lo siguiente:
```username
' OR 1=1 --
```

A esto se le conoce como `payload`. El `' OR 1=1 --` es un **ataque de inyección SQL** diseñado para evadir autenticación en sistemas vulnerables.
El `OR 1=1` hace que la condición siempre sea verdadera, devolviendo todos los usuarios de la tabla.

En el apartado de `password` no ingreses nada o ingresa lo que sea y presiona `login`.

Esto nos devuelve la bandera:
```flag
picoCTF{s0m3_SQL_fb3fe2ad}
```

### Notas adicionales
### Referencias

