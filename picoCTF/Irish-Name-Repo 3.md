#sql #Injection #SQL #ROT13 #encrypt
#### Description
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!


### Solution
el ejersicio dice que esta encriptado , haciendo pruebas con el campo de debug que esta oculto damos con que lo que ingresamos en el campo de pass se encripta con rot13
![[Pasted image 20231008152934.png]]
![[Pasted image 20231008152949.png]]

asi que con ayuda de cyberchef encriptamos la inyeccion y la metemos en el input de manera de que  al interior se desencripte y se ejecute la inyeccion 
![[Pasted image 20231008152327.png]]

![[Pasted image 20231008152523.png]]


### Flag
picoCTF{3v3n_m0r3_SQL_06a9db19}