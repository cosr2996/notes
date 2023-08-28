### Level Goat
La usuaria isla ha dejado su password en un fichero zip.
### User
**victoria**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
victoria@venus:~$ ls
flagz.txt  mission.txt  passw0rd.zip
victoria@venus:~$ unzip passw0rd.zip
Archive:  passw0rd.zip
checkdir error:  cannot create pwned
                 Permission denied
                 unable to process pwned/victoria/passw0rd.txt.
victoria@venus:~$ unzip passw0rd.zip -d /tmp/cosr
Archive:  passw0rd.zip
 extracting: /tmp/cosr/pwned/victoria/passw0rd.txt
victoria@venus:~$ cd /tmp/cosr
victoria@venus:/tmp/cosr$ ls
pwned
victoria@venus:/tmp/cosr$ cd pwned/
victoria@venus:/tmp/cosr/pwned$ ls
victoria
victoria@venus:/tmp/cosr/pwned$ cd victoria/
victoria@venus:/tmp/cosr/pwned/victoria$ ls
passw0rd.txt
victoria@venus:/tmp/cosr/pwned/victoria$ cat passw0rd.txt
D3XTob0FUImsoBb
victoria@venus:/tmp/cosr/pwned/victoria$ su isla
Password:
isla@venus:/tmp/cosr/pwned/victoria$ cd /pwned/isla
isla@venus:~$ cat  flagz.txt
8===ZyZqc1suvGe4QlkZHFlq===D~~
isla@venus:~$
```
### Summary
usamos el comando unzip para extrrar el archivo.zip, al principio da error poque no tenemos permiso de escritura en ese directorio por eso con la opcion -d le decimos donde extraerlo 