## Reto: Local Authority
### Descripción
¿Puedes conseguir la bandera?Ve a esto [sitio web](http://saturn.picoctf.net:51348/) y mira lo que puedes descubrir.
### Solución
Al ingresar a la pagina, podemos notar que es un `loggin`, el cual al inspeccionar el codigo fuente, no tenemos ninguna pista, así que ingresamos cualquier cosa para acceder. Esto nos regresa un mensaje de error. 
En la nueva pagina al inspeccionar el codigo, podemos ver que hay un archivo llamado `secure.js`, al ver ese documento en la siguiente linea podemos ver el `username` y `password`

```js
  if( username === 'admin' && password === 'strongPassword098765' )
```
Volvemos a la primera pagina, ya con las credenciales y al ingresar encontramos la bandera
```flag
picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}
```

### Notas adicionales
### Referencias

