# Level-29 -> Level-30

### Level Goat
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
### Credentials
ssh bandit29@bandit.labs.overthewire.org -p 2220
password: **tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S**
### Solution
```shell
bandit29@bandit:~$ mkdir /tmp/piccolo
bandit29@bandit:~$ cd /tmp/piccolo
bandit29@bandit:/tmp/piccolo$



bandit29@bandit:/tmp/piccolo$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames
'
bandit29-git@localhosts password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/piccolo$
bandit29@bandit:/tmp/piccolo$ cd repo
bandit29@bandit:/tmp/piccolo/repo$ ls
README.md
bandit29@bandit:/tmp/piccolo/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/piccolo/repo$





bandit29@bandit:/tmp/piccolo/repo$ git log
commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

commit 1a57cf10158f133c4f40ff82251f605a7618631d
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/piccolo/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/piccolo/repo$  git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/piccolo/repo$ git checkout dev
Already on 'dev'
Your branch is up to date with 'origin/dev'.
bandit29@bandit:/tmp/piccolo/repo$ git branch
* dev
  master
bandit29@bandit:/tmp/piccolo/repo$ git log
commit 13e735685c73e5e396252074f2dca2e415fbcc98 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add data needed for development

commit 8caf551dba9f9e39bc8ea4163de7902e6fa85f3a
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add gif2ascii

commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (origin/master, origin/HEAD, master)
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

commit 1a57cf10158f133c4f40ff82251f605a7618631d
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/piccolo/repo$
bandit29@bandit:/tmp/piccolo/repo$ git show 13e735685c73e5e396252074f2dca2e415fbcc98
commit 13e735685c73e5e396252074f2dca2e415fbcc98 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials

 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/piccolo/repo$

```
### Summary
vemos que el repositorio tiene multiples ramas a si que nos cambiamos a la de desarrollo y y vemos los cimmit realizados  y por ultimo mostramos cada uno de los commits a ver en donde se realizo el cambio de la contrasena

 `git branch -a` podemos ver todas las ramas existentes en el repositorio.
 `git checkout` podemos restaurar o seleccionar una de las ramas existentes.
 `git show` es un comando de Git que se utiliza para mostrar varios tipos de objetos. Puede mostrar uno o más objetos (blobs, árboles, etiquetas y confirmaciones)
### FLAG
**xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS** 