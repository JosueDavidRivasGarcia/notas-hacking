## Reto: Lo encadena
### Descripción
Puedes encontrar la bandera en [archivo](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) ¿sin ejecutarlo?
### Solución
Para encontrar la bandera sin ejecutarlo, usamos el comando grep:
```
grep picoCTF /mnt/c/Users/josue/Downloads/strings
```

Nos dice que no podemos buscar en binario, por lo que procedemos a ejecutar el comando, para buscar en binario con grep usando `-a`. 
```
grep -a picoCTF /mnt/c/Users/josue/Downloads/static
```

Nos muestra una salida tan grande que no localizamos la bandera, así que le decimos que nos muestre solo la bandera:
```
grep -a -o picoCTF /mnt/c/Users/josue/Downloads/strings
```

Solo muestra picoCTF, por lo que mostramos el contenido que tiene usando limites (En este caso los corchetes):
```
grep -a -o  picoCTF{.*} /mnt/c/Users/josue/Downloads/strings
```

Y obtenemos la bandera
```
picoCTF{5tRIng5_1T_827aee91}
```

### Notas adicionales
### Referencias
_15 practical GREP command examples in Linux / UNIX_. (2009, 15 marzo). https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/


