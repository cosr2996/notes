#Crypto
# Descripción:
We slipped like a snake and accessed confidential information available in a shared folder, to extract it without being discovered we have encrypted it in a simple way
# Solución:
```shell
omar@omar-pc:~/Descargas/snakes$ ls
msg.zip
omar@omar-pc:~/Descargas/snakes$ unzip msg.zip 
Archive:  msg.zip
  inflating: msg.txt                 
omar@omar-pc:~/Descargas/snakes$ ls
msg.txt  msg.zip
omar@omar-pc:~/Descargas/snakes$ cat msg.txt 
  	 | 	  | 	|		 |		|	  	|    |  |	  |	  | |	 |		| |   |   | 	|		 | | 	|  |	|    |			| 	  |	  |   |	|  	|  	 |  	 omar@omar-pc:~/Descargas/snakes$ xxd msg.txt 
00000000: 2020 0920 7c20 0920 207c 2009 7c09 0920    . | .  | .|.. 
00000010: 7c09 097c 0920 2009 7c20 2020 207c 2020  |..|.  .|    |  
00000020: 7c09 2020 7c09 2020 7c20 7c09 207c 0909  |.  |.  | |. |..
00000030: 7c20 7c20 2020 7c20 2020 7c20 097c 0909  | |   |   | .|..
00000040: 207c 207c 2009 097c 2020 7c09 7c20 2020   | | ..|  |.|   
00000050: 207c 0909 097c 2009 2020 7c09 2020 7c20   |...| .  |.  | 
00000060: 2020 7c09 7c20 2009 7c20 2009 207c 2020    |.|  .|  . |  
00000070: 0920                                     . 
omar@omar-pc:~/Descargas/snakes$
```
![[codigo-morse-2 1.jpg]]

# Bandera:
flagMX{hiddenmessagewitholdstuff}
# Resumen:
descargamos el archivo que es un .zip, lo descomprimimos y vemos que dentro hay un archivo de texto plano, al ver su contenido vemos que hay un mensaje raro , al usar el comando xxd vemos cierto patrón que nos hace pensar que puede ser código morse , tratando de encontrar el patrón hacemos la decodificacion  