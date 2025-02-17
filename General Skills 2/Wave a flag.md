## Reto: Agita una bandera
### Descripción
¿Puedes invocar banderas de ayuda para una herramienta o binario? [Este programa](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) tiene información extraordinariamente útil...
### Solución
Como en los desafíos anteriores, solo hemos necesitado el comando grep, lo intentaremos, esperando que nos de solo la bandera, así que con `-a` buscaremos en binario y con `-o` solo buscaremos la bandera, ignorando el demás contenido:

Intento 1:
```
 grep -a -o  picoCTF{.*} /mnt/c/Users/josue/Downloads/warm
```

Y obtenemos la bandera, al primer intento
```
picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
```
### Notas adicionales
### Referencias

