## Reto: ideme

### Descripción: 
Cada archivo recibe una bandera.El analista de SOC vio una imagen enviada de un lado a otro entre dos personas. Decidieron investigar y descubrieron que había más de lo que parece [aquí](https://artifacts.picoctf.net/c/258/flag.png).
### Solución
Primero descargamos el archivo:
```shell
wget https://artifacts.picoctf.net/c/258/flag.png
```

Buscamos y descomprimimos archivos ocultos:
```shell
binwalk -e flag.png
```

Ahora entramos a la carpeta descomprimida:
```shell
cd _flag.png.extracted/
```

Dentro, entramos a la carpeta `secret`:
```shell
cd secret
```

Y ahí se encuentra una imagen, la abrimos:
```shell
open flag.png
```

Y nos devuelve la bandera:
```flag
picoCTF{Hidding_An_image_within_@n_ima9e_d55982e8}
```
### Notas adicionales
### Referencias

