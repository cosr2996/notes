### Level Goat
The user iris has left me her key.
### User
**eliza**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
eliza@venus:~$ ls
flagz.txt  mission.txt
eliza@venus:~$ cat mission.txt 
################
# MISSION 0x20 #
################

## EN ##
The user iris has left me her key.

## ES ##
La usuaria iris me ha dejado su key.
eliza@venus:~$ ls -la
total 36
drwxr-x--- 2 root  eliza 4096 Jul 26 08:54 .
drwxr-xr-x 1 root  root  4096 Jul 26 08:53 ..
-rw-r--r-- 1 eliza eliza  220 Apr 23 21:23 .bash_logout
-rw-r--r-- 1 eliza eliza 3526 Apr 23 21:23 .bashrc
-rw-r----- 1 root  eliza 2602 Jul 26 08:54 .iris_key
-rw-r--r-- 1 eliza eliza  807 Apr 23 21:23 .profile
-rw-r----- 1 root  eliza   31 Jul 26 08:53 flagz.txt
-rw-r----- 1 root  eliza  143 Jul 26 08:53 mission.txt
eliza@venus:~$ ssh -i .iris_key iris@localhost
iris@venus:~$ ls
eloise  flagz.txt  irispass.txt  mission.txt
iris@venus:~$ cat flagz.txt 
8===ClrdWOqlZ1vL61zSk9Va===D~~
iris@venus:~$ 

```
### Summary

debido a que tenemos la clave ssh para el usuario iris solo tenemos que usarla para logeralos como iris y como ya estamos dentro del servidor usamos localhost