## Descripcion:

Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:60153/), and find the flag!

## Solucion

Vamos al sitio con el link que nos proporciona y ahi dentro vemos una pagina con un codigo de js que al momento de hacer click, nos lo guarda en el portapapeles:

```js
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£Ö�ÓÚåÛÑ¢ÕÓ�Ô�ÅÐ�Ù�í";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
    
```

Parece ser que el codigo por si mismo nos entrega la flag al ejecutaarse, entonces vamos a buscar js online, pegamos nuestro codigo y lo ejecutamos. Al hacerlo aparece una ventana emergente con la flag:

```flag
picoCTF{p@g3_turn3r_e8b2d43b}
```

### Notas adicionales
### Referencias

