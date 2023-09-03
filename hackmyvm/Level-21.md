### Level Goat
User eloise has saved her password in a particular way. 
### User
**iris**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell
iris@venus:~$ ls -l
total 32
-rw-r----- 1 root iris 17484 Jul 26 08:54 eloise
-rw-r----- 1 root iris    31 Jul 26 08:53 flagz.txt
-rw-r----- 1 root iris    16 Jul 26 08:54 irispass.txt
-rw-r----- 1 root iris   195 Jul 26 08:53 mission.txt
iris@venus:~$ cat mission.txt 
################
# MISSION 0x21 #
################

## EN ##
User eloise has saved her password in a particular way. 

## ES ##
La usuaria eloise ha guardado su password de una forma particular.


┌──(kali㉿kali)-[~/Downloads]
└─$ nano encode     

┌──(kali㉿kali)-[~/Downloads]
└─$ base64 -d encode > decode  

┌──(kali㉿kali)-[~/Downloads]
└─$ file decode   

decode: JPEG image data, JFIF standard 1.01, resolution (DPI), density 96x96, segment length 16, Exif Standard: [TIFF image data, big-endian, direntries=4], baseline, precision 8, 394x102, components 3                                             
┌──(kali㉿kali)-[~/Downloads]
└─$


iris@venus:~$ su eloise
Password:
eloise@venus:/pwned/iris$ cd ..
eloise@venus:/pwned$
eloise@venus:/pwned$ cd eloise/
eloise@venus:~$ cat flagz.txt 
8===57CzBLKaEq2N8YBFRu31===D~~
eloise@venus:~$ 


```

![[decode.jpeg]]
yOUJlV0SHOnbSPm
### Summary
al ver lo que contenía el archivo eloise vemos que termina con "=" eso nos da la pista de que se puede tratar de un archivo en base64, así que lo desciframos con el comando base64 -d y lo guardamos en un nuevo archivo vemos que al aplicarle el comando file dice que se trata de una imagen jpeg así que le agregamos la extension y la abrimos con cualquier gestor de imágenes y dentro tenemos la imagen 