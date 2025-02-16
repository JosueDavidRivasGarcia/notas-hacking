## Reto:  plumbing
### Descripción
A veces necesita manejar datos de proceso fuera de un archivo. ¿Puede encontrar una manera de mantener la salida de este programa y buscar la bandera? Conectarse a `jupiter.challenges.picoctf.org 4427`.
### Solución

Como hemos visto anteriormente, poder ingresar al dominio y al puerto utilizando nc, por lo que procedemos a ejecutar el comando.

```
nc jupiter.challenges.picoctf.org 4427 
```

Al ejecutar este comando, vemos que nos llena de información basura, por lo que procederemos a buscar la bandera con un grep.

```
nc jupiter.challenges.picoctf.org 4427 | grep -i "pico"
```

Con esto, nos da la bandera lista para copiar.
### Notas adicionales
A veces tienes que volver a tus ejercicios anteriores, ya que son las bases para poder resolver problemas mas complejos
### Referencias
