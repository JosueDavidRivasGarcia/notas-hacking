## Reto: Lets Warm Up
### Descripción
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
### Solución 1
Simplemente hay que buscar una tabla de hexadecimal a ascii e identificar el 0x70 en la columna hexadecimal, al lado en la columna char o caracter se mostrara la letra, en este caso es la letra "p", por lo que esa es la solucion.

### Solución 2
O bien, podría ser con una función de python, llamada chr
```
>>> chr(0x70)
    'p'
```
### Notas adicionales
Ten certeza de buscar una tabla confiable, además de enviar la respuesta a manera de bandera: picoCTF{p}
### Referencias
_ASCII Chart_. (s. f.). CommFront. https://www.commfront.com/pages/ascii-chart