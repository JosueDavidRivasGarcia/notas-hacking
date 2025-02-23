## Reto: Permisos
### Descripción
¿Puedes leer archivos en el archivo raíz?El administrador del sistema ha aprovisionado una cuenta para usted en el servidor principal:`ssh -p 50792 picoplayer@saturn.picoctf.net`Contraseña: `NBD+zO8s4y`¿Puedes iniciar sesión y leer el archivo raíz?
### Solución
Entramos al servidor con `ssh`:
```ssh
ssh -p 50792 picoplayer@saturn.picoctf.net
```
Introducimos la contrasena:
```password
NBD+zO8s4y
```

Ahora, tal como dice el desafio, mostramos los permisos que nosotros tenemos con el comando
```
sudo -l -U picoplayer
```

Nos muestra lo siguiente:
```salida
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
```

Nosotros tenemos permiso de `vi`, por lo que tenemos permiso para ejecutar el comando `usr/bin/vi` con privilegios de administrador, por lo que se usara `sudo`.

ALL proviene de un archivo de configuración de **`sudoers`**, que define los permisos de sudo para usuarios o grupos.

Usamos el comando:
```
sudo vi/root
```

Observamos un archivo llamado `flag.txt`, por lo que intuimos que ahí esta la bandera.

Al ejecutar el comando:
```
sudo vi /root/.flag.txt
```

Y nos regresa la bandera

```flag
picoCTF{uS1ng_v1m_3dit0r_1cee9dcb}
```
### Notas adicionales
### Referencias

