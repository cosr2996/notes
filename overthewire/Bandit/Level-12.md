# Level-11 -> Level-12

### Level Goat
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
### Credentials
ssh bandit11@bandit.labs.overthewire.org -p 2220
password: **6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**
### Solution
```shell
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$ 

```
### Summary
Rot13 es una forma de cifrado donde cada letra se recorre 13 posiciones para poder decifrarlo primero leemos el archivo con cat y eso lo desiframos con el comando tr e indicandole la forma en la que se recorren las letras

![[ROT13_table_with_example.svg]]
### FLAG
**JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv** 