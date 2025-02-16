## Reto: Nice netcat
### Descripción
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 21135`, but it doesn't speak English...
### Solución
Ingresamos el comando para entrar a el dominio y el puerto
```
nc mercury.picoctf.net 21135
```
Esto nos da una lista de números en decimales, las cuales tendrán que convertirse a ASCII.
Para ello utilizamos python como en anteriores problemas.
1. Creamos una lista con los números que nos arroja
```
decimales = [112, 105, 99, 111, 67, 84, 70, 123, 103, 48, 48, 100, 95, 107, 49, 116, 116, 121, 33, 95, 110, 49, 99, 51, 95, 107, 49, 116, 116, 121, 33, 95, 97, 102, 100, 53, 102, 100, 97, 52, 125, 10]

```

1. Hacemos una función para convertir a ASCII
```
texto = ''.join(chr(d) for d in decimales)
```

 Se crea una variable llamada texto que con ``''.join()``  une todos los caracteres en una sola cadena de texto, ``chr(d)`` convierte cada numero en su correspondiente carácter ASCII. Y finalmente con ``for d in decimales`` iteramos sobre cada numero decimal.

2. Imprimimos la llave
```
print(texto)
```

### Notas adicionales
Esta es la manera en la que yo lo hice, tomando como referencia apuntes de la materia de big data usando python y también la conversión de ejercicios anteriores.
### Referencias
_Array.prototype.join() - JavaScript | MDN_. (s. f.). MDN Web Docs. https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/join