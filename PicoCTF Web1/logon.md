## Reto: logon
### Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573
### Solución
Entramos a la pagina a donde nos dirige esa pagina, gracias al comando proporcionado en la materia, ingresamos a la linea de comandos `Kali-Linux` y ingresamos el siguiente comando:

```r
curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: username;password;admin = True" | grep pi
coCTF{.*}
```

Este comando nos permite ingresar a la cookie donde se encuentra la bandera, y `grep` nos sirve para solo buscar e identificar la bandera.

```html
 <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>
```

Y ya encontramos la bandera:
```flag

```


### Notas adicionales
### Referencias
