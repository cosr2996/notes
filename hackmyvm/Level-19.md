### Level Goat
La password de eliza es el unico string que se repite (sin estar ordenado) en repeated.txt.
### User
**frida**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
frida@venus:~$ ls
flagz.txt  mission.txt  repeated.txt
frida@venus:~$ uniq -d repeated.txt
eb5467ab16852b1
Fg6b6aoksceQqB9
frida@venus:~$ su eliza
Password:
su: Authentication failure
frida@venus:~$ su eliza
Password:
eliza@venus:/pwned/frida$ cd ..
eliza@venus:/pwned$ cd eliza/
eliza@venus:~$ cat flagz.txt
8===zwWIPyDf2ozwVhCTxm1I===D~~
eliza@venus:~$
```
### Summary

para este reto usamos el comando uniq que nos muestra las lineas no repetidas de un archivo pero si lo acompañamos de la opcion -d nos muestra las lineas que se repiten solo una vez ,tambien esta la opcion -D que nos muestra las lineas repetidas y cuantas veces se repiten 

esto nos arroja dos resultados , calamos las dos .