#headers #burpsuite 
#### Description

This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

### Solution
vemos que nos dice que solo se puede acceder desde el navegador picobrowser
![[Captura de pantalla de 2023-10-02 10-54-03.png]]
con ayuda de burpsuite vemos las peticiones que se hacen
![[Captura de pantalla de 2023-10-02 10-54-35.png]]
cambiamos la cabecera user-agent a el navegador que si es peritido picobrowser
![[Captura de pantalla de 2023-10-02 10-55-07.png]]

![[Captura de pantalla de 2023-10-02 10-53-13.png]]
### Flag

`picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}`