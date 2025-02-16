## Reto: Magikarp Ground Mission
### Descripción
¿Sabes cómo moverte entre directorios y leer archivos en la terminal? Inicia el contenedor, conéctate a él mediante `ssh` y luego usa `ls` una vez conectado para comenzar. Inicia sesión vía `ssh` como `ctf-player` con la contraseña `6d448c9c`.

Habrá más detalles disponibles después de lanzar tu instancia del desafío.
### Solución
Una vez comience la instancia del desafío, nos conectaremos por medio de ssh:
```
ssh ctf-player@venus.picoctf.net -p 52776
``` 

Introducimos la contraseña:
```
6d448c9c
```

Ahora ya conectados al servidor, podemos observar que estamos en un shell. Para comenzar a buscar la bandera, listamos los archivos que este pueda contener:
```
ls
```
Nos muestra dos archivos
**`1of3.flag.txt`  `instructions-to-2of3.txt`**

Al mostrar el contenido del archivo `1of3.flag.txt` con el comando `cat`, observamos que contiene el inicio de la bandera.
```
picoCTF{xxsh_
```
Al mostrar el contenido del archivo `instructions-to-2of3.txt`, con el comando `cat`. Nos da una pista para encontrar la siguiente parte de la bandera.
***`
A continuación, vaya a la raíz de todas las cosas, más sucintamente `/`

Entonces salimos del directorio, hacia el directorio raíz, utilizando el comando:
```
cd /
```
Listamos los archivos que contiene
```
ls
```
Podemos observar todo el contenido en el directorio:
**`2of3.flag.txt  boot  etc   instructions-to-3of3.txt  lib64  mnt  proc  run   srv  `tmp  var bin            dev   home  lib                       media  opt  root  sbin  sys  usr`

El primer archivo "**`2of3.flag.txt`**" es la siguiente parte de la bandera, así que mostramos el contenido.
```
 cat 2of3.flag.txt
```
Y obtenemos la siguiente parte de la bandera
```
0ut_0f_\/\/4t3r_
```

Ahora leemos las instrucciones, que nos llevaran a la siguiente parte de la bandera.
```
cat instructions-to-3of3.txt
```
El cual dice:

***`Por último, ctf-player, vete a casa... más sucintamente ~

Ya con la pista, procedemos a buscar la ultima parte de la bandera, ejecutando el comando
```
cd ~
```
Ahora listamos los archivos que están en el directorio principal.
```
ls
```
Archivos:
**`3of3.flag.txt  drop-in`

Mostramos el contenido del archivo:
```
cat 3of3.flag.txt
```

Y obtenemos la bandera completa
```
5190b070}
```

Al juntar toda la bandera queda de la siguiente forma:
```
picoCTF{xxsh_0ut_0f_\/\/4t3r_5190b070}
```

Y terminamos el desafío.
### Notas adicionales
### Referencias

