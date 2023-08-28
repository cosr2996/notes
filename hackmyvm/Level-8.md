### Level Goat
La usuaria victoria ha dejado su password en un fichero en el cual el propietario es el usuario violin.
### User
**eleanor**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
eleanor@venus:~$ find / -user violin -type f 2</dev/null
/usr/local/games/yo
eleanor@venus:~$ cat /usr/local/games/yo
pz8OqvJBFxH0cSj
eleanor@venus:~$ su victoria
Password:
victoria@venus:/pwned/eleanor$ cd ..
victoria@venus:/pwned$ cd victoria/
victoria@venus:~$ cat flagz.txt
8===NWyTFi9LLqVsZ4OnuZYN===D~~
victoria@venus:~$
```
### Summary
usamos nuevamente el comando find y esta vez con la opcion -user para indicar el usuario dueño del archivo
