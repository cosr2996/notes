# Level-14 -> Level-15

### Level Goat
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

### Credentials
ssh bandit14@bandit.labs.overthewire.org -p 2220
password: **fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq**

### Solution
```shell
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
### Summary
Localhost es un nombre de host y su dirección IP es '127.0.0.1'. Se utiliza para acceder a los servicios de red en el mismo dispositivo que ejecuta estos servicios.

`nc` o es un comando que permite leer y escribir datos a través de una conexión de red. Se puede utilizar para conexiones TCP y UDP. Para conectarse a un servicio (como cliente) en una red, la sintaxis del comando es la siguiente: . Para crear un servidor que escuche los paquetes entrantes, el comando tiene este aspecto: .`netcat``nc <host> <port>``nc -l <port>`

primero iniciamos sesion en el usuario actual (14) y despues tenemos que enviar la contraseña actual a localhost en el puerto 30000 y esto nos devuelbe la contraseña del siguiente nivel
### FLAG
**jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt** 