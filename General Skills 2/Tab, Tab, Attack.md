## Reto: ### Pestaña, Pestaña, Ataque
### Descripción
El uso de tabcomplete en la Terminal agregará años a su vida, especialmente cuando se trata de estructuras de directorios y nombres de archivos de larga duración: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)
### Solución 1
Descomprimimos, mostrando el contenido con `unzip -p` y buscamos la bandera con un `grep`:
```
 unzip -p "/mnt/c/Users/josue/Downloads/Addadshashanammu.zip" |grep pico
```

Nos dice que no podemos buscar en binario de esa manera, asi que con `-a` buscamos en binario con `grep`:
```
unzip -p "/mnt/c/Users/josue/Downloads/Addadshashanammu.zip" |grep -a pico
```
Y aparece la bandera
```
picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
```

### Solución 2
Mostrar únicamente la bandera:
```
unzip -p "/mnt/c/Users/josue/Downloads/Addadshashanammu.zip" |grep -a -o picoCTF{.*}
```
Esto nos muestra exclusivamente la bandera
### Notas adicionales
### Referencias