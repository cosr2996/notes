### Level Goat
El password de la usuaria violet esta en la linea que empieza por a9HFX (sin ser estos 5 caracteres parte de su password.).
### User
**isla**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
isla@venus:~$ grep "a9HFX" passy
WKINVzNQLKLDVAca9HFX
dWeFra9HFXzNQLKLDVAc
kfRgNa9HFXzNQLKLDVAc
zNQa9HFXfEtrgLKLDVAc
WKINVzNQLa9HFXDwErfc
WKINVa9HFXzDcceWeTfd
a9HFXWKINVzNQLKLDVAc
isla@venus:~$ su violet
Password:
violet@venus:/pwned/isla$ cd ..
violet@venus:/pwned$ cd violet
violet@venus:~$ cat flagz.txt
8===LzErk0qFPYJj16mNnnYZ===D~~
violet@venus:~$

```
### Summary
para este reto usamos el comando grep para buscar la el texto que se nos dijo , para esto  hay 7 resultados que contienen esa cadena , buscamos la que tiene esa cadena al principio y ese es el password

tambien podemos usar esta forma para buscar que directamente esa cadena se encuentre al principio
```
grep '^sdfsd' archivo.txt
```
Aquí, `^` se utiliza para indicar el inicio de la línea, y `sdfsd` es la cadena que deseas buscar.