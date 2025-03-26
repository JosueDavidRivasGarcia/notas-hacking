## Reto: Where are the robots
### Descripción
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474
### Solución
Primero entramos al link que nos proporciona la pagina, en el buscador.
En link agregamos robots.txt en la busqueda, el cual queda de la sig manera:
```link
https://jupiter.challenges.picoctf.org/problem/36474/robots.txt
```
Y nos regresa lo siguiente:
```
User-agent: *
Disallow: /477ce.html
```

Bien, ahora en vez de `robots.txt` agregamos la extensión que aparece, quedando de este manera:
```link
https://jupiter.challenges.picoctf.org/problem/36474//477ce.html
```

Y nos regresa la bandera:
```flag
picoCTF{ca1cu1at1ng_Mach1n3s_477ce}
```

### Notas adicionales
### Referencias

