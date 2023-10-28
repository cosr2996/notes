#Crypto #vigenere 
#### Description
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

### Solution
El cifrado de Vigenère es un método de cifrado que usa una serie de diferentes cifrados César basados en una palabra clave. Cada letra del texto se reemplaza por otra letra que se encuentra un cierto número de posiciones más adelante en el alfabeto, según la letra correspondiente de la palabra clave. Por ejemplo, si la palabra clave es BING y el texto es HOLA, se cifra así:

H + B = I O + I = R L + N = T A + G = G

podemos hacerlo de manera manual con ayuda de la tabla o con cyber chef
![[Pasted image 20231025135807.png]]

![[Pasted image 20231025135942.png]]
en la forma manual usamos la clave para identificar la file hasta encontrar la letra del texto cifrado y la letra de esa columna es la letra descifrada por ejemplo 
- la clave empieza con s entonces buscamos la columna s
- la letra del text cifrada es u entonces nos detenemos en la columna que contiene dicha letra en este caso la c
### Flag
picoCTF{CRYPTOISFUN}