# Level-7 -> Level-8

### Level Goat
The password for the next level is stored in the file **data.txt** next to the word **millionth**
### Credentials
ssh bandit7@bandit.labs.overthewire.org -p 2220
password: **z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**
### Solution
```shell
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep "millionth" data.txt 
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
### Summary
usamos el comando grep para poder buscar una palabra dentro de un archivo de texto 
### FLAG
**TESKZC0XvTetK0S9xNwm25STk5iWrBvP** 