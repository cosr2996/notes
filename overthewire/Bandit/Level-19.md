# Level-18 -> Level-19

### Level Goat
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
### Credentials
ssh bandit18@bandit.labs.overthewire.org -p 2220
password: **hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg**
### Solution
```shell
┌──(root㉿docker-desktop)-[/home/reto]
└─# nano pass.txt

┌──(root㉿docker-desktop)-[/home/reto]
└─# sshpass -f pass.txt ssh bandit18@bandit.labs.overthewire.org -p 2220 "/bin/bash"
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

ls
readme
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```
### Summary
al ingresar al servidor este nos saca por una configuración que tiene bashrc ,pero nosotros ya sabermos que la contraseña se encuentra en el archivo readme asi que usmaos el comando sshpass para espesificarle la contraseña que guardamos en un archivo y al ultimo del comando inyectamos una orden que nos inicia un bash donde podemos hacer cosas basicas alli leemos el arhcivo readme
### FLAG
**awhqfNnAbc1naukrpqDYcF95h7HoMTrC** 