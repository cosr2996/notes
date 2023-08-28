### Level Goat
La usuaria sophia ha guardado su contraseña en un fichero oculto en esta carpeta.Encuentralo y logueate como sophia.
### User
hacker
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
hacker@venus:~$ ls -la
total 44
drwxr-x--- 1 root   hacker 4096 Jul 26 08:55 .
drwxr-xr-x 1 root   root   4096 Jul 26 08:53 ..
-rw-r----- 1 root   hacker   31 Jul 26 08:55 ...
-rw-r--r-- 1 hacker hacker  220 Apr 23 21:23 .bash_logout
-rw-r--r-- 1 hacker hacker 3621 Aug 10 14:17 .bashrc
-rw-r----- 1 root   hacker   16 Jul 26 08:53 .myhiddenpazz
-rw-r--r-- 1 hacker hacker  807 Apr 23 21:23 .profile
-rw-r----- 1 root   hacker  287 Jul 26 08:53 mission.txt
-rw-r----- 1 root   hacker 2542 Jul 26 08:53 readme.txt
hacker@venus:~$ cat .myhiddenpazz
Y1o645M3mR84ejc
hacker@venus:~$ su sophia
Password:
sophia@venus:/pwned/hacker$ cd ..
sophia@venus:/pwned$ cd sophia/
sophia@venus:~$ cat flagz.txt
8===LUzzNuv8NB59iztWUIQS===D~~
sophia@venus:~$

```
### Summary

usamos ls -la para mostrar todos los archivos incluidos los ocultos y de forma detallada asi encontramos la contrasena del usuario sophia , con ayuda del comando su cambiamos de usuario y buscamos la bandera.