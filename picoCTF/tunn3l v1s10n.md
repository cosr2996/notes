#forensic  #hexadecimal #hex_editor #favorite
#### Description
We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.

### Solution
investigando el tipo de dato del archivo nos da como resultado que es de datos lo cual no nos dice nada claro esto nos hace pensar que no se trate de el archivo correcto o que tenga algo escondido dentro .

al comprobar que el archivo no tiene nada dentro . y al ver los metadatos nos dice que parece ser se trata de una imagen bmp .

usamos el comando xxd para ver los primeros bytes y ver si con ayuda de los números mágicos podemos identificar de que tipo e archivo se trata , y si coinciden los bytes **42 4d** con el tipo de archivo de imagen bmp .

viendo el formato del archivo encontramos la información de en que offset se encuentra cada parte del encabezado y analizando en un editor hexadecimal la información vemos que hay algunos offset que están apagados ya que tienen como valor  **ba d0** así que procedemos a cambiar esos bytes

primero cambiamos los offset **0A** para decirle donde acaba el encabezado es decir donde empieza la información de la imagen.(esta acaba en el 28 o sea 40 en decimal ya que ese es el tamaño del encabezado ).

después cambiamos el byte del offset **0E** el cual indica el tamaño del encabezado y de antemano sabemos que el tamaño es 40 que al transformarlo a hexa es  28

con estos cambios vemos que la imagen ya se puede abrir y que se muestra de forma correcta pero es raro que la imagen tenga tan poca altura considerando que pesa casi 3 megas por lo cual es muy extraño .

así que cambiamos el valor del byte del offset que indica el tamaño de la altura que es es el **16** lo cambiamos por un valor mas grande y BINGO tenemos la bandera 
(valores iniciales de la imagen )

![[Pasted image 20231016015924.png]]

(valores despues de editar los bytes )
![[Pasted image 20231016015349.png]]

(ss de imagen resultante )
![[Pasted image 20231016142849.png]]

### Flag
picoCTF{qu1t3_a_v13w_2020}

[BMP file format - Wikipedia](https://en.wikipedia.org/wiki/BMP_file_format)

|Hexágono desplazado|Desplazamiento dec|Tamaño|Propósito|
|---|---|---|---|
|0A|10|4 bytes|El desplazamiento, es decir, la dirección inicial, del byte donde se pueden encontrar los datos de la imagen de mapa de bits (matriz de píxeles).|
|0E|14|4|El tamaño de este encabezado, en bytes (40)|
|16|22|4|La altura del mapa de bits en píxeles (entero con signo)|

