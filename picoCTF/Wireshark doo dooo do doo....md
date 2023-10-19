#forensic #wireshark #ROT13 #encrypt 
#### Description
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/b44842413a0834f4a3619e5f5e629d05/shark1.pcapng).

### Solution
analizando los paquetes tcp en el stream 5 encontramos un string con una base parecida a la de una bandera , tal vez este encriptada
![[Pasted image 20231018213746.png]]

![[Pasted image 20231018213936.png]]
### Flag
picoCTF{p33kab00_1_s33_u_deadbeef}