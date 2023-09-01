# Level-25 -> Level-26

### Level Goat
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.
### Credentials
ssh bandit25@bandit.labs.overthewire.org -p 2220
password: **p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d**
### Solution
```shell
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220

  _                     _ _ _   ___   __  
 | |                   | (_) | |__ \ / /  
 | |__   __ _ _ __   __| |_| |_   ) / /_  
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \ 
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
 |_.__/ \__,_|_| |_|\__,_|_|\__|____\___/ 
Connection to localhost closed.
'
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
bandit25@bandit:~$ 
bandit25@bandit:~$ 
```


### Summary
`more`es un filtro para hojear texto una pantalla a la vez. Con el comando `v`podemos iniciar un editor en la línea actual. El editor se toma de la variable de entorno VISUAL si está definido, o EDITOR si VISUAL no está definido, o por defecto es vi si no están definidos ni VISUAL ni EDITOR.

Para habilitarlo `more`tenemos que disminuir el tamaño de la ventana de nuestra terminal.

- para este nivel tenemos que desencadenar more que solo pasara si tenemos un lugar reducido , por eso hacemos pequeña la terminal 
- more nos deja meter comandos para ello tenemos que usar vi y dentro de vi podremos lanzar otros comandos
- entre esos esta read el cual se desencadena con r que funciona como si fuera un cat 
![[Screenshot 2023-08-31 165815.png]]
- usamos la tecla **v** para lanzar vi 
![[Screenshot 2023-08-31 165828 1.png]]
- nos ponemos en la ultima Linea fuera del texto y ponemos **:**
![[Screenshot 2023-08-31 170409.png]]
- lanzamos el comando read con r que funciona de la misma manera que un cat 
![[Screenshot 2023-08-31 170433 1.png]]
- nos imprime la contraseña
![[Screenshot 2023-08-31 171138.png]]
### FLAG
**c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1** 