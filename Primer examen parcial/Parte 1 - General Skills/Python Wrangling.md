## Reto: Python Wrangling
### Descripción
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py) using [this password](https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt) to get [the flag](https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en)?
### Solución
1. Descargamos los 3 archivos que nos indica el problema
```shell
wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py
wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt
wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en
```
 2. Extraemos lo que hay en flag.txt y pw.txt
```shell
cat flag.txt.en

gAAAAABgUAIWsYfVayn4m1dKle5X91HrZW_MIRAW4ILPgf4gD6jalLF4PysYB5_YTpDwclcQPqw_0xTxanpJ_Urx5Vi6mTeBA_rWPA_WQLvVXXHp1mG3EpOgY8Na1_NIAfc9LceH_L2o
```

```shell
cat pw.txt
67c6cc9667c6cc9667c6cc9667c6cc96
```

 3. Usamos el código en Python para desencriptar la bandera. Para usar el código necesitamos la contraseña en pw
```css
python ende.py -d flag.txt.en
Please enter the password:67c6cc9667c6cc9667c6cc9667c6cc96
```

Y obtenemos la bandera:
```flag
picoCTF{4p0110_1n_7h3_h0us3_67c6cc96}
```
### Notas adicionales
### Referencias

 
