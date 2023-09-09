# Level-2 -> Level-3

### Credentials

```
Username: natas3
Password: G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q
URL:      http://natas3.natas.labs.overthewire.org
```
### Solution

![[Screenshot 2023-09-09 134542.png]]
![[Screenshot 2023-09-09 135223.png]]
vemos si existe el archivo robots.txt
![[Screenshot 2023-09-09 135317.png]]
![[Screenshot 2023-09-09 135338.png]]
![[Screenshot 2023-09-09 135343.png]]
### Summary

debido al comentario que encontramos en el codigo nos da la pista de que se puede tratar de un robots.txt  que se coloca en la base de un directorio web (por ejemplo, sitio web.com/robots.txt). Este archivo de texto tiene un formato estandarizado que indica a los motores de búsqueda y otros rastreadores web qué páginas web y directorios no deben indexar, lo que significa que esas páginas no aparecerán en los resultados de búsqueda.

con esto encontramos que hay una carpeta no indexada llamada s3cr3t dentro un archivo users dentro la bandera
### FLAG
**tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm** 
### Takeaway
consulte siempre robots.txt.