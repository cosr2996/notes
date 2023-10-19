#web_exploitation #address
#### Description
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55793/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

### Solution
sabemos que todos los archivos están en `/usr/share/nginx/html/` y que  la flag esta en `/flag.txt` (ósea en la raíz) así que solo retrocedemos las carpetas en las que estamos (4) y leemos el archivo 

![[Pasted image 20231018182933.png]]

### Flag
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}