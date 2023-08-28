### Level Goat
La password de la usuaria clara se encuentra en un fichero modificado el 01 de Mayo de 1968.
### User
**eva**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
eva@venus:~$ find / -type f -mtime +19365 2>/dev/null
/usr/lib/cmdo
eva@venus:~$ cat /usr/lib/cmdo
39YziWp5gSvgQN9
eva@venus:~$ su clara
Password:
clara@venus:/pwned/eva$ cd ..
clara@venus:/pwned$ cd clara/
clara@venus:~$ cat flagz.txt
8===EJWmHDEQeEN1vIR7NYiH===D~~
```
### Summary

usamos el comando find con la opcion -mtime que nos dice que archivos han sido modificados en  de n dias , y usamos el simbolo + para decir que liste los que han pasado antes de esos dias , para este reto tuvimos que calcular los dias que havian pasado desde que se modifico el archivo. en etste caso en particualar si buscabamos por los dias exactos no salia nada asi que buscamos de nuevo con un poco mas de olgura dando dos años mas a la fecha que se nos indico de esta forma el calculo quedo de la siguiente manera
(2023-1970)x365=19365