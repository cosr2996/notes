#Misc #base64 #email #encrypt #vigenere
# Descripción:
The security area intercepted a communication from an employee who is selling critical information.
# Solución:
descargamos el archivo el cual es un .eml , es un tipo de archivo que se usa para correo electrónico dentro guarda el mensaje los correos archivos adjuntos etc.

email:
The TechDart3 attachment contains the access details.JbZigma will provide access to the password.Submit payment as directed.

vemos que tiene un file.7z adjunto , lo descargamos y intentamos  descomprimir pero tiene contraseña así que leyendo bien el correo intento poner como contraseña TechDart3 y funciona  .

nos encontramos con un archivo txt con mucho texto que parece ser base64, lo metemos en cyberchef y resulta si ser base64 edemas de que se trataba de una imagen así que tambien la renderisa
![[Captura de pantalla de 2023-10-05 10-17-04.png]]

copiamos el texto que da la imagen y lo pasamos igual por cyberchef y nos da la siguiente cadena
omzoSJ{Dnuzqre aaf huvarcbmb}

esta encritada en vigenere y la llave venia en el correo JbZigma
![[Captura de pantalla de 2023-10-05 12-08-18.png]]

# Bandera:
flagMX{Details are important}
# Resumen:
Los archivos que contienen una extensión EML **corresponden con los correos electrónicos** que por lo general se envían o se reciben por una aplicación de correo electrónico asociado a Microsoft Outlook, si bien también puede ser creados por otros clientes de correo electrónico. Dentro de estos archivos se incluye el contenido del mensaje, junto con el asunto, el remitente, los destinatarios, archivos adjuntos enviados por el remitente, hipervínculos y la fecha del mensaje. Generalmente, los archivos EML quedan almacenados en formato de texto sin formato.