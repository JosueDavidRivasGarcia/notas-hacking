## Reto: Redaction gone wrong
### Descripción:
Ahora no me ves.Esto [informe](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) tiene algunos datos críticos en él, algunos de los cuales han sido redactados correctamente, mientras que otros no lo fueron. ¿Puedes encontrar una clave importante que no haya sido redactada correctamente?
### Solución
Descargamos el archivo:
```shell
wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
```

Al abrirlo podemos ver que hay un texto cubierto, pero si lo seleccionamos podemos ver que se encuentra la bandera:
```flag
picoCTF{C4n_Y0u_S33_m3_fully}
```


### Notas adicionales
### Referencias

