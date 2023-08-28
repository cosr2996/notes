### Level Goat
Puede que sudo te ayude para ser natalia.
### User
**anna**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
anna@venus:~$  sudo -l
Matching Defaults entries for anna on venus:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin, use_pty

User anna may run the following commands on venus:
    (natalia) NOPASSWD: /bin/bash
anna@venus:~$ sudo -u natalia
usage: sudo -h | -K | -k | -V
usage: sudo -v [-ABkNnS] [-g group] [-h host] [-p prompt] [-u user]
usage: sudo -l [-ABkNnS] [-g group] [-h host] [-p prompt] [-U user] [-u user] [command [arg ...]]
usage: sudo [-ABbEHkNnPS] [-r role] [-t type] [-C num] [-D directory] [-g group] [-h host] [-p prompt] [-R directory]
            [-T timeout] [-u user] [VAR=value] [-i | -s] [command [arg ...]]
usage: sudo -e [-ABkNnS] [-r role] [-t type] [-C num] [-D directory] [-g group] [-h host] [-p prompt] [-R directory]
            [-T timeout] [-u user] file ...
anna@venus:~$ sudo -u natalia bash
natalia@venus:/pwned/anna$ cd ..
natalia@venus:/pwned$ cd natalia/
natalia@venus:~$ cat flagz.txt
8===JWHa1GQq1AYrBWNXEJrH===D~~
```
### Summary

El comando `sudo -l` es utilizado en sistemas operativos basados en Unix para listar los permisos que un usuario tiene para ejecutar comandos como superusuario o como otro usuario. El comando `-l` es una abreviatura de “list” y se utiliza para listar los permisos de un usuario. Si se ejecuta el comando `sudo -l` sin argumentos, se mostrará una lista de los comandos que el usuario puede ejecutar con `sudo`. [Si se especifica un comando después del argumento `-l`, se mostrarán los permisos del usuario para ese comando en particular](https://www.neoguias.com/que-es-sudo-en-linux/)

El comando `sudo -u` se utiliza en sistemas operativos basados en Unix para ejecutar un comando como otro usuario. El argumento `-u` se utiliza para especificar el nombre de usuario o el ID de usuario del usuario que se utilizará para ejecutar el comando.

comando `bash` se utiliza para iniciar un shell de Bash. Al ejecutar este comando, se iniciará un shell de Bash con los permisos del usuario `natalia`