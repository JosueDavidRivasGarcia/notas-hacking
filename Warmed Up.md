## Reto: Warmed Up
### Descripción
¿Qué es 0x3D (base 16) en decimal (base 10)?
### Solución
Para convertir de base 16 a base 10, primero cada digito en Hexadecimal lo convertimos a binario con 4 digitos, en este caso:

| 3   | 0011 |
| --- | ---- |
| D   | 1101 |
Juntamos los números resultantes en un solo binario

00111101

Y ahora convertimos a decimal:

| 1   | 1   | 1   | 1   | 0   | 1   |
| --- | --- | --- | --- | --- | --- |
| 32  | 16  | 8   | 4   | 2   | 1   |

32 + 16 + 8 + 4 + 1 = 61
### Notas adicionales
Ten certeza de buscar una tabla confiable, hacer bien tus cálculos, además de enviar la respuesta a manera de bandera: picoCTF{61}

### Referencias