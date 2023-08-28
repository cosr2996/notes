### Level Goat
La usuaria mia ha dejado su password en el fichero -.
### User
**emma**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
emma@venus:~$ ls -la
total 36
-rw-r----- 1 root emma   16 Jul 26 08:53 -
drwxr-x--- 2 root emma 4096 Jul 26 08:53 .
drwxr-xr-x 1 root root 4096 Jul 26 08:53 ..
-rw-r--r-- 1 emma emma  220 Apr 23 21:23 .bash_logout
-rw-r--r-- 1 emma emma 3526 Apr 23 21:23 .bashrc
-rw-r--r-- 1 emma emma  807 Apr 23 21:23 .profile
-rw-r----- 1 root emma   31 Jul 26 08:53 flagz.txt
-rw-r----- 1 root emma  170 Jul 26 08:53 mission.txt
emma@venus:~$ cat ./-
iKXIYg0pyEH2Hos
emma@venus:~$ su mia
Password:
mia@venus:/pwned/emma$ cd ..
mia@venus:/pwned$ cd mia/
mia@venus:~$ cat flagz.txt
8===FBMdY8hel2VMA3BaYJin===D~~
mia@venus:~$
```
### Summary
para este nivel tenemos que leer un archivo con un nombre especial para ello podemos usar ./
Tambien se puede usar <