# Level-12 -> Level-13

### Level Goat
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
### Credentials
ssh bandit12@bandit.labs.overthewire.org -p 2220
password: **JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv**
### Solution
```shell
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ file data.txt
data.txt: ASCII text
bandit12@bandit:~$ mkdir /tmp/cosr2
bandit12@bandit:~$ cat data.txt | xxd -r > /tmp/cosr2/archivo.bin
bandit12@bandit:~$ cd /tmp//cosr2
bandit12@bandit:/tmp/cosr2$ ls
archivo.bin
bandit12@bandit:/tmp/cosr2$ file archivo.bin
archivo.bin: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 581
bandit12@bandit:/tmp/cosr2$ mv archivo.bin archivo.gz
bandit12@bandit:/tmp/cosr2$ gzip -d archivo.gz
bandit12@bandit:/tmp/cosr2$ ls
archivo
bandit12@bandit:/tmp/cosr2$ file archivo
archivo: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/cosr2$ mv archivo archivo.bz2
bandit12@bandit:/tmp/cosr2$ bzip2 -d archivo.bz2
bandit12@bandit:/tmp/cosr2$ ls
archivo
bandit12@bandit:/tmp/cosr2$ file archivo
archivo: gzip compressed data, was "data4.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/cosr2$ mv archivo archivo.gz
bandit12@bandit:/tmp/cosr2$ gzip -d archivo.gz
bandit12@bandit:/tmp/cosr2$ ls
archivo
bandit12@bandit:/tmp/cosr2$ file archivo
archivo: POSIX tar archive (GNU)
bandit12@bandit:/tmp/cosr2$ mv archivo archivo.tar
bandit12@bandit:/tmp/cosr2$ tar xf archivo.tar
bandit12@bandit:/tmp/cosr2$ ls
archivo.tar  data5.bin
bandit12@bandit:/tmp/cosr2$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/cosr2$ mv data5.bin data5.tar
bandit12@bandit:/tmp/cosr2$ tar xf data5.tar
bandit12@bandit:/tmp/cosr2$ ls
archivo.tar  data5.tar  data6.bin
bandit12@bandit:/tmp/cosr2$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/cosr2$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/cosr2$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/cosr2$ ls
archivo.tar  data5.tar  data6
bandit12@bandit:/tmp/cosr2$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/cosr2$ mv data6 data6.tar
bandit12@bandit:/tmp/cosr2$ tar xf data6.tar
bandit12@bandit:/tmp/cosr2$ ls
archivo.tar  data5.tar  data6.tar  data8.bin
bandit12@bandit:/tmp/cosr2$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/cosr2$ mv data8.bin data8.gz
bandit12@bandit:/tmp/cosr2$ gzip -d data8.gz
bandit12@bandit:/tmp/cosr2$ ls
archivo.tar  data5.tar  data6.tar  data8
bandit12@bandit:/tmp/cosr2$ file data8
data8: ASCII text
bandit12@bandit:/tmp/cosr2$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/cosr2$
```
### Summary
En informática , un **volcado hexadecimal** es una vista hexadecimal (en pantalla o en papel) de datos informáticos, desde la memoria o desde un archivo informático o dispositivo de almacenamiento . La observación de un volcado hexadecimal de datos generalmente se realiza en el contexto de depuración , ingeniería inversa o análisis forense digital

para revertir el volcado :
## xxd

Crea un volcado hexadecimal de un archivo. También puede convertir un volcado hexadecimal de nuevo a su forma binaria inicial. Además, puede ser utilizado para realizar parches archivo binario.

Su sintaxis es de la forma:  
xxd [opciones] [archivo]

Sus **opciones** son:

-p muestra el archivo en hexadecimal plano o plain hexdump.

-r transforma de hexadecimal a binario.

-h muestra la ayuda del comando.

despues de revertir el volcado nos damos cuenta que es un archivo comprimido asi que segun la comprecion usamos el comando correspondiente pero entes de eso le cambiamos la extencion para que sea la correcta


![[Screenshot 2023-08-21 155005.png]]
### FLAG
**wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw** 