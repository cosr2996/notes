# Level-9 -> Level-10

### Credentials

```
Username: natas10
Password: D44EcsFkLxPIkAAKLosx8z3hxX1Z4MCE
URL:      http://natas10.natas.labs.overthewire.org
```
### Solution


![[2023-09-17-21^%04^%15-screenshot.png]]
![[2023-09-17-21^%04^%25-screenshot.png]]
![[2023-09-17-21^%05^%10-screenshot.png]]

### Summary
el reto es muy parecido al anterior con la diferencia de que esta vez se prohiben ciertos caracteres como **; y /** así que no podemos usar la anterior solución pero si hacer algo parecido como el siguiente comando **s  /etc/natas_webpass/natas11** 

Pero si le pasamos al input la cadena `s /etc/natas_webpass/natas11` (por ejemplo), estará buscando el contenido de la letra `s` en los ficheros `dictionary.txt` y `/etc/natas_webpass/natas11`, que es donde se encuentra la **contraseña** para acceder al siguiente nivel.
### FLAG
**1KFqoJXi6hRaPluAmk8ESDW4fSysRoIg** 