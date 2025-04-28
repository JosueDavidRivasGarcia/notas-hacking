## Reto: m00nwalk
### Descripción
Decodificar esto [mensaje](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) de la luna.
### Solución 
Descargamos el archivo
```shell
wget https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
```

Tenemos 2 pistas, una dice, como las imágenes de la luna llegaron de regreso a la tierra y otra dice cual es el nombre de la mascota de CMU universidad, tal vez puede ayudarte al seleccionar la opción RX.

Vamos a examinar que formato tiene el archivo y vemos que es de audio.
Al buscar como llegaron las imágenes, vemos que viajo a manera de audio y se decodificaba, así que buscaremos un decodificador en linea.

Al encontrar uno en GitHub hacemos lo siguiente:
Entrar a la carpeta opt:
```shell
cd /opt
```
Instalar la herramienta sstv:
```shell
sudo git clone https://github.com/colaclanth/sstv.git
```
Instalar el setup de python:
```shell
sudo python setup.py install
```
Checar la ayuda:
```shell
 sstv --help
```

Y ahora regresamos a la carpeta en donde se encuentra este reto, y hacemos lo siguiente:
```shell
sstv -d message.wav -o result.png
```

Esto decodificare el mensaje de audio en imagen, la cual se encuentra en esta carpeta.
```flag
picoCTF{beep_boop_im_in_space}
```


### Notas adicionales 
### Referencias

 
