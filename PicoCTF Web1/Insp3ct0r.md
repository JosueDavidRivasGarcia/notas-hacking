## Reto: Insp3ct0r
### Descripción
Kishor Balan nos avisó que el siguiente código puede necesitar inspección: `https://jupiter.challenges.picoctf.org/problem/9670/` ([enlace](https://jupiter.challenges.picoctf.org/problem/9670/)) o http://jupiter.challenges.picoctf.org:9670
### Solución
Al entrar a la pagina en el apartado de How, nos dice que usemos HTML, CSS, y JS. 
Inspeccionamos el codigo fuente y podemos ver que en un comentario inicia la bandera.
```html
<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
```

Bien, ya que tenemos la primera parte de la bandera, entramos al archivo `CSS` y podemos ver que al final se encuentra la siguiente parte de la bandera.
```css
/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```

Por ultimo al entrar a el documento de `javaScript`, al final en un comentario se encuentra la parte final de la bandera:
```js
/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?2e7b23e3} */
```

Al juntar cada parte de la bandera nos queda de la siguiente manera:
```flag
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}
```
### Notas adicionales

### Referencias

