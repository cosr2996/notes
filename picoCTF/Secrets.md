#web_exploitation 
#### Description
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:64727/).

### Solution
viendo el codigo fuente de la pagina nos encontramos con un imagen que al abrirla notamos algo interesante en la ruta
![[Pasted image 20231018195324.png]]

asi que entrramos al directorio secrets y nos encontramos con esto 
![[Pasted image 20231018195358.png]]

y nuevamente revisando el codigo fuente encontramos un archivo css en una ruta interesante
![[Pasted image 20231018195545.png]]

entramos en la ruta hidden
![[Pasted image 20231018195615.png]]

revisando el codigo nuevamente encontrmaos un input oculto que lo que hace es redireccionar a una pagina 
![[Pasted image 20231018195900.png]]
entramos a la carpeta superhidden
![[Pasted image 20231018195918.png]]
### Flag
picoCTF{succ3ss_@h3n1c@10n_790d2615}