# Level-19 -> Level-20

### Level Goat
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
### Credentials
ssh bandit19@bandit.labs.overthewire.org -p 2220
password: **awhqfNnAbc1naukrpqDYcF95h7HoMTrC**
### Solution
```shell
bandit19@bandit:~$ ls -l
total 16
-rwsr-x--- 1 bandit20 bandit19 14876 Apr 23 18:04 bandit20-do
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
### Summary

En Linux, el bit `setuid` es un permiso especial que se puede establecer en un archivo ejecutable. Cuando se establece este permiso, el archivo se ejecuta con los permisos del propietario del archivo en lugar de los permisos del usuario que lo ejecuta.

El bit `setuid` es útil para permitir que los usuarios ejecuten programas con permisos elevados sin tener que otorgarles permisos de administrador. Sin embargo, también puede ser peligroso si se usa incorrectamente, ya que puede permitir que los usuarios ejecuten código malicioso con permisos elevados.

### FLAG
**VxCazJaVykI6W36BkBU0mJTCM8rR95XT** 