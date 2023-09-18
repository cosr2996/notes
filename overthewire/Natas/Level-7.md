# Level-6 -> Level-7

### Credentials

```
Username: natas7
Password: jmxSiH3SP6Sonf8dv66ng8v1cIEdjXWr
URL:      http://natas7.natas.labs.overthewire.org
```
### Solution

![[2023-09-17-19^%34^%25-screenshot.png]]
![[2023-09-17-19^%35^%28-screenshot.png]]
![[2023-09-17-19^%36^%02-screenshot.png]]
![[2023-09-17-19^%36^%32-screenshot.png]]
![[2023-09-17-19^%36^%34-screenshot.png]]

### Summary

Si hacemos clic en algunos de los enlaces, podemos ver que se construye una URL del tipo `http://natas7.natas.labs.overthewire.org/index.php?**page=home**` donde cada página es llamada mediante la función include de PHP que vimos en el reto anterior.

En las instrucciones iniciales del reto, se indica que las claves de cada nivel están almacenadas en la ruta `/etc/natas_webpass/natas_nivel` del servidor.
### FLAG
**a6bZCNYwdKqN5cGP11ZdtPg0iImQQhAB ** 