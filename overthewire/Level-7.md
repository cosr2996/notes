# Level-6 -> Level-7

### Level Goat
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
### Credentials
ssh bandit6@bandit.labs.overthewire.org -p 2220
password: **P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU**
### Solution
```js
bandit6@bandit:~$ ls
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
### Summary
usamos el comando find para buscar en directorio raíz /
le indicamos que es un archivo lo que buscamos  **-type f**
le indicamos el el usuario que es dueño  **-user bandit7**
le indicamos el grupo al que pertenece **-group bandit6**
indicamos el tamaño -size 33c
como estamos ejecutando este comando desde el directorio raíz nos saldrá multiples errores de error por acceso denegado , para ocultar esos errores  agregamos **2>/dev/null**
### FLAG
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S 