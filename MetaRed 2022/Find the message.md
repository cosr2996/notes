#Stego #metadata 
# Descripción:
You have the file 2023Metared.jpg Can you find the flag?
 [2023Metared.jpg](https://ctfd.anuies.mx/files/bc8e90261d26030d76237cba0791d30b/2023Metared.jpg?token=eyJ1c2VyX2lkIjoyMTQsInRlYW1faWQiOjkzLCJmaWxlX2lkIjoxNX0.ZR7Qiw.xOFYYw7eyHOUwSwL9NlVpOYzF0M)You have the file 2023Metared.jpg Can you find the flag?
# Solución:
```shell
omar@omar-pc:~/Descargas/first$ ls
2023Metared.jpg
omar@omar-pc:~/Descargas/first$ binwalk 2023Metared.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
30            0x1E            TIFF image data, little-endian offset of first image directory: 8
534           0x216           JPEG image data, JFIF standard 1.01
484909        0x7662D         PDF document, version: "1.6"

omar@omar-pc:~/Descargas/first$ binwalk --dd='.*' 2023Metared.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
30            0x1E            TIFF image data, little-endian offset of first image directory: 8
534           0x216           JPEG image data, JFIF standard 1.01
484909        0x7662D         PDF document, version: "1.6"

omar@omar-pc:~/Descargas/first$ ls
2023Metared.jpg  _2023Metared.jpg.extracted
omar@omar-pc:~/Descargas/first$ cd _2023Metared.jpg.extracted/
omar@omar-pc:~/Descargas/first/_2023Metared.jpg.extracted$ ls
0  1E  216  7662D
omar@omar-pc:~/Descargas/first/_2023Metared.jpg.extracted$ exiftool 0

```
# Bandera:
flagMX{Always use two-step authentication (2FA)}

# Resumen:
Descargamos el archivo que es una imagen analizando la imagen nos damos cuenta de que la imagen tiene archivos ocultos dentro, las extraemos con ayuda de binwalk y entramos en la carpeta , revisamos los archivos que hay y encontramos un pdf con contraseña , tenemos que encontrar la contraseña.

se me ocurre revisar los meta-datos de loa archivos al examinar los de la imagen con nombre 0 encontramos algo curioso

![[Captura de pantalla de 2023-10-05 09-43-02.png]]

así que busco las coordenadas en google maps
![[map.png]]

exploramos un poco el mapa y nos encontramos con una universidad, curioso?
![[Captura de pantalla de 2023-10-05 09-57-02.png]]

decido probar el nombre de la iniversidad como contraseña para el pdf y no funciona , quito el espacio y trato de nuevo y funciono tenemos acceso al pdf .

parece vacio , pero encontramos un texto en formato extraño
![[Captura de pantalla de 2023-10-05 09-53-08.png]]

si pegamos ese texto enalgun otro lado se revela la bandera