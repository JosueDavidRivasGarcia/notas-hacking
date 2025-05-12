## Reto: Easy 1
### Descripción:
La almohadilla de una sola vez puede ser criptográficamente segura, pero no cuando conoce la clave. ¿Puedes resolver esto? Le hemos dado la bandera cifrada, la llave y una tabla para ayudar `UFJKXQZQUNB` con la clave de `SOLVECRYPTO`. Puedes usar esto [mesa](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) para resolverlo?.
### Solución
Descargamos el archivo:
```shell
wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt
```

Podemos hacerlo manualmente con la tabla o podemos ir al `cyberchef`.

Ahí ponemos el cifrado y le damos la llave, y nos regresa esto:
```
CRYPTOISFUN
```

Esa sera la bandera:
```flag
picoCTF{CRYPTOISFUN}
```

### Notas adicionales:

### Referencias

