## Reto: So Meta
### Descripción
Encuentra la bandera en esto [imagen](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).
### Solución
- Descargamos la imagen
```shell
wget https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
```

Ahora buscaremos cadenas de texto legibles dentro del archivo utilizando el comando `strings`

```shell
strings -n18 pico_img.png
```

Y vemos que se encuentra al final:
```flag
picoCTF{s0_m3ta_d8944929}
```

### Notas adicionales
### Referencias

