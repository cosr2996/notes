### Level Goat
La usuaria luna ha dejado su password en algún fichero dentro de la carpeta muack.
### User
**camila**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
camila@venus:~$ ls
flagz.txt  mission.txt  muack
camila@venus:~$ find muack/ -type f -exec cat {} \;
j3vkuoKQwvbhkMc
camila@venus:~$ su luna
Password:
luna@venus:/pwned/camila$ cd ..
luna@venus:/pwned$ cd luna/
luna@venus:~$ cat flagz.txt
8===KCO34FpIq3nBmHbyZvFh===D~~
luna@venus:~$

```
### Summary
El comando `find muack/ -type f -exec cat {} \;` busca todos los archivos regulares en el directorio `muack/` y sus subdirectorios, y luego imprime el contenido de cada archivo en la terminal.

Aquí, `find` se utiliza para buscar archivos, `muack/` es el directorio raíz de la búsqueda, `-type f` se utiliza para buscar solo archivos regulares, `-exec cat {} \;` se utiliza para imprimir el contenido de cada archivo encontrado.