## Reto: Caesar
### Descripción:
Descifrar esto [mensaje](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
### Solución
Primero descargamos el archivo:
```shell
wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
```

Ahora hacemos un `cat` al archivo:
```shell
cat ciphertext
```

Y nos regresa lo siguiente:
```
picoCTF{ynkooejcpdanqxeykjrbdofgkq}
```

Vemos que el texto esta rotado, asi que vamos al `cyberchef` para resolverlo.
Al hacerlo nos damos cuenta que no esta rotado 13 veces, asi que aumentamos el numero de rotaciones, que al final terminan siendo 15.

Y nos regresa la bandera:
```flag
picoCTF{crossingtherubiconvfhsjkou}
```

### Notas adicionales
### Referencias

