#forensic #wireshark 
#### Description
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

### Solution
vemos el stream de los paquetes udp ya que hay muchos y eso nos  hace sospechar que por aquí puede estar la bandera , y en stream 6 encontramos la bandera

![[Pasted image 20231015214354.png]]

### Flag
picoCTF{StaT31355_636f6e6e}