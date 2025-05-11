## Reto: Secret of the Polyglot
### Descripción
El Centro de Operaciones de Red (NOC) de su institución local recogió un archivo sospechoso, están recibiendo información contradictoria sobre qué tipo de archivo lo es. Te han traído como un experto externo para examinar el archivo. Can ¿extraes toda la información de este extraño archivo?Descarga el archivo sospechoso [aquí](https://artifacts.picoctf.net/c_titan/8/flag2of2-final.pdf).
### Solución
Descargamos el archivo;
```shell
 wget https://artifacts.picoctf.net/c_titan/8/flag2of2-final.pdf
```

Ahora abrimos el archivo y encontramos esto:
```
1n_pn9_&_pdf_249d05c0}
```

Vemos que es la parte final de la bandera, asi que procedemos a cambiarlo a una imagen:
```shell
cp flag2of2-final.pdf flag2of2-final.png
```

Y nos devuelve lo siguiente:
```
picoCTF{f1u3n7_
```

Al juntarlo, obtenemos la bandera:
```flag
picoCTF{f1u3n7_1n_pn9_&_pdf_249d05c0}
```


### Notas adicionales
### Referencias

