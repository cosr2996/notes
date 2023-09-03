### Level Goat
The user isabel has left her password in a file in the /etc/xdg folder but she does not remember the name, however she has dict.txt that can help her to remember.


### User
**lucia**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
lucia@venus:~$ ls 
dict.txt  flagz.txt  mission.txt
lucia@venus:~$ cat dict.txt 
s
hack
hacker
handler
hanlder
happening
head
header
headers
hello
helloworld
indexes
info
invite
jsps
.
.
.

lucia@venus:~$ for i in `cat dict.txt`; do echo $i; done
s
hack
hacker
handler
hanlder
happening
head
header
headers
hello
.
.
.
lucia@venus:~$ for i in `cat dict.txt`; do ls /etc/xdg/$i; done 2>/dev/null
/etc/xdg/readme

lucia@venus:~$ cat /etc/xdg/readme
H5ol8Z2mrRsorC0
lucia@venus:~$ su isabel
Password: 
isabel@venus:/pwned/lucia$ cd ..
isabel@venus:/pwned$ cd isabel
isabel@venus:~$ cat flagz.txt 
8===Md2CU83GtVfouhm9U0AS===D~~
isabel@venus:~$ 

```
### Summary

vemos que tenemos que encontrar el nombre del archivo en una lista de nombres para eso usamos un siclo for y vemos a cual de los archivos tenemos permiso ya que los demas no nos dejaran listarlos , 