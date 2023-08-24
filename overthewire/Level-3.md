# Level-2 -> Level-3

### Level Goat
The password for the next level is stored in a file called **spaces in this filename** located in the home directory
### Credentials
ssh bandit2@bandit.labs.overthewire.org -p 2220
password: **rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi*
### Solution
```js
bandit2@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit3 bandit2 33 Apr 23 18:04 spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ 

```
### Summary
para poder ver lo que contenia el archivo ponemos el nombre entre comillas para evitar el error por los espacios que contiene el nombre
### FLAG
**aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG** 