## Reto: inútil 
### Descripción
Hay un script interesante en el directorio de inicio del usuario

Los detalles adicionales estarán disponibles después de lanzar su instancia de desafío.

### Solución
Podemos notar que en la carpeta `home`, se encuentra solo un archivo llamado `useless`
```
dir
```

Ahora mostraremos el contenido del archivo
```
cat useless
```

Esto simplemente nos muestra un programa bash, no pudimos encontrar nada y ejecutando un grep, tampoco.

Si vemos los detalles del programa con el comando `man` para mostrar las paginas de manual. Con el comando `cat`, tal como se lee en el contenido. Decía que leyendo el manual nos daba la bandera.
Así que vemos el manual:

```
man useless
```

Y la bandera es:
```
picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_3823}
```


### Notas adicionales
### Referencias

