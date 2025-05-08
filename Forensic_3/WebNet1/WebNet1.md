## Reto: WebNet1
### Descripción
Encontramos esto [captura de paquetes](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) y [clave](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recuperar la bandera.
### Solución
Primero descargamos el archivo:
```shell
wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
```

Abrimos el archivo de captura de paquetes, y al igual que en el ejercicio anterior, volvemos a cargar el archivo key:
Lo que realizamos es usar la llave que nos dan(segundo archivo) para desencriptarlo:
- Edit
	- Preferencias
		- Protocols
			- TLS
Y agregamos el archivo.

Aunque seguimos los mismos pasos, aun no podemos encontrar la bandera, pero podemos observar que se pueden exportar objetos dentro de esto.
Vamos a 
- File
	- Export
		- Object
			- HTTP
Ahora descargamos el archivo `.jpg`.

Al hacerlo aplicamos strings para obtener la bandera
```shell
strings vulture.jpg | grep picoCTF{.*}
```

Y nos devuelve la bandera:
```
picoCTF{honey.roasted.peanuts}
```
### Notas adicionales
### Referencias

