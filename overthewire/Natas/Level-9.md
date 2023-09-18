# Level-8 -> Level-9

### Credentials

```
Username: natas9
Password: Sda6t0vkOPkM8YeOZkAGVhFoaplvlJFd
URL:      http://natas9.natas.labs.overthewire.org
```
### Solution

![[2023-09-17-20^%09^%42-screenshot.png]]
![[2023-09-17-20^%54^%04-screenshot.png]]
![[2023-09-17-20^%58^%05-screenshot.png]]
### Summary

en este reto se nos da acceso al código fuente , vemos que esa una función de php la función passthru que permite ejecutar comandos igual que las funciones `exec` y `system`. que lo que hace es ejecutar el comando grep con la cadena que le demos si que podemos inyectar el siguiente texto **; cat /etc/natas_webpass/natas10** que lo que hace es cerrar el grep y concatena el comando cat que nos muestra la bandera
### FLAG
**D44EcsFkLxPIkAAKLosx8z3hxX1Z4MCE** 