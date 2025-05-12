## Reto: Tapping
### Descripción:
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.
### Solución
Entramos al sitio:
```shell
nc jupiter.challenges.picoctf.org 9422
```

Y nos devuelve lo siguiente:
```shell
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }
```

Vemos que es un encriptado en morse, asi que vamos al `cyberchef` y nos devuelve esto:
```
PICOCTFM0RS3C0D31SFUN2683824610
```

Al reacomodar, obtenemos la bandera
```flag
picoCTF{M0RS3C0D31SFUN2683824610}
```

### Notas adicionales
### Referencias

