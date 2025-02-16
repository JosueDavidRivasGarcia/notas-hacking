## Reto: Glitch Cat
### Descripción
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.
### Solución
Al comenzar el challenge, nos da un tiempo de 15 minutos, despues nos da un dominio y un puerto al cual conectarnos con nc. Al hacerlo, vemos que la bandera esta incompleta y la demas esta en hexa, por lo que procedemos a abrir python y hacer la conversion.

```
nc saturn.picoctf.net 57837
```

Entrando ahora nos da la bandera:
`'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'`

Ahora hay que resolver con python, para las conversiones:
```
>>> chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
```

Nos da la conversion
`a4392d2e}'`

Y completamos la bandera:
`picoCTF{gl17ch_m3_n07_`a4392d2e}`

### Notas adicionales
### Referencias