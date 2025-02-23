## Reto: Commitment Issue
### Descripción
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/76/challenge.zip)
### Solución
- Descargamos el archivo que nos proporciona la pagina
Descomprimimos el archivo y creamos la carpeta
```
unzip -o desafio.zip -d desafio
```

Ahora entramos a la carpeta que se encuentra ahí
```
cd drop-in
```

Vemos los `commits` anteriores:
```git
git reflog
```

Vemos que existe un `commit` anterior
```salida
a6dca68 (HEAD -> master) HEAD@{0}: commit: remove sensitive info
e720dc2 HEAD@{1}: commit (initial): create flag
```

Con un `diff`, mostramos lo que antes contenía el repositorio: 
```git
 git diff HEAD^ HEAD
```

```salida
diff --git a/message.txt b/message.txt
index d263841..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_7246792d}
+TOP SECRET
```

Como vemos, ya nos da la bandera:
```
picoCTF{s@n1t1z3_7246792d}
```
### Notas adicionales
### Referencias

