## Reto: MatchTheRegex
### Descripción
Qué tal tratar de igualar una expresión regularEl sitio web se está ejecutando [aquí](http://saturn.picoctf.net:54606/).
### Solución
Entramos a la pagina que nos dirige el ejercicio
Al examinar el codigo fuente, vemos que en el comentario de la parte de validacion nos da una pista bastante importante sobre la expresion, la cual se presenta a continuacion:
```js
// ^p.....F!?
```

Debe de iniciar con `p` y finaliza con `F`, obviamente esta palabra sera `picoCTF`

Y al ingresarla nos regreesa la bandera
```flag
picoCTF{succ3ssfully_matchtheregex_0694f25b}
```

### Notas adicionales
### Referencias

