### Level Goat
The password of the user ariel is online! (HTTP)
### User
**alexa**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
alexa@venus:~$ ls -la
total 32
drwxr-x--- 2 root  alexa 4096 Jul 26 08:53 .
drwxr-xr-x 1 root  root  4096 Jul 26 08:53 ..
-rw-r--r-- 1 alexa alexa  220 Apr 23 21:23 .bash_logout
-rw-r--r-- 1 alexa alexa 3526 Apr 23 21:23 .bashrc
-rw-r--r-- 1 alexa alexa  807 Apr 23 21:23 .profile
-rw-r----- 1 root  alexa   31 Jul 26 08:53 flagz.txt
-rw-r----- 1 root  alexa  172 Jul 26 08:53 mission.txt
alexa@venus:~$ cat mission.txt 
################
# MISSION 0x26 #
################

## EN ##
The password of the user ariel is online! (HTTP)

## ES ##
El password de la usuaria ariel esta online! (HTTP)
alexa@venus:~$ 
alexa@venus:~$ curl localhost
33EtHoz9a0w2Yqo
alexa@venus:~$ su ariel
Password: 
ariel@venus:/pwned/alexa$ cd ~
ariel@venus:~$ cat flagz.txt 
8===lqTeJ1msxhNjNJCptxmZ===D~~
ariel@venus:~$ 



```
### Summary

El comando "curl localhost" en Linux se utiliza para realizar una solicitud HTTP GET al servidor local (localhost) en el puerto 80.

Cuando se ejecuta este comando, [curl](https://www.google.com/search?q=curl) enviará una solicitud GET al servidor local y recibirá la respuesta del servidor. Dependiendo de la configuración del servidor y los recursos en el localhost, la respuesta puede ser una página web, datos JSON, archivos u otra información que el servidor esté configurado para devolver en respuesta a una solicitud GET.

El comando [curl](https://www.google.com/search?q=curl) es una herramienta de línea de comandos que permite realizar solicitudes HTTP y obtener respuestas desde una variedad de servidores. Al especificar "localhost" como el destino, le estás diciendo a [curl](https://www.google.com/search?q=curl) que realice la solicitud al servidor local en tu propia máquina.

Es importante tener en cuenta que el resultado de ejecutar "curl localhost" puede variar dependiendo de la configuración y los servicios que se estén ejecutando en tu localhost. Si no hay un servidor web configurado en el puerto 80 de tu localhost, es posible que obtengas un error o una respuesta vacía.