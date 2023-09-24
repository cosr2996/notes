## E**steganografía**, ocultar un archivo dentro de otros

ocultar archivos dentro de otros, se le llama **Esteganografía**, que es «_el estudio y aplicación de técnicas que permiten ocultar mensajes u objetos, dentro de otros, llamados portadores, para ser enviados y de modo que no se perciba el hecho. Es decir, procura ocultar mensajes dentro de otros objetos y de esta forma establecer un canal encubierto de comunicación, de modo que el propio acto de la comunicación pase inadvertido para observadores que tienen acceso a ese canal_«.

## Ocultar archivos en una imagen completamente funcional

Antes de detallar los pasos a seguir, vamos a decir qué vamos a hacer: vamos a coger una carpeta, en mi caso CarpetaSecreta, que será la que tendrá todos los archivos, vamos a comprimir dicha carpeta y crear el archivo **CarpetaSecreta.zip, unirla a una imagen** llamada Imagen.png que será «el disfraz» o «tapadera» y crear un archivo que solo mostrará una imagen pero tendrá todos los archivos dentro, que en mi caso será Captura.png. Los pasos a seguir serían los siguientes:

1. Ponemos la imagen y la carpeta que queremos ocultar (CarpetaSecreta) dentro de una misma carpeta, la que sea. Por ejemplo, en Documentos.
2. Si no lo hemos hecho ya, metemos todos los archivos que queramos ocultar en CarpetaSecreta. Yo he eliminado el espacio en el nombre de la carpeta para facilitar las cosas en el terminal.
3. Comprimimos la carpeta. Esto podemos hacerlo haciendo clic derecho y usando nuestro compresor por defecto.
4. Abrimos el terminal.
5. Vamos a la carpeta donde están juntos CarpetaSecreta.zip e Imagen.png, en mi caso el comando sería _cd /home/pablinux/Escritorio_.
6. El siguiente paso es «concatenar» los archivos CarpetaSecreta.zip e Imagen.png en el archivo de salida Captura.png. El comando para mi ejemplo sería el siguiente:


```shell
cat Imagen.png CarpetaSecreta.zip > Captura.png
```



##  INTRODUCCIÓN A STEGHIDE

Steghide puede ser un dispositivo de esteganografía que te permite **encubrir registros confidenciales dentro de un registro de imagen o sonido con una frase de contraseña**. Refuerza los grupos de imagen BMP y JPEG, y los grupos de sonido AU y WAV. Por defecto, utiliza Rijndael ([AES](https://es.wikipedia.org/wiki/Advanced_Encryption_Standard)) para encubrir el registro y la medida clave es de 128 bits.

Esta herramienta tiene sus ventajas y desventajas. Una ventaja es que es significativamente mejor para disimular y puede, sin mucho esfuerzo, cubrir cualquier tipo de documento. Lo hace como tal utilizando un cálculo propulsado para envolverlo dentro del registro de imagen (o sonido) sin cambiar la apariencia del documento. Esto adicionalmente implica que sin utilizar steghide es difícil **extraer los documentos ocultos de la imagen**.

- [==Steghide: Esteganografía para ocultar datos en Imágenes==](https://esgeeks.com/steghide-para-ocultar-datos-en-imagenes/)

Caracteristicas:

- Compresión de datos incrustados.
- BMP, GIF y JPG compatibles.
- Cifrado de datos incrustados.
- Descifrado por contraseña.
- Utiliza varios algoritmos para el cifrado.