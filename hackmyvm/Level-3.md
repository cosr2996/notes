
### Level Goat
La password de la usuaria emma esta en la linea 4069 del fichero findme.txt
### User
angela
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
angela@venus:~$ sed -n '4069p' findme.txt
fIvltaGaq0OUH8O
angela@venus:~$ su emma
Password:
emma@venus:/pwned/angela$ cd ..
emma@venus:/pwned$ cd emma/
emma@venus:~$ cat flagz.txt
8===0daqdDlmd9XogkiHu4yq===D~~
emma@venus:~$

```
### Summary
usamos el comando sed para que nos muestre una linea espesifica de un archivo para ello ocupamos la opcion -n que evita la salida estandar del comando y la opcion '4069p' para decirle que linea queremos que nos muestra 
