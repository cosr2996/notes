#forensic #favorite #steganography #moon
#### Description
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.
### Solution
para este reto usamos una herramienta que decodifica archivos sstv repo :
[colaclanth/sstv: SSTV Decoder (github.com)](https://github.com/colaclanth/sstv)

este reto es muy interesante , se nos da un audio el cual no tiene mucho sentido edemas buscando en los strings y metadatos no hay nada fuera de lo común , por medio de las pistas esto nos hace pensar que hay algo oculto dentro del archivo .

resulta que las primeras fotos de la luna se mandaban en formato sstv.

Desde antes de Internet, ya era muy popular entre los radio aficionados el envío de imágenes a través de las ondas de radio gracias a la aparición y masificación de las computadoras. Esta técnica se conoce como SSTV, cuya sigla en inglés corresponde a Slow Scan TV y en español se traduce como Televisión de Barrido Lento.
La televisión de barrido lento (SSTV) es un método para transmitir imágenes fijas utilizando canales de radio convencionales.  
Los sistemas SSTV se desarrollaron originalmente para su uso en transmisiones de radioaficionados, pero también pueden utilizarse para transmitir imágenes de sondas espaciales u otras aplicaciones científicas.  
El principio básico de la SSTV es enviar cada línea de la imagen en una señal de radio separada, y cada señal tarda un tiempo diferente en transmitirse.  
Esto significa que la estación receptora debe ser capaz de reconstruir la imagen juntando las diferentes señales.  
Los sistemas SSTV suelen transmitir imágenes en blanco y negro o en color.  
El formato más común de SSTV es el llamado Robot 36, que transmite una imagen en blanco y negro utilizando una señal que tarda unos 36 segundos en transmitirse.

**Una de las ventajas de la SSTV es que puede utilizarse para transmitir imágenes a grandes distancias, ya que la señal no tiene que ser muy potente para ser recibida.  
Otra ventaja es que las imágenes de SSTV pueden almacenarse y recuperarse fácilmente en un ordenador.**

```shell
┌──(kali㉿kali)-[~/Desktop]
└─$ sstv -d message.wav -o result.png 
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...          [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$                        
```

![[result.jpg]]
### Flag
picoCTF{beep_boop_im_in_space}
