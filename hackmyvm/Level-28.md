### Level Goat
The user celeste has left a list of names of possible .html pages where to find her password. 
### User
**lola**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
lola@venus:~$ find /var/www/html "*.html" 2>/dev/null
/var/www/html
/var/www/html/key.php
/var/www/html/cebolla.html
/var/www/html/index.nginx-debian.html
/var/www/html/index.html
/var/www/html/waiting.php
/var/www/html/method.php
lola@venus:~$ curl http://127.0.0.1/cebolla.html
VLSNMTKwSV2o8Tn
lola@venus:~$ su celeste
Password: 
celeste@venus:/pwned/lola$ cd 
celeste@venus:~$ cat flagz.txt 
8===TrdsvMy99slFZtd4Cy4Q===D~~
celeste@venus:~$ 


```
### Summary
hacemos un find para buscar los posibles archivos html que hallan , al ser un a pagina que esta funcionando lo mas comun es que este en var/www/html por eso buscamos alli vemos que solo hay dos documentos un index y cebolla , el nombre cebolla lo vimos en la lista de paginas asi que todo pinta a que esa sea la indicada asi que le hacemos un curl y nos da la contrasena 
