### Level Goat
El password de la usuaria lucy se encuentra en la linea que acaba por 0JuAZ (sin ser estos ultimos 5 ca
### User
**violet**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
violet@venus:~$ ls
end  flagz.txt  mission.txt
violet@venus:~$ find "0JuAZ$" end
find: ‘0JuAZ$’: No such file or directory
end
violet@venus:~$ find "0JuAZ$" end
find: ‘0JuAZ$’: No such file or directory
end
violet@venus:~$ grep "0JuAZ$" end
OCmMUjebG53giud0JuAZ
violet@venus:~$ cd..
bash: cd..: command not found
violet@venus:~$ cd ..
violet@venus:/pwned$ su lucy
Password:
lucy@venus:/pwned$ cd lucy
lucy@venus:~$ cat flagz.txt
8===AdCJ4wl8pmbhi770Xbd3===D~~
```
### Summary

Para buscar una línea que termine con “sdfsd” en un archivo de texto en Linux, puedes usar el comando `grep`. Por ejemplo, si deseas buscar la línea que termine con “sdfsd” en el archivo `archivo.txt`, puedes ejecutar el siguiente comando en la terminal:

```
grep 'sdfsd$' archivo.txt
```

Copy

Aquí, `$` se utiliza para indicar el final de la línea, y `sdfsd` es la cadena que deseas buscar.