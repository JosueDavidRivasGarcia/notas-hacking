## Reto: Client-side-again
### Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/56816/` ([link](https://jupiter.challenges.picoctf.org/problem/56816/)) or http://jupiter.challenges.picoctf.org:56816
### Solución
Al ingresar a la pagina, vemos que es un login, asi que entramos a ver codigo fuente de la pagina y podemos observar que ahi esta la bandera, solo que de manera ofuscada.

Solo tenemos que organizarla de manera sencilla:
```js
var _0x5a46=['37115}','_again_3','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];
```

Y obtenemos la bandera, lo unico que tenemos que hacer es  ordenarla:
```flag
picoCTF{not_this_again_337115} 
```

### Notas adicionales
### Referencias

