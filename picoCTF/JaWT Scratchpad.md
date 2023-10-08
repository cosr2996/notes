#JWT #cookie #john_the_ripper #crack
#### Description
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864


### Solution
por las pistas del reto investigamos las cookies , cuando iniciamos session se crea una cookie que esta en formato jwt
![[Pasted image 20231008162857.png]]
la metemos en [JSON Web Tokens - jwt.io](https://jwt.io/) y vemos que es un web token de acceso donde indica el usuario con el que esta logeado si cambiamos el nombre omar por admin deveria de funcionar , sin embargo no lo hara ya que nos falta la llave para que la pagina compruebe que es correcta la coockie
![[Pasted image 20231008162950.png]]

así que con ayuda de la herramienta john crackeamos el hash  y encontramos que la llave es ilovepico
![[Pasted image 20231008163602.png]]

en este apartado es donde colocamos la llave 
![[Pasted image 20231008163830.png]]
![[Pasted image 20231008163852.png]]
ponemos la nueva cookie y recargamos la pantalla  esto nos da acceso a las notas de admin el cual tiene la bandera 
![[Pasted image 20231008163725.png]]


### Flag
picoCTF{jawt_was_just_what_you_thought_1ca14548}