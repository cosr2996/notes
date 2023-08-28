### Level Goat
El password de la usuaria elena esta entre los caracteres fu y ck
### User
**lucy**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
lucy@venus:~$ sed -n '/^fu.*ck$/p' file.yo
fu4xZ5lIKYmfPLg9tck
lucy@venus:~$ su elena
Password:
elena@venus:/pwned/lucy$ cd ..
elena@venus:/pwned$ cd elena
elena@venus:~$ cat flagz.txt
8===st1pTdqEQ0bvrJfWGwLA===D~~
```
### Summary
Donde `cadena` es la cadena de texto que deseas buscar y `archivo` es el nombre del archivo en el que deseas buscar.

La opción `-n` se utiliza para suprimir la salida de todas las líneas del archivo excepto las que coinciden con el patrón de búsqueda. La expresión regular `/^cadena.*cadena$/` busca todas las líneas que comienzan con la cadena y terminan con la cadena. La opción `p` se utiliza para imprimir las líneas que coinciden con el patrón de búsqueda.

-  los símbolos `/` al principio y al final de la expresión regular indican que es una expresión regular.
- en el medio de la expresión regular indica que cualquier número de caracteres puede aparecer entre las dos palabras
