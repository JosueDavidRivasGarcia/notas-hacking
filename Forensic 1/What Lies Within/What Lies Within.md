## Reto: What Lies Within
### Descripción
Hay algo en el [edificio](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). ¿Puedes recuperar la bandera?
### Solución
Aplicando el comando `strings` no nos devuelve nada, asi que instalaremos una nueva herramienta llamada `zsteg`. La cual puede encontrar texto en las imagenes.

```ruby
gem install zsteg
```

Ahora abriremos la imagen con el siguiente comando:
```ruby
zsteg buildings.png
```

Y nos muestra el siguiente resultado:
```shell
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"
```

Y encontramos la bandera:
```flag
picoCTF{h1d1ng_1n_th3_b1t5}
```

### Notas adicionales
### Referencias

