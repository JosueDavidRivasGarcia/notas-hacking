## Reto: Specialer
### Descripción
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.`ssh -p 64026 ctf-player@saturn.picoctf.net`. The password is `3f39b042`
### Solución
Iniciamos estableciendo la conexión a través de ssh con el servidor proporcionado en la descripción del desafío una vez que se inicio la instancia:
```shell
ssh -p 64026 ctf-player@saturn.picoctf.net
```

Se inicia probando comandos básicos, pero no nos arrojan el resultado esperado, por lo que se procede a consultar la ayuda con el comando help:
```shell
help
```

Revisado el manual, descubrimos que para consultar el contenido de un archivo se hace de la forma en que se muestra a continuación:
```shell
echo */*
```

Una vez que se probaron los archivos uno por uno, encontramos uno que nos muestra lo siguiente:
```shell
echo "$(<abra/cadaniel.txt)"
```

```shell
echo "$(<ala/kazam.txt)"
```

Y obtenemos la bandera:
```flag
picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_811ae7e9}
```

Dándonos la bandera que soluciona a este reto:

### Notas adicionales
### Referencias

 
