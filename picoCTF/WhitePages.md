#forensic #binary #python #unicode 
#### Description
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

### Solution
al tratar de abrir el archivo parece estar vacío , pero viendo mas a detalle nos damos cuenta que todo son espacios , al usar el comando xxd para ver el archivo en hexadecimal  y ver que tiene dentro vemos que seimpre se repiten los mismos valores  **e28083** y **20** 
```shell
❯ xxd whitepages.txt|head
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2 8083 e280 83e2 8083 2020 e280  .  .........  ..
00000070: 8320 20e2 8083 2020 2020 e280 8320 e280  .  ...    ... ..
00000080: 83e2 8083 e280 83e2 8083 2020 e280 8320  ..........  ... 
00000090: e280 8320 e280 8320 e280 83e2 8083 e280  ... ... ........
```
vemos que se repite el **e28083**
investigando un poco ese character también es un espacio así que con esto en mente se nos ocurre que al ser los mismos dos caracteres repetidos puede tratarse de codigo binario 

para ello usamos una de las bibliotecas de python mas útiles para ciberseguridad la cual es pwn , con esto hacemos un script que hace  lo siguiente :

1 - importar biblioteca
2 - abrimos el archivo 
3- leemos el archivo y lo almacenamos en data
4- Luego convierto el patrón "**E28083**" en 0 y el "**20**" en 1. Si esto no funciona, intentaré al revés.
6 - convertimos el contenido a ascii
7- 
8- mostramos el resultado 

```python
from pwn import *

file = open('whitepages.txt','rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)

```

el convertir todos estos caracteres unicode a binario y después a ascci resulta darnos un mensaje :

b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'

### Flag
picoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}