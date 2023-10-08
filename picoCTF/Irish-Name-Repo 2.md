#sql #Injection #SQL 
#### Description

There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

### Solution

este reto es muy parecido al reto pasado donde de igual manera haremos una inyeccion sql pero esta vez la pagina se dio cuenta de que era vulnerable entonces cuando  ponemos una inyeccion la detecta y no nos deja entrar .
posiblemente lo que este haciendo es detectar ciertos caracteres para saber que se trata de una inyeccion asi que para este reto hacemos la siguiente inyeccion donde si ponemos un usario y despues la inyeccion para intentar que no detecte que se trata de una inyeccion 

```sql
admin';--
```
### Flag
picoCTF{m0R3_SQL_plz_fa983901}