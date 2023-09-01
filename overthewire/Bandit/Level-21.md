# Level-20 -> Level-21

### Level Goat

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
### Credentials
ssh bandit20@bandit.labs.overthewire.org -p 2220
password: **VxCazJaVykI6W36BkBU0mJTCM8rR95XT**
### Solution
```shell
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Apr 23 18:04 suconnect
bandit20@bandit:~$ nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3759535
bandit20@bandit:~$ Listening on 0.0.0.0 3030
jobs
[1]+  Running                 nc -lvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ./suconnect 3030
Connection received on 127.0.0.1 56710
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$
```
### Summary

El comando `nc` es una herramienta de red que se utiliza para leer y escribir datos a través de conexiones de red. El comando `nc -l` se utiliza para escuchar conexiones entrantes en un puerto específico. El argumento `-p` se utiliza para especificar el número de puerto en el que se escucharán las conexiones entrantes. El argumento `-v` se utiliza para habilitar la salida detallada.
el `&` es para que se ejecute en segundo plano.

En este caso, el comando `nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &` escuchará las conexiones entrantes en el puerto 3030 y enviará la cadena `VxCazJaVykI6W36BkBU0mJTCM8rR95XT` a cualquier cliente que se conecte.
### FLAG
**NvEJF7oVjkddltPSrdKEFOllh9V1IBcq** 