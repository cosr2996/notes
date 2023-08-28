### Level Goat
Parece que la usuaria camila ha dejado su password dentro de una carpeta llamada hereiam
### User
**mia**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
mia@venus:~$ find / -name hereiam -type d 2</dev/null
/opt/hereiam
mia@venus:~$ cd /opt/hereiam/
mia@venus:/opt/hereiam$ ls -la
total 12
drwxr-xr-x 2 root root 4096 Jul 26 08:53 .
drwxr-xr-x 1 root root 4096 Jul 26 08:53 ..
-rw-r--r-- 1 root root   16 Jul 26 08:53 .here
mia@venus:/opt/hereiam$ cat .here
F67aDmCAAgOOaOc
mia@venus:/opt/hereiam$
mia@venus:/opt/hereiam$ su camila
Password:
camila@venus:/$ cd pwned/camila/
camila@venus:~$ cat flagz.txt
8===iDIi5sm1mDuqGmU5Psx6===D~~
camila@venus:~$
```
### Summary

