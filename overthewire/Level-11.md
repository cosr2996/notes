# Level-10 -> Level-11

### Level Goat
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
### Credentials
ssh bandit10@bandit.labs.overthewire.org -p 2220
password: **G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s**
### Solution
```js
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ base64 -d data.txt 
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$ 
```
### Summary
usamos el comando base64 con el parametro -d para decodificar el mensaje
### FLAG
**6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**