# Level-8 -> Level-9

### Level Goat
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
### Credentials
ssh bandit8@bandit.labs.overthewire.org -p 2220
password: **TESKZC0XvTetK0S9xNwm25STk5iWrBvP**
### Solution
```shell
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$ 
```
### Summary
`uniq`es un comando que filtra la entrada y escribe en la salida. En concreto, filtra en función de líneas idénticas. Tiene una bandera `-u`, que filtra por líneas únicas (líneas que aparecen solo unas). Otra funcionalidad interesante es, por ejemplo, que también puede contar ( `-c`) o solo devolver líneas duplicadas ( `-d`).

El comando se usa a menudo con `sort`. Para `uniq`filtrar por líneas únicas, las líneas deben ordenarse. `sort`ordena las líneas de un archivo de texto. Además, tiene banderas para ordenar en reversa ( `-r`) y ordenar numéricamente ( `-n`).
### FLAG
**EN632PlfYiZbn3PhVK3XOGSlNInNE00t** 