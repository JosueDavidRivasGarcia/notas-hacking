## Reto: picobrowser
### Descripción
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or http://jupiter.challenges.picoctf.org:50522
### Solución
En este desafio, lo que tenemos que hacer es un curl para poderencontrar la bandera y lo que tenemos que hacer es cambiar el `user-agent` con el siguiente comando:

```q
curl -s https://jupiter.challenges.picoctf.org/problem/50522/flag -H "user-agent: picobrowser" | grep pico{.*}
```


Obtiene la página web, finge ser un navegador especial, y filtra la bandera secreta que está en formato.

Y obtenemos la bandera:
```flag
picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}
```

### Notas adicionales
### Referencias 

