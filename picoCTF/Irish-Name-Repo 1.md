#sql #Injection #SQL 
#### Description
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!


### Solution
viendo el codigo fuente nos damos cuenta de que hay un campo oculto llamado debug , con ayuda del inspector lo ponemos a 1 
![[Pasted image 20231003194623.png]]
al intentar hacer login con el debug a 1 nos mestra esto que es la consulta que se hace para validar usuarios
![[Pasted image 20231003194727.png]]

ademas viendo la seccion de soporte se nos da la informacion de que se trata de una base de datos sql asi que intentamos inyectar codigo sql

```sql
' OR 1=1--
```

Lo que está sucediendo aquí es que la consulta comprueba si el nombre de usuario es igual a nada. Luego, verifica OR 1 = 1. Como 1 siempre va a ser igual a 1, esto devuelve verdadero. El -- al final simplemente comenta el resto de la consulta. Esto engaña al servidor para que nos deje pasar por el portal.
### Flag
picoCTF{s0m3_SQL_c218b685}