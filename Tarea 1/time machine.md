## Reto: Time Machine
### Descripción
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/67/challenge.zip)
### Solución

Al ser un archivo `.zip` intentaremos realizar la búsqueda mediante `unzip` y en un solo comando buscar la bandera, la mayoría de los ejercicios se ha resuelto de esta manera, así que lo intentamos:
```
unzip -p desafioo.zip | grep -a -o picoCTF{.*}
```

Y obtenemos la bandera
```flag
picoCTF{t1m3m@ch1n3_5cde9075}
```
### Notas adicionales
### Referencias

