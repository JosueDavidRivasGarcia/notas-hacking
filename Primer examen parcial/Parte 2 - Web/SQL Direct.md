## Reto: SQL Direct
### Descripción
¡Conéctese a este servidor PostgreSQL y encuentre la bandera!`psql -h saturn.picoctf.net -p 61962 -U postgres pico`La contraseña es `postgres`

### Solución
Abrimos nuestra terminal de `Kali` y ingresamos el comando para hacer la conexión: 
```shell
psql -h saturn.picoctf.net -p 61962 -U postgres pico
```
La contraseña será:
```
postgres
```

Ahora nos indica que escribamos `help`
Al hacerlo nos proporciona lo siguiente
```
Use \? for help or press control-C to clear the input buffer.
```

Al usar el comando `\?` nos muestra un listado de los comandos que podemos utilizar.
Y al usar el comando `Ctrl` + `C` borramos el `buffer`.

Leyendo la lista de comandos, primero utilizamos el siguiente para mostrar todas las bases de datos:
```SQL
\l 
```

El cual nos muestra las siguientes 3 opciones:
- pico
- postgres
- template0

Ahora para conectar con una base de datos usamos el comando `\c`, y nosotros queremos ingresar a la base de datos `pico`
```SQL
\c pico
```

Una vez en la base de datos, mostramos las tablas con el comando:
```SQL
\dt
```

Vemos que solo hay una tabla llamada flags:
```r
         List of relations
 Schema | Name  | Type  |  Owner
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)
```

Ahora con SQL mostramos la tabla
```SQL
 select * from flags;
```

Y obtenemos la bandera:
```flag
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
```




### Notas adicionales
### Referencias

