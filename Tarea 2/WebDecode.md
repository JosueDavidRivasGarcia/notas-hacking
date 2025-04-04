## Reto: WebDecode
### Descripción
¿Sabes cómo usar el inspector web?Comienza a buscar [aquí](http://titan.picoctf.net:49390/) para encontrar la bandera
### Solución
Al entrar a la pagina podemos notar que intenta burlarse de nosotros y al inspeccionar el codigo, no se ve nada raro. Ahora en el apartado de  `about` dice que la bandera puede estar ahi. Al inspeccionar el código vemos que hay una cadena en `base64` y tal cual lo dice el desafió puede encontrarse al decodificar esa cadena.
```html
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9">
```

Al pasarlo por `cyberchef` en `from base64` nos da la bandera:
```flag
picoCTF{web_succ3ssfully_d3c0ded_10f9376f}
```
### Notas adicionales
### Referencias

