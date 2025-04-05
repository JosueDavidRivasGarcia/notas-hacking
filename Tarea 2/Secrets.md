## Reto: Secrets
### Descripción
Tenemos varias páginas ocultas. ¿Puedes encontrar el que tiene la bandera?El sitio web se está ejecutando [aquí](http://saturn.picoctf.net:51039/).
### Solución
Entramos a la pagina y inspeccionamos el código fuente, vemos que hace alusión a la carpeta `secret`, así que entramos:
```http
view-source:http://saturn.picoctf.net:51039/secret/
```

Vemos que ahora se hace alusión a una carpeta llamada `hidden`, asi que ingresamos:
```http
view-source:http://saturn.picoctf.net:51039/secret/hidden/
```

Y finalmente hace alusión a la carpeta `superhidden`, al ingresar nos muestra la bandera:
```http
view-source:http://saturn.picoctf.net:51039/secret/hidden/superhidden
```

```flag
picoCTF{succ3ss_@h3n1c@10n_51b260fe}
```

### Notas adicionales
### Referencias

