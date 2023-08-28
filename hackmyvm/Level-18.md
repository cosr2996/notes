### Level Goat
La password de frida esta en el zip protegido con password.(rockyou.txt puede ayudarte)
### User
**clara**
### Credentials
ssh hacker@venus.hackmyvm.eu -p 5000
pass: **havefun!**
### Solution
```shell

TERMINAL 1
clara@venus:~$ ls
flagz.txt  mission.txt  protected.zip
clara@venus:~$ base64 protected.zip -w 0
UEsDBAoACQAAAMFG+lZzdJ8jHAAAABAAAAAZABwAcHduZWQvY2xhcmEvcHJvdGVjdGVkLnR4dFVUCQADKd/AZCnfwGR1eAsAAQQAAAAABAAAAAA1p/4kJie4z6wyYuU5N9W7cQ5FIJb5UGmHTrylUEsHCHN0nyMcAAAAEAAAAFBLAQIeAwoACQAAAMFG+lZzdJ8jHAAAABAAAAAZABgAAAAAAAEAAACkgQAAAABwd25lZC9jbGFyYS9wcm90ZWN0ZWQudHh0VVQFAAMp38BkdXgLAAEEAAAAAAQAAAAAUEsFBgAAAAABAAEAXwAAAH8AAAAAAA==clara@venus:~$





TERMINAL 2
┌──(kali㉿kali)-[~/Downloads]
└─$ echo 'UEsDBAoACQAAAMFG+lZzdJ8jHAAAABAAAAAZABwAcHduZWQvY2xhcmEvcHJvdGVjdGVkLnR4dFVUCQADKd/AZCnfwGR1eAsAAQQAAAAABAAAAAA1p/4kJie4z6wyYuU5N9W7cQ5FIJb5UGmHTrylUEsHCHN0nyMcAAAAEAAAAFBLAQIeAwoACQAAAMFG+lZzdJ8jHAAAABAAAAAZABgAAAAAAAEAAACkgQAAAABwd25lZC9jbGFyYS9wcm90ZWN0ZWQudHh0VVQFAAMp38BkdXgLAAEEAAAAAAQAAAAAUEsFBgAAAAABAAEAXwAAAH8AAAAAAA==' | base64 -d >private.zip

┌──(kali㉿kali)-[~/Downloads]
└─$ ls
private.zip  rockyou.txt  rockyou.txt.zip                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ zip2john private.zip > hash
ver 1.0 efh 5455 efh 7875 private.zip/pwned/clara/protected.txt PKZIP Encr: 2b chk, TS_chk, cmplen=28, decmplen=16, crc=239F7473 ts=46C1 cs=46c1 type=0                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ cat hash       
private.zip/pwned/clara/protected.txt:$pkzip$1*2*2*0*1c*10*239f7473*0*53*0*1c*46c1*35a7fe242627b8cfac3262e53937d5bb710e452096f95069874ebca5*$/pkzip$:pwned/clara/protected.txt:private.zip::private.zip

┌──(kali㉿kali)-[~/Downloads]
└─$ john hash -w=rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
pass123          (private.zip/pwned/clara/protected.txt)     
1g 0:00:00:00 DONE (2023-08-27 17:11) 50.00g/s 409600p/s 409600c/s 409600C/s newzealand..total90
Use the "--show" option to display all of the cracked passwords reliably
Session completed.                                                      
┌──(kali㉿kali)-[~/Downloads]
└─$ unzip private.zip    
Archive:  private.zip
[private.zip] pwned/clara/protected.txt password: 
 extracting: pwned/clara/protected.txt  
                                                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
hash  private.zip  pwned  rockyou.txt  rockyou.txt.zip

┌──(kali㉿kali)-[~/Downloads]
└─$ cd pwned    

┌──(kali㉿kali)-[~/Downloads/pwned]
└─$ ls
clara

┌──(kali㉿kali)-[~/Downloads/pwned]
└─$ cd clara 

┌──(kali㉿kali)-[~/Downloads/pwned/clara]
└─$ ls
protected.txt

┌──(kali㉿kali)-[~/Downloads/pwned/clara]
└─$ cat protected.txt 
Ed4ErEUJEaMcXli





TERMINAL 1
clara@venus:~$ su frida
Password:
frida@venus:/pwned/clara$ cd ..
frida@venus:/pwned$ cd frida/
frida@venus:~$ cat flagz.txt
8===Ikg2qj8KT2bGJtWvR6hC===D~~
frida@venus:~$

```
### Summary

El archivo `rockyou.txt` es un archivo de texto que contiene una lista de contraseñas comunes utilizadas en ataques de fuerza bruta. El archivo se ha utilizado en muchos ataques de seguridad y es una de las listas de contraseñas más populares utilizadas por los atacantes. El archivo contiene más de **14 millones** de contraseñas y se ha utilizado en muchos ataques exitosos contra sistemas y aplicaciones que no tienen medidas de seguridad adecuadas .

Es importante tener en cuenta que el uso del archivo `rockyou.txt` para fines malintencionados es ilegal y puede resultar en consecuencias graves.

solución
para este ejercicio tendremos que usar fuerza bruta con ayuda de un programa llamado john para esto tendremos que usar otra terminal en nuestra maquina  ya que en el servidor de hackmyvm hay muchas restricciones para el uso de estos programas  . para esto tendremos que llebarnos el archivo.zip que esta protegido con  contraseña, esto parece complicado , para ello una solucion que encontre fue encriptar el archivo en base64.

1 -encriptar el archivo protected.zip en base64 , usamos la opcion -w 0 para que nos de el resultado formateado a una sola linea y lo copiamos
2 - nos vamos a la termnial de nuestra maquina y desencriptamos el archvio y redirigiendo la salida a un archivo.zip
3-  con ayuda de zip2john convertimos el archivo a un hash que puede entender john para después crackearlo 
4- ejecutamos john pasándole el archivo a crackear y li lista de contraseñas rockyou.txt
5-  descubrimos que la contraseña es pass123 con esa contraseña extraemos el archivo .zip
6 - usamos la contraseña que encontramos para loogearnos con el usuario Frida
7 - encontramos la bandera

### Extra

El comando `john hash -w=rockyou.txt` es utilizado para crackear contraseñas. `john` es un programa que se utiliza para descifrar contraseñas cifradas. El argumento `hash` especifica el archivo que contiene las contraseñas cifradas que se desean descifrar. El argumento `-w` especifica el archivo de palabras que se utilizará para descifrar las contraseñas. En este caso, el archivo de palabras utilizado es `rockyou.txt`, que es una lista de palabras comunes utilizadas en contraseñas .

El comando `zip2john private.zip > hash` se utiliza para convertir el archivo `private.zip` en un archivo de hash que puede ser utilizado por el programa `john` para descifrar la contraseña del archivo. El símbolo `>` se utiliza para redirigir la salida del comando a un archivo llamado `hash`.