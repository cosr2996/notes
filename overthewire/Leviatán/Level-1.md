# Level-0 -> Level-1
### Credentials

```
host: leviathan0@leviathan.labs.overthewire.org  -p 2223
pass: leviathan0
```
### Solution

```shell
leviathan0@gibson:~$ ls
leviathan0@gibson:~$ ls -la
total 24
drwxr-xr-x  3 root       root       4096 Apr 23 18:04 .
drwxr-xr-x 83 root       root       4096 Apr 23 18:06 ..
drwxr-x---  2 leviathan1 leviathan0 4096 Apr 23 18:04 .backup
-rw-r--r--  1 root       root        220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root       root       3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root       root        807 Jan  6  2022 .profile
leviathan0@gibson:~$ cd .backup/
leviathan0@gibson:~/.backup$ ls
bookmarks.html
leviathan0@gibson:~/.backup$ grep leviathan1 bookmarks.html 
<DT><A HREF="http://leviathan.labs.overthewire.org/passwordus.html | This will be fixed later, the password for leviathan1 is PPIfmI1qsA" ADD_DATE="1155384634" LAST_CHARSET="ISO-8859-1" ID="rdf:#$2wIU71">password to leviathan1</A>
leviathan0@gibson:~/.backup$ 
```
### Summary

### FLAG
**PPIfmI1qsA** 
