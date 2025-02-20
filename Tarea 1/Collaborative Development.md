## Reto: Collaborative Development
### Descripción
¡Mi equipo ha estado trabajando muy duro en nuevas características para nuestro programa de impresión de banderas! ¿Me pregunto cómo trabajarán juntos?Puede descargar los archivos de desafío aquí:

- [desafío.zip](https://artifacts.picoctf.net/c_titan/179/challenge.zip)
### Solución
- Descargamos el archivo comprimido
- Descomprimimos el archivo `.zip` con un `unzip`
```
unzip -o challengeiii.zip -d challengeiii
```

Dentro se encuentra una carpeta llamada `drop-in` y al interior de la carpeta esta un archivo llamado `flag.py`
Al mostrar el contenido del programa con el siguiente comando
```
cat flag.py
```

Podemos ver que el contenido es el siguiente
```contenido
print("Printing the flag...")
```

Pero al decir que es colaborativo el archivo, como lo indica el titulo de este ejercicio, hay que revisar el historial de cambios hechos en el git, esto se logra con el comando:
```git
git reflog
```

Observamos que han existido varios cambios
```salida
5e4b2da (HEAD -> main) HEAD@{0}: checkout: moving from feature/part-3 to main
12c2ae8 (feature/part-3) HEAD@{1}: commit: add part 3
5e4b2da (HEAD -> main) HEAD@{2}: checkout: moving from main to feature/part-3
5e4b2da (HEAD -> main) HEAD@{3}: checkout: moving from feature/part-2 to main
74989a4 (feature/part-2) HEAD@{4}: commit: add part 2
5e4b2da (HEAD -> main) HEAD@{5}: checkout: moving from main to feature/part-2
5e4b2da (HEAD -> main) HEAD@{6}: checkout: moving from feature/part-1 to main
300cff1 (feature/part-1) HEAD@{7}: commit: add part 1
5e4b2da (HEAD -> main) HEAD@{8}: checkout: moving from main to feature/part-1
5e4b2da (HEAD -> main) HEAD@{9}: commit (initial): init flag printer
```

Vemos que hay varios cambios hechos con los nombres `feature/part-X`, así que con ayuda del comando `git diff` obtenemos las modificaciones que se han realizado en cada uno de los cambios anteriores

Para la parte 1:
```
git diff feature/part-1
```
Salida:
```salida
diff --git a/flag.py b/flag.py
old mode 100644
new mode 100755
index 6e17fb3..77d6cec
--- a/flag.py
+++ b/flag.py
@@ -1,2 +1 @@
 print("Printing the flag...")
-print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
```

Para la parte 2:
```
git diff feature/part-2
```
Salida
```salida
diff --git a/flag.py b/flag.py
old mode 100644
new mode 100755
index 7ab4e25..77d6cec
--- a/flag.py
+++ b/flag.py
@@ -1,3 +1 @@
 print("Printing the flag...")
-
-print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
```

Para la parte 3:
```
git diff feature/part-3
```
Salida:
```salida
diff --git a/flag.py b/flag.py
old mode 100644
new mode 100755
index c312152..77d6cec
--- a/flag.py
+++ b/flag.py
@@ -1,3 +1 @@
 print("Printing the flag...")
-
-print("w0rk_798f9981}")
```

Podemos ver que en los `print` se encuentran las diferentes partes de la bandera, al juntarlo obtenemos la bandera.
```flag
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981}
```

### Notas adicionales
### Referencias

