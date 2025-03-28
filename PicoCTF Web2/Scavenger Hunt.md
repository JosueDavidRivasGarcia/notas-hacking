## Reto:  Scavenger Hunt
### Descripción
There is some interesting information hidden around this site [http://mercury.picoctf.net:27278/](http://mercury.picoctf.net:27278/). Can you find it?
### Solución
Al entrar al enlace proporcionado, podemos observar una pagina la cual no nos da muchas pistas, aunque es muy parecida a un reto anterior llamado `robots`.
Bien al inspeccionar el código, podemos observar que en un comentario esta el inicio de la bandera.
```html
<!-- Here's the first part of the flag: picoCTF{t -->
```

Bien, ahora entramos al archivo de estilos `css`, donde encontramos la segunda parte de esta bandera.

```css
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```

Bien, por ahora llevamos dos partes de esta bandera, entraremos al archivo de `js` para poder ver mas pistas. 
Al entrar nos encontramos la siguiente pista, pero no la siguiente parte de la bandera:
```js
/* How can I keep Google from indexing my website? */
```

Pregunta como Google indexa el sitio web, donde en retos anteriores, vimos que era en el archivo robots, asi que ingresamos al siguiente enlace:
```http
http://mercury.picoctf.net:27278/robots.txt
```

Este enlace nos muestra la siguiente parte de la bandera
```http
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```

Bien, la siguiente pista es como poder ingresar al servidor apache, en el cual entramos con  `.htaccess`.

Entramos al siguiente enlace:
```http
http://mercury.picoctf.net:27278/.htaccess
```

Y aqui encontramos la siguiente parte de la bandera.

```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```

Dice que la pagina fue echa en una MAC, en donde todas las carpetas tienen el documento `DS_Store` y ahi encontramos el final de la bandera:
```
Congrats! You completed the scavenger hunt. Part 5: _a69684fd}
```

```flag
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_a69684fd}
```


### Notas adicionales
### Referencias



