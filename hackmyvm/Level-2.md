
### Level Goat
La usuaria angela ha guardado su password en un fichero pero no recuerda donde... solo recuerda que el fichero se llamaba whereismypazz.txt
### User
sophia
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
sophia@venus:~$ find / -name "whereismypazz.txt" -type f 2>/dev/null
/usr/share/whereismypazz.txt
sophia@venus:~$ cat /usr/share/whereismypazz.txt
oh5p9gAABugHBje
sophia@venus:~$ su angela
Password:
angela@venus:/pwned/sophia$ cd ..
angela@venus:/pwned$ cd angela/
angela@venus:~$ cat flagz.txt
8===SjMYBmMh4bk49TKq7PM8===D~~
angela@venus:~$

```
### Summary
usamos el comando file para buscar desde la raiz con la opcion -name para buscar por nombre y la opcion -type para indicar que se trata de un archivo y por ultimo redirigimos los errores de accesio con 2>/dev/null
