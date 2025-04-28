## Reto: shark on wire 2
### Descripción
Encontramos esto [captura de paquetes](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recupere la bandera que fue robada de la red.
### Solución 
Descargamos el archivo y vemos que es una captura de paquetes como `wireshark`.
```shell
 wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
```

Vemos los grupos de paquetes, así que tomamos uno de los primeros paquetes UDP, y vamos al primer string, y en el paquete 32 esta la palabra `start`, notamos que el puerto origen es el 5000 y el destino el 22, con una longitud de 5


Al llegar al paquete 60, vemos que se encuentra la palabra `end`. Ambos comparten como puerto destino el 22. 

Así que filtramos todos los paquetes cuyo puerto destino es el 22.

Vemos que el puerto origen va variando y si con ayuda de python vemos el numeor de paquetes, vemos que es la bandera codificada.

Hacemos el siguiente truco para no estar realizando operacion de puerto en puerto.
Instalamos `scapy`:
```python
python3 -m pip install scapy
```

Creamos el siguiente script para poder filtrar cada paquete y que nos regrese la bandera:
```python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''
for p in packets:
	if UDP in p and p[UDP].dport == 22:
		flag += chr(p[UDP].sport - 5000)
print(flag)
```

Y al ejecutarlo nos regresa la bandera:
```python
python3 exp.py
```

Bandera:
```flag
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```





### Notas adicionales
### Referencias

 
