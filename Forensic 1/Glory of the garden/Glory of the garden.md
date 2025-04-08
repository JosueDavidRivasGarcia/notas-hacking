## Reto: Glory of the garden
### Descripción
Esto [jardín](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contiene más de lo que parece.
### Solución
Primero descargamos la imagen que se nos proporciona
```shell
wget https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
```

Ahora buscaremos cadenas de texto legibles dentro del archivo utilizando el comando `strings`

```shell
 strings -n18 garden.png
```

`strings`: es una herramienta de Linux que extrae texto imprimible (ASCII o Unicode) de archivos binarios o binarios ejecutables.    
`-n 18` o `-n18`: especifica que sólo muestre las cadenas que tengan al menos **18 caracteres** de longitud. 
`garden.png`: es el archivo del cual se extraerán las cadenas.

Y nos muestra lo siguiente:
```r
Copyright (c) 1998 Hewlett-Packard Company
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
```

Y podemos ver que al final esta la bandera.
```flag
picoCTF{more_than_m33ts_the_3y3657BaB2C}
```
### Notas adicionales
### Referencias



