## Reto: IntroToBurp
### Descripción
Intentar [aquí](http://titan.picoctf.net:57939/) para encontrar la bandera
### Solución
Entramos a nuestra herramienta `Burp Suite`, en el apartado de proxy, activamos la intercepcion.
Ahora abrimos el navegador y al estar en la pagina, vemos que es un registro, no importa lo que pongamos como datos, al finalizar seleccionamos `register`.
Ahora vemos que hay una segunda verificación. la cual en OTP ingresamos lo que sea.
Vemos que en la conversación POST, nos dice que el OTP es invalido, si eliminamos el apartado OTP, y le damos en `send` vemos que el `request` nos muestra la bandera.
```flag
picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}
```
 
### Notas adicionales
### Referencias

