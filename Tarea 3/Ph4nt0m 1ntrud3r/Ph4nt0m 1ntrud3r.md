## Reto: Ph4nt0m 1ntrud3r
### Descripción:
¡Un fantasma digital ha violado mis defensas y mis datos confidenciales han sido robados! 😱💻 Tu misión es descubrir cómo este intruso fantasma se infiltró en mi sistema y recuperar la bandera oculta.Para resolver este desafío, deberá analizar el archivo PCAP proporcionado y rastrear el método de ataque. El atacante ha ocultado hábilmente sus movimientos de manera oportuna. ¡Sumérgete en el tráfico de la red, aplica los filtros correctos y muestra tu destreza forense y desenmascara al intruso digital!Encuentra el archivo PCAP aquí [Archivo PCAP de tráfico de red](https://challenge-files.picoctf.net/c_verbal_sleep/a681faccaaa199ce75c3abeef9525f813b6451644a8d8d27cc097e4b1ccb741a/myNetworkTraffic.pcap) y trata de conseguir la bandera.
### Solución

Primero descargamos el archivo:
```shell
wget https://challenge-files.picoctf.net/c_verbal_sleep/a681faccaaa199ce75c3abeef9525f813b6451644a8d8d27cc097e4b1ccb741a/myNetworkTraffic.pcap
```

Ahora abrimos el archivo y podemos ver que es una captura de paquetes, que están codificados en base 64, por lo que serán los paquetes con longitud 4 y 12. Así que aplicamos el filtro.
```shell
tcp.len == 4  || tcp.len == 12
```

Ahora que tenemos los paquetes filtrados, al hacer clic copiamos su cadena codificada y juntamos cada una de ellas, quedando de la siguiente manera:
```css
cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfZA==MTA2NTM4NA==fQ==
```

Y si lo pasamos al `cyberchef` nos regresa la bandera:
```flag
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_d1065384}
```

### Notas adicionales
### Referencias

