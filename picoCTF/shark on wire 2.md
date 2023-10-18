#forensic #wireshark #python 
#### Description
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

### Solution

nos llama la atención que hay muchos paquetes upd por lo que nos ponemos a revisar los streams y encontramos algo curioso 
![[Pasted image 20231017214516.png]]

mas adelante en el stream 60 encontramos 
![[Pasted image 20231017214608.png]]

esto nos hace pensar que el mensaje esta oculto en esos streams del 22 al 60 por lo tanto hacemos una búsqueda para todos los paquetes que se enviaron al port 22 ya que ambos se mandan a ese puerto nos hace pensar que el resto de paquetes igual 
![[Pasted image 20231017214809.png]]

vemos algo curioso y es que en el puerto origen va cambiando esto nos hace pensar que puede ser código ascii si le quitamos 5000 al puerto nos da un numero que si puede ser representado con ascii , así que con la función de python chr() vemos que :
112 -> p
105 -> i
99 -> c
111 -> 0
esto va formando una bandera así que parece ser aquí esta la respuesta.

para no hacer esto con cada uno de los paquetes haremos un script para automatizar el proceso con python (scapy)

```python 
from scapy.all import *

packets =rdpcap('capture.pcap')
flag =""

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag += chr(p[UDP].sport - 5000)
print(flag)
			
```

al correr el script nos da la bandera 
![[Pasted image 20231017220645.png]]

### Flag
picoCTF{p1LLf3r3d_data_v1a_st3g0}