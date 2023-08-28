### Level Goat
El admin ha dejado la password de anna como comentario en el fichero passwd.
### User
**alice**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
alice@venus:~$ cat /etc/passwd | grep alice
alice:x:1014:1014:w8NvY27qkpdePox:/pwned/alice:/bin/bash
alice@venus:~$ su anna
Password:
anna@venus:/pwned/alice$ cd ..
anna@venus:/pwned$ cd anna
anna@venus:~$ cat flagz.txt
8===5Y3DhT66fa6Da8RpLKG0===D~~
anna@venus:~$
```
### Summary
El archivo `passwd` es un archivo de sistema en Linux que almacena información sobre los usuarios del sistema . Este archivo se utiliza para almacenar información como el nombre de usuario, la contraseña cifrada, el ID de usuario y el directorio de inicio del usuario .

El archivo `passwd` se encuentra en el directorio `/etc` y solo puede ser accedido por el usuario root o por un usuario con permisos de administrador . El archivo `passwd` es utilizado por muchos programas y servicios en Linux para autenticar a los usuarios y controlar el acceso a los recursos del sistema .
