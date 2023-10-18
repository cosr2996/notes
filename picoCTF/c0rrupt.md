#forensic #hex_editor #hexadecimal #png 
#### Description
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

### Solution
para este reto usamos una herramienta muy practica que nos ayuda a ver que problemas tiene un archivo png este se llama pngcheck

al estar cheacando un poco el archivo creemos que se puede tratar de un archivo png .

primero corregimos los primeros 8 bytes ya que esos siempre son los mismos en un archivo png.

después corregimos uno de los critical chunks  IHDR el cual  debe ser la primera sección, que  contiene la cabecera , vemos que en el inspector se que esta mal así que cambiamos los valores parra que siga IHDR.

después seguimos con las secciones de metadatos 
- pHYs: contiene el tamaño previsto del píxel y/o el ratio de la imagen.(la resolucion )
y al parecer tiene valores muy grandes asi que pensando que la imagen es cuadrada lo cambiamos a 00 para que tenga el mismo valor que el ancho 

despues continuamos con otro critical chunk el cual se encarga de :
- IDAT, contiene la imagen que debe ser dividida en múltiples secciones IDAT, haciendo esto se incrementa el tamaño de la imagen ligeramente pero hace posible generar imágenes PNG en [streaming](https://es.wikipedia.org/wiki/Streaming "Streaming").
vemos que Tambien esta mal así que lo cambiamos para que diga IDAT.

por ultimo nos encontramos con el que tamaño es muy grande ya que esta usando 4 bytes cuando regularmente se usan solo 2 así que cambiamos dos de esos a 00 (aa->00).
![[Pasted image 20231016181744.png]]

(resultado)
![[Pasted image 20231016181434.png]]
![[mystery - copia.png]]
### Info:
[PNG - Wikipedia](https://en.wikipedia.org/wiki/PNG)
### Flag
picoCTF{c0rrupt10n_1847995}