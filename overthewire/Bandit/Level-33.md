# Level-32 -> Level-33

### Level Goat
After all this `git` stuff its time for another escape. Good luck!
### Credentials
ssh bandit32@bandit.labs.overthewire.org -p 2220
password: **rmCBvG56y58BXzv98yZGdO7ATVL5dW8y**
### Solution
```shell
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> LS
sh: 1: LS: Permission denied
>> $0
$ ls
uppershell
$ whoami
bandit33
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$
```
### Summary
`$0`, nos permite invocar el shell de bash

El shell convierte cada comando a mayúsculas. Necesitamos arreglarlo y recuperar el shell normal. Como se trata de un shell interactivo, tenemos la posibilidad de ejecutarlo nuevamente usando la variable $0.
### FLAG
**odHo63fHiFqcWWJG9rLiLDtPm45KzUKy** 