## Reto: Big Zip
### Descripción
Descomprime este archivo y encuentra la bandera.

- [Descargar archivo zip](https://artifacts.picoctf.net/c/505/big-zip-files.zip)
### Solución
Una vez descargado el archivo comprimido, procedemos a descomprimirlo y buscamos la bandera con un grep, esto se puede hacer desde una sola linea:
```
unzip -p "/mnt/c/Users/josue/Downloads/big-zip-files.zip" | grep pico
```

##### Expliquemos para que sirve cada cosa
`unzip -p`: Extrae el contenido del archivo ZIP
`-p`: Indica que se debe imprimir el contenido de los archivos dentro  del ZIP
`"/mnt/c/Users/josue/Downloads/big-zip-files.zip"`: Especificamos la ruta donde se encuentra el archivo. Al estar utilizando el subsistema, ponemos `"mnt"`.
`grep pico`: Buscamos en el contenido de los archivos la bandera, en este caso inicia con pico.

Al ejecutar el comando, observamos que nos imprime el contenido de los archivos y al final encontramos la bandera:
```
picoCTF{gr3p_15_m4g1c_ef8790dc}
```

Y terminamos el desafío. 
### Notas adicionales
### Referencias
A, D., & A, D. (2024, 11 octubre). _Cómo usar el comando Unzip de Linux_. Tutoriales Hostinger. https://www.hostinger.mx/tutoriales/comando-unzip-linux 