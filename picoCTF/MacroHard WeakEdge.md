#forensic #base64 #pptm 
#### Description

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/52da699e0f203321c7c90ab56ea912d8/Forensics%20is%20fun.pptm)

### Solution
Un archivo de PowerPoint es básicamente un archivo ZIP con una extensión diferente y un contenido específico, así que lo descomprimimos para ver si podernos encontrar algo interesante .

y encontramos algo interesante al final un archivo con nombre hidden así que vemos que tiene adentro , vemos un mensaje algo raro así que le quitamos los espacios y lo metemos en cyberchef
```shell
┌──(kali㉿kali)-[~]
└─$ cd Desktop              
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop]
└─$ unzip Forensics\ is\ fun.pptm 
...
inflating: ppt/vbaProject.bin      
  inflating: ppt/presProps.xml       
  inflating: ppt/viewProps.xml       
  inflating: ppt/tableStyles.xml     
  inflating: docProps/core.xml       
  inflating: docProps/app.xml        
  inflating: ppt/slideMasters/hidden
  
┌──(kali㉿kali)-[~/Desktop]
└─$ cat ppt/slideMasters/hidden 
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q 

```
la cadena anterior resulto ser una cadena encriptada en base64
![[Pasted image 20231016155928.png]]

### Flag
picoCTF{D1d_u_kn0w_ppts_r_z1p5}