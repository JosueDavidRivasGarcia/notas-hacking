## Reto: Chrono
### Descripción
How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 58640
Username: picoplayer 
Password: emrdK96SGH
```

### Solución
Primero nos conectamos al servidor por ssh:
```ssh
ssh picoplayer@saturn.picoctf.net -p 58640
```

Ingresamos la contraseña:
```password
emrdK96SGH
```

Al ingresar, vamos al directorio raíz con el siguiente comando:
```
cd /
```

Una vez estando ahí, buscamos donde pueda estar el `cron`.
Buscando entre las carpetas, observamos que esta en la carpeta llamada `etc`
Así que mostramos el contenido de este archivo:
```
cat crontab
```

Y nos regresa la bandera
```flag
picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}
```

### Notas adicionales
### Referencias

