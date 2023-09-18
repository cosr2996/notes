# Level-5 -> Level-6

### Credentials

```
Username: natas6
Password: fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR
URL:      http://natas6.natas.labs.overthewire.org
```
### Solution
vemos que nos da la opción de ver el Código fuente 
![[2023-09-17-19^%17^%20-screenshot.png]]
viendo el código vemos que usan la función include de php
![[2023-09-17-19^%17^%29-screenshot.png]]
entramos a la dirección que tiene la función include
![[2023-09-17-19^%25^%57-screenshot.png]]
vemos que sale una pagina en blanco , pero si las inspeccionamos encontramos el valor de la variable secret
![[2023-09-17-19^%26^%04-screenshot.png]]
ponemos el valor de la variable en el input y nos da la bandera
![[2023-09-17-19^%26^%26-screenshot 1.png]]
### Summary

### FLAG
**jmxSiH3SP6Sonf8dv66ng8v1cIEdjXWr** 