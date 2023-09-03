### Level Goat
The password of the user freya is the only string that is not repeated in different.txt 

### User
**isabel**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
isabel@venus:~$ ls
different.txt  flagz.txt  mission.txt

isabel@venus:~$ uniq -u different.txt 
EEDyYFDwYsmYawj
isabel@venus:~$ su freya
Password: 
freya@venus:/pwned/isabel$ cd ..
freya@venus:/pwned$ cd freya
freya@venus:~$ cat flagz.txt 
8===m1rRSv2pdm3sBGmgidul===D~~
freya@venus:~$ 

```
### Summary

usamos el comando uniq con la opción -u para que nos muestre las líneas que no se repiten 