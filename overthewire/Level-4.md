# Level-3 -> Level-4

### Level Goat
The password for the next level is stored in a hidden file in the **inhere** directory.
### Credentials
ssh bandit3@bandit.labs.overthewire.org -p 2220
password: **aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**
### Solution
```js
bandit3@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  inhere  .profile
bandit3@bandit:~$ cd  inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$ 
```
### Summary
usamos la el parámetro -a con el comando ls para que nos muestre los archivos ocultos
### FLAG
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe