## Reto: First Find
### Descripción
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)
### Solución
Con el comando `unzip` descomprimimos y con la función grep, buscamos el archivo llamado `uber-secret.txt`
```
unzip -l "/mnt/c/Users/josue/Downloads/files.zip" | grep uber-secret
```

`unzip`: descomprime el archivo
`-l`: Lista todos los archivos que hay en la carpeta
`/mnt/c/Users/josue/Downloads/files.zip`: Especificamos la ruta, a manera de subsistema
`|` : Separamos comando
`grep`: Buscamos texto
`uber-secret`: Nombre del archivo

Una vez ejecutado el comando, nos mostrara la direccion en donde se encuentra el archivo que buscamos, en este caso
` 31  2022-05-13 15:17 files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt`

Ahora buscamos la palabra `pico`, ya que así inician las banderas `picoCTF`.

Para esto hacemos una separación entre la ruta que ya habíamos usado y la nueva ruta que nos manda al archivo. Tambien con un `grep` podemos buscar la bandera de la siguiente manera:
```
unzip -p "/mnt/c/Users/josue/Downloads/files.zip" "files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt" | grep pico
```

con un espacio se separa la dirección del archivo descargado y la dirección en la que se encuentra el archivo que buscamos, y con el grep buscamos la bandera.

Y encontramos la bandera
```
picoCTF{f1nd_15_f457_ab443fd1}
```

### Notas adicionales
### Referencias

