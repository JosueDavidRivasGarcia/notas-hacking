## Reto: WebNet0
### Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
### Solución
Descargamos los archivos:
```shell
wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
```

Abrimos el archivo de captura con `WireShark`:
```shell
wireshark capture.pcap &>/dev/null &disown
```

Vemos que el trafico esta encriptado.
Lo que realizamos es usar la llave que nos dan(segundo archivo) para desencriptarlo:
- Edit
	- Preferencias
		- Protocols
			- TLS
Y agregamos el archivo.

Después de ahí, vamos a seguir el trafico de TLS y encontramos la bandera:
```flag
picoCTF{nongshim.shrimp.crackers}
```

### Notas adicionales
### Referencias

