## Reto: Búsqueda binaria
### Descripción
¿Quieres jugar un juego? A medida que usa más del shell, ¡podría estar interesado en cómo funcionan! La búsqueda binaria es un algoritmo clásico utilizado para encontrar rápidamente un elemento en una lista ordenada. ¿Puedes encontrar la bandera? Tendrás 1000 posibilidades y solo 10 conjeturas.La seguridad cibernética a menudo tiene una gran cantidad de datos para revisar, desde registros, informes de vulnerabilidad y análisis forense. ¡Practicar los fundamentos manualmente podría ayudarlo en el futuro cuando tenga que escribir sus propias herramientas!Puede descargar los archivos de desafío aquí:

- [desafío.zip](https://artifacts.picoctf.net/c_atlas/19/challenge.zip)

Los detalles adicionales estarán disponibles después de lanzar su instancia de desafío.

### Solución
Lo primero que hacemos es conectarnos al servidor
Conectar por ssh:
```
ssh -p 51729 ctf-player@atlas.picoctf.net
```
La contraseña:
`ctf-player@atlas.picoctf.net's password:`
```
1db87a14
```

Al comenzar el juego nos indica que es un algoritmo de búsqueda binaria, el cual va de 0 al 1000, recordemos que el algoritmo nos dice si es menor o mayor el numero ingresado al valor que obtuvo. 

`Welcome to the Binary Search Game!
`I'm thinking of a number between 1 and 1000.

tendremos que comenzar por la mitad ya que seria nuestro punto de partida.
`Enter your guess: 500
`Lower! Try again.

Nos va indicando si estamos por debajo o sobre el numero que mando el algoritmo. es una busqueda hasta encontrar la solucion, se recomienda comunmente hacer, es siempre ir por el medio:
# ${inicio+final/2}$

`Enter your guess: 250
`Lower! Try again.
`Enter your guess: 100
`Higher! Try again.
`Enter your guess: 150
`Higher! Try again.
`Enter your guess: 200
`Higher! Try again.
`Enter your guess: 220
`Lower! Try again.
`Enter your guess: 210
`Lower! Try again.
`Enter your guess: 205
`Lower! Try again.

Aquí el numero ya se que esta entre 200 y 205, así que aplicando la formula…

`Enter your guess: 203
`Congratulations! You guessed the correct number: 203

Y finalmente obtenemos la bandera.

`Here's your flag: 
```
picoCTF{g00d_gu355_1597707f}
```

`Connection to atlas.picoctf.net closed.

Se termina la conexión.
### Notas adicionales

En el enlace nos la la referencia hacia una carpeta, que uno de sus archivos es el algoritmo de búsqueda binaria, lo que nos puede a ayudar a entender como se comporta este algoritmo.
### Referencias
