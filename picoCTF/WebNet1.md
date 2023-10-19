#forensic #wireshark #TLS #key #metadata 
#### Description
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

### Solution
no podemos ver los streams de la captura de paquetes ya que están encriptados con tls afortunadamente se nos da la llave para poder hacer la desencriptación .
después de agregar la llave privada se nos deja  ver algunos paquetes y notamos algo interesante en uno

![[Pasted image 20231018175738.png]]
es una imagen , con ayuda de wireshark podemos descargar la imagen , nos vamos a FIle->Export Objects->HTTP

esto nos descarga una imagen , lo primero que se me ocurre es revisar los metadatos .

![[Pasted image 20231018175916.png]]
### Flag
picoCTF{honey.roasted.peanuts}
