# Level-9 -> Level-10

### Level Goat
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
### Credentials
ssh bandit9@bandit.labs.overthewire.org -p 2220
password: **EN632PlfYiZbn3PhVK3XOGSlNInNE00t**
### Solution
```js
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep ===
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$ 

```
### Summary
usamos el comando string para poder distinguir las cadenas legibles  por humanos , despues concatenamos el resultado con el comando grep para que nos muestre unicamente las lineas que empiecen con mas de un signos de igual
### FLAG
**G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s** 