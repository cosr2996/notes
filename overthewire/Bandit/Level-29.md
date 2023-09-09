# Level-28 -> Level-29

### Level Goat
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.
### Credentials
ssh bandit28@bandit.labs.overthewire.org -p 2220
password: **AVanL161y9rsbcJIsFHuw35rjaOM19nR**
### Solution
```shell
bandit28@bandit:/$ mkdir /tmp/gohan
bandit28@bandit:/$ cd /tmp/gohan
bandit28@bandit:/tmp/gohan$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames
'
bandit28-git@localhosts password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.

bandit28@bandit:/tmp/gohan$ ls
repo
bandit28@bandit:/tmp/gohan$ cd repo/
bandit28@bandit:/tmp/gohan/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Sep  9 02:55 .
drwxrwxr-x 3 bandit28 bandit28 4096 Sep  9 02:54 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Sep  9 02:55 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Sep  9 02:55 README.md
bandit28@bandit:/tmp/gohan/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/gohan/repo$ git log -p
commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx


commit abcff758fa6343a0d002a1c0add1ad8c71b88534
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
bandit28@bandit:/tmp/gohan/repo$
```
### Summary
clonamos el repositorio con ssh vemos que esta vez el README  no contiene la constraseña , asi que vemos el historial de commit que se han echo y usamos la opcion -p para que nos muestre los cambios que se hicieron 

[El comando **git log -p** muestra el historial de confirmaciones con las diferencias introducidas en cada una de ellas](https://www.bing.com/search?pglt=161&q=retos+bandit+nivel+28&cvid=77ce20734a8e42bf8dada50236a4046e&aqs=edge..69i57j69i64.7412j0j1&FORM=ANNTA1&PC=EDGEDBB&ntref=1&showconv=1#)[1](https://www.atlassian.com/es/git/tutorials/git-log)[2](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Ver-el-Historial-de-Confirmaciones). Es útil para ver los cambios que se han hecho en los archivos modificados por cada confirmación
### FLAG
**tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S** 