## Reto: Static ain't always noise
### Descripción
Puedes ver los datos en este binario: [estático](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? Esto [guión BASH](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) ¡podría ayudar!
### Solución
Mostramos el contenido de la carpeta, y buscamos la bandera con picoCTF
```
cat /mnt/c/Users/josue/Downloads/static | grep pico
```

Nos lanza un error `grep: (standard input): binary file matches`, que nos dice que no podemos buscar en binario, de la misma manera que en texto, por lo que la forma adecuada de buscar en binario, por medio de `grep` es:
```
cat /mnt/c/Users/josue/Downloads/static | grep -a pico
```

Y obtenemos la bandera
```
picoCTF{d15a5m_t34s3r_98d35619}
```

### Notas adicionales
Al abrir el guion bash me marco virus y no me dejo continuar a la pagina (Yo uso subsistema). Al abrirlo en una VM, me dio un código, que fue poco eficiente para la solución del reto.
### Referencias

_How do I grep through binary files that look like text?_ (s. f.). Server Fault. https://serverfault.com/questions/328101/how-do-i-grep-through-binary-files-that-look-like-text