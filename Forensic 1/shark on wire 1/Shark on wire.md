## Reto: Shark on wire
### Descripción
Encontramos esto [captura de paquetes](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recuperar la bandera.
### Solución
- Descargamos el archivo
```shell
wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
```

Ahora podemos ver que tenemos que utilizar `WireShark`, kali tiene uno incluido, asi que abrimos este archivo:
```shell
wireshark capture.pcap
```
Tenemos que analizar que archivo pueda tener la bandera, iniciamos con un protocolo `UDP` con los siguientes pasos:
- `click izquierdo` 
- `Follow`
- `UDP stream`
Ahora se nos abre una ventana y sobre el apartado de `stream` vamos buscando y vemos que en el `stream 6` se encuentra la bandera:
```flag
picoCTF{StaT31355_636f6e6e}
```
### Notas adicionales
### Referencias

