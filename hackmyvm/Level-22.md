### Level Goat
User lucia has been creative in saving her password.

### User
**eloise**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
eloise@venus:~$ ls -la
total 36
drwxr-x--- 2 root   eloise 4096 Jul 26 08:54 .
drwxr-xr-x 1 root   root   4096 Jul 26 08:53 ..
-rw-r--r-- 1 eloise eloise  220 Apr 23 21:23 .bash_logout
-rw-r--r-- 1 eloise eloise 3526 Apr 23 21:23 .bashrc
-rw-r--r-- 1 eloise eloise  807 Apr 23 21:23 .profile
-rw-r----- 1 root   eloise   31 Jul 26 08:53 flagz.txt
-rw-r----- 1 root   eloise   50 Jul 26 08:54 hi
-rw-r----- 1 root   eloise  194 Jul 26 08:53 mission.txt
eloise@venus:~$ cat mission.txt 
################
# MISSION 0x22 #
################

## EN ##
User lucia has been creative in saving her password.

## ES ##
La usuaria lucia ha sido creativa en la forma de guardar su password.
eloise@venus:~$ cat hi
00000000: 7576 4d77 4644 5172 5157 504d 6547 500a
eloise@venus:~$ xxd -r hi
uvMwFDQrQWPMeGP
eloise@venus:~$ su lucia
Password: 
lucia@venus:/pwned/eloise$ cd ..
lucia@venus:/pwned$ cd lucia
lucia@venus:~$ cat flagz.txt 
8===5Sr2pqeVTmn8RaaPmTPE===D~~

```
### Summary

al ver lo que contiene el archivo hi vemos que se trata de un volcado para ver o que tiene lo transformamos con xxd -r  y eso nos de la contraseña