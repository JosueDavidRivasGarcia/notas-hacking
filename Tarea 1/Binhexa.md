## Reto: Binhexa
### Descripción
¿Qué tan bien puedes realizar operaciones binarias básicas?
Los detalles adicionales estarán disponibles después de lanzar su instancia de desafío.

### Solución
Al iniciar el desafio, por medio del comando `nc` :
```nc
nc titan.picoctf.net 53387
```

Al iniciar la instancia, nos marca las instrucciones a seguir para realizar el reto.
```
Welcome to the Binary Challenge!"

Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 10111000

Binary Number 2: 10101110
```

Primero dice que es el desplazamiento a la derecha:
```
Question 1/6:

Operation 1: '>>'

Perform a right shift of Binary Number 2 by 1 bits .

Enter the binary result: 01010111

Correct!
```

Después nos aparece una operación `AND`:
```
Question 2/6:

Operation 2: '&'

Perform the operation on Binary Number 1&2.

Enter the binary result: 10101000

Correct!
```

Después nos pide realizar una operación: 
```
Question 3/6:

Operation 3: '*'

Perform the operation on Binary Number 1&2.

Enter the binary result: 111110100010000

Correct!
```

Lo siguiente es la operación `OR`:
```
Question 4/6:

Operation 4: '|'

Perform the operation on Binary Number 1&2.

Enter the binary result: 10111110

Correct!
```

Luego realizamos una suma entre los números: 
```
Question 5/6:

Operation 5: '+'

Perform the operation on Binary Number 1&2.

Enter the binary result: 101100110

Correct!
```

Como ultima operación realizamos un desplazamiento a la izquierda: 
```
Question 6/6:

Operation 6: '<<'

Perform a left shift of Binary Number 1 by 1 bits.

Enter the binary result: 101110000

Correct!
```

Ahora nos pide ingresar el resultado de la ultima operación en hexadecimal:
```
Enter the results of the last operation in hexadecimal: 170
```

Y nos da la bandera
```flag
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_1367e2c6}
```

### Notas adicionales
### Referencias

