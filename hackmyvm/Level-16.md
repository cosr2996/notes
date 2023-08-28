### Level Goat
El password de eva esta encodeado en el fichero base64.txt
### User
**natalia**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
natalia@venus:~$ base64 -d base64.txt
upsCA3UFu10fDAO
natalia@venus:~$ su eva
Password:
eva@venus:/pwned/natalia$ cd ..
eva@venus:/pwned$ cd eva
eva@venus:~$ cat flagz.txt
8===22cqk3iGkGYVqnYrHiof===D~~
eva@venus:~$
```
### Summary

El comando `base64` en Linux es una herramienta de codificación que se utiliza para convertir datos binarios en texto ASCII. El comando toma datos binarios como entrada y los convierte en una cadena de caracteres ASCII que se puede imprimir.