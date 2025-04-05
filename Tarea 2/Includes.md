## Reto: Includes
### Descripción
¿Puedes conseguir la bandera?Ve a esto [sitio web](http://saturn.picoctf.net:64457/) y mira lo que puedes descubrir.
### Solución
Al entrar a la pagina, vemos que nos muestra lo siguiente:
```
# On Includes

Many programming languages and other computer files have a directive, often called include (sometimes copy or import), that causes the contents of a second file to be inserted into the original file. These included files are called copybooks or header files. They are often used to define the physical layout of program data, pieces of procedural code and/or forward declarations while promoting encapsulation and the reuse of code.

  

Source: Wikipedia on Include directive

Say hello
```

No hay mucho que nos pueda ayudar a encontrar la bandera, asi que al entrar a su codigo fuente, vemos que hay un archivo `css` y otro `js`. 
En ambos archivos se encuentra la primera y segunda parte de la bandera:

```css
/*  picoCTF{1nclu51v17y_1of2_  */
```

```js
//  f7w_2of2_df589022}
```

Y con ello encontramos la bandera

```flag
picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}
```
### Notas adicionales 
### Referencias

