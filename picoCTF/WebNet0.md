#forensic #wireshark #TLS #key
#### Description
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag

### Solution
cuando queremos ver los streams no nos muestra nada esto es debido a que estan cifrados con una llave , lo que tenemos que hacer es cargar esa llave en wireshark .

seguido de esto hacemos una busqueda de un string "picoCTF" en los detalles de los paquetes y encontramos la llave

![[Pasted image 20231018174323.png]]


### Flag
picoCTF{nongshim.shrimp.crackers}

