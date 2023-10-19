#forensic #base64 #encrypt #metadata 
#### Description
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)

### Solution
lo primero que hacemos es checar los metadatos , hay un apartado que llamo mi atención parece base64

![[Pasted image 20231018180319.png]]
lo ponemos en cyberchef
![[Pasted image 20231018180301.png]]

### Flag
picoCTF{the_m3tadata_1s_modified}