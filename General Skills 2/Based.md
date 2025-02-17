## Reto: Basado
### Descripción
Para obtener verdaderamente 1337, debe comprender diferentes codificaciones de datos, como hexadecimal o binaria. ¿Puedes obtener la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conectar con `nc jupiter.challenges.picoctf.org 29956`.
### Solución
Primero nos conectamos al servidor:
```
 nc jupiter.challenges.picoctf.org 29956
```

Al ingresar nos dice lo siguiente:
`Let us see how data is stored
`nurse
`Please give the 01101110 01110101 01110010 01110011 01100101 as a word.
`...
`you have 45 seconds.....

`Input:`

Lo que hacemos es que abrimos varias ventanas de `CyberChef` para poder convertir a a diferentes bases, tal como dice la pista.

Como observamos el primero, viene primero de binario: `from binario`

Y la respuesta es: `nurse`

Arroja lo siguiente:

`Please give me the 146 141 154 143 157 156 as a word. 
`Input:`

Observamos que esta en base 8: `from octal` 

Y nos da la respuesta: `falcon`

Y nos arroja lo siguiente:

`Please give me the 616e696d6174696f6e as a word. 
`Input:

Observamos que este se encuentra en base hexadecimal, por lo que se procede a su conversión en `CyberChef`

La respuesta es: `animation`

Y ya obtenemos la bandera

### Notas adicionales
### Referencias

_CyberChef_. (s. f.). Crown Copyright 2016-2025. https://gchq.github.io/CyberChef/