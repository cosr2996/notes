# Level-5 -> Level-6

### Level Goat
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
### Credentials
ssh bandit5@bandit.labs.overthewire.org -p 2220
password: **lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR**
### Solution
```shell
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ find -readable -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
bandit5@bandit:~/inhere$ 

```
### Summary
usamos el comando find para buscar el archivo con las características que se nos indico ,
con -**readable** checamos que sea legible después indicamos el peso con **-size**
(- b – 512-byte blocks (this is the default if no suffix is used)
- c – bytes
- w – two-byte words
- k – Kilobytes
- M – Megabytes
- G – Gigabytes)
y por ultimo que sea ejecutable pero como queremos lo contrario negamos el resultado
**! -executable**
### FLAG
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU 