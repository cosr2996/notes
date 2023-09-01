# Level-21 -> Level-22

### Level Goat
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
### Credentials
ssh bandit21@bandit.labs.overthewire.org -p 2220
password: **NvEJF7oVjkddltPSrdKEFOllh9V1IBcq**
### Solution
```shell
bandit21@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-r--------  1 bandit21 bandit21   33 Apr 23 18:04 .prevpass
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit21@bandit:~$ cd /etc/cron.d/
bandit21@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit21@bandit:/etc/cron.d$
```
### Summary
En Linux, `cron` es un servicio que se utiliza para programar tareas en el sistema operativo. Permite a los usuarios programar comandos o scripts para que se ejecuten automáticamente en momentos específicos o en intervalos regulares.

El servicio `cron` se ejecuta en segundo plano y lee un archivo llamado `crontab` que contiene las tareas programadas. Cada línea del archivo `crontab` representa una tarea programada y especifica cuándo y cómo se debe ejecutar la tarea.

Por ejemplo, si desea programar un script para que se ejecute todos los días a las 3:00 a.m., puede agregar una línea al archivo `crontab` que se vea así:

```
0 3 * * * /ruta/al/script.sh
```

Esta línea especifica que el script `/ruta/al/script.sh` debe ejecutarse todos los días a las 3:00 a.m.

En este caso, los valores son `* * * * *`, lo que significa que la tarea se ejecutará cada minuto.
![[Linux-cron-crontab-añadir-tareas-periodicas.webp]]

### FLAG
**WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff** 