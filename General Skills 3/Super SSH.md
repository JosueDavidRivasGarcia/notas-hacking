## Reto: Super SSH
### Descripción
Usar un Secure Shell (SSH) va a ser bastante importante.Puedes `ssh` como `ctf-player` a `titan.picoctf.net` en el puerto `56856` ¿para conseguir la bandera?También necesitará la contraseña `84b12bae`. Si se le pregunta, acepte la huella digital con `yes`.Si su dispositivo no tiene un shell, puede usar: [https://webshell.picoctf.org](https://webshell.picoctf.org/)Si no está seguro de qué es un shell, consulte nuestro Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)

### Solución
Entramos al servidor, mediante ssh:
```ssh
ssh ctf-player@titan.picoctf.net -p 56856
```

Y ponemos la contraseña:
```password
84b12bae
```

Al entrar, nos da directamente la bandera:
```flag
 picoCTF{s3cur3_c0nn3ct10n_07a987ac}
```
### Notas adicionales
### Referencias

