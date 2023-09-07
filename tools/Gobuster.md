### Que es?

Gobuster es una herramienta de línea de comandos que se utiliza para buscar directorios y archivos en un sitio web. Es una herramienta útil para los profesionales de seguridad que buscan vulnerabilidades en un sitio web. Gobuster es capaz de buscar directorios y archivos utilizando una lista de palabras personalizada, lo que lo hace muy flexible y adaptable a diferentes situaciones.

Gobuster es compatible con varios protocolos, incluidos HTTP, HTTPS y FTP. También es compatible con la autenticación básica y la autenticación por formulario. Gobuster es una herramienta de código abierto y está disponible para su uso en sistemas operativos Linux, macOS y Windows.

### Ejemplos:

gobuster dir -u http://10.129.1.15 -w /usr/share/dirb/wordlists/common.txt 
El comando `gobuster dir -u http://10.129.1.15 -w /usr/share/dirb/wordlists/common.txt` se utiliza para buscar directorios y archivos en un sitio web.

Aquí está lo que hace cada parte del comando:

- `gobuster`: el nombre del programa que se está ejecutando.
- `dir`: el modo de búsqueda que se está utilizando. En este caso, se busca directorios y archivos.
- `-u http://10.129.1.15`: la URL del sitio web que se va a buscar.
- `-w /usr/share/dirb/wordlists/common.txt`: la ruta del archivo de lista de palabras que se utilizará para buscar.

En resumen, el comando buscará en el sitio web `http://10.129.1.15` todos los directorios y archivos que se encuentren en la lista de palabras `/usr/share/dirb/wordlists/common.txt`.

sudo gobuster dir -u http://10.129.1.15 -w /usr/share/dirb/wordlists/common.txt -x .php
- `-x .php`: la extensión de archivo que se buscará en el sitio web.

En resumen, el comando buscará en el sitio web `http://10.129.1.15` todos los directorios y archivos que contengan la extensión `.php` y que estén incluidos en la lista de palabras `/usr/share/dirb/wordlists/common.txt`.