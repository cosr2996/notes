### Level Goat
La usuaria eleanor ha dejado su password en un fichero que ocupa 6969 bytes.
### User
**luna**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
luna@venus:~$ find / -type f -size 6969c 2</dev/null
/usr/share/moon.txt
luna@venus:~$ cat /usr/share/moon.txt
UNDchvln6Bmtu7b
luna@venus:~$ su eleanor
Password:
eleanor@venus:/pwned/luna$ cd ..
eleanor@venus:/pwned$ cd eleanor/
eleanor@venus:~$ cat flagz.txt
8===Iq5vbyiQl4ipNrLDArjD===D~~
eleanor@venus:~$
```
### Summary

usamos el comando find para poder buscar un archivo con un tamaño especifico en bytes
