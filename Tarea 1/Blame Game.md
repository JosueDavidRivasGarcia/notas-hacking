## Reto: Juego de Culpa
### Descripción
Los compromisos de alguien parecen estar impidiendo que el programa funcione. ¿Quién es?Puede descargar los archivos de desafío aquí:

- [desafío.zip](https://artifacts.picoctf.net/c_titan/157/challenge.zip)

### Solución
Pues al ser un archivo `.zip` (archivo comprimido), podemos usar el comando `unzip -p` para que imprima el contenido de cada archivo y buscaremos con el comando `grep` solamente la bandera, estableciendo limites, en este caso los parentesis.

```
 unzip -p challengeii.zip | grep -a -o picoCTF{.*}
```

Con eso obtenemos la bandera
```flag
picoCTF{@sk_th3_1nt3rn_cfca95b2}
```

### Notas adicionales
### Referencias

