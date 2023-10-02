### Level Goat

ROT13 es un cifrado de sustitución simple.

Los cifrados de sustitución son un algoritmo de sustitución simple. En este ejemplo
de un cifrado de sustitución, exploraremos un cifrado 'monoalfebético'.
Monoalfebético significa, literalmente, "un alfabeto" y verás por qué.

Este nivel contiene una forma antigua de cifrado llamado 'Cifrado César'.
Un cifrado César cambia el alfabeto en un número determinado. Por ejemplo:

simple: a b c d e f g h i j k ...
cifrado: G H I J K L M N O P Q ...

En este ejemplo, la letra 'a' en texto plano se reemplaza por una 'G' en el
texto cifrado, por lo que, por ejemplo, el texto plano 'malo' se convierte en 'HGJ' en texto cifrado.

La contraseña para el nivel 3 está en el archivo krypton3. esta en 5 letras
texto cifrado grupal. Está cifrado con un cifrado César. Sin ningún
Para obtener más información, este texto cifrado puede resultar difícil de descifrar. Tú haces
No tienes acceso directo a la clave, sin embargo sí tienes acceso a un programa.
eso cifrará todo lo que desee darle usando la clave.
Si piensas lógicamente, esto es completamente fácil.

¡Un disparo puede resolverlo!

Divertirse.

Información adicional:

El binario `encrypt` buscará el archivo de claves en su archivo de trabajo actual.
directorio. Por lo tanto, podría ser mejor crear un directorio de trabajo en /tmp
y allí un enlace al archivo de claves. Mientras el binario `encrypt` ejecuta setuid
`krypton3`, también debes darle acceso a `krypton3` a tu directorio de trabajo.

Aquí hay un ejemplo:

kriptón2@melinda:~$ mktemp -d
/tmp/tmp.Wf2OnCpCDQ
krypton2@melinda:~$ cd /tmp/tmp.Wf2OnCpCDQ
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ ln -s /krypton/krypton2/keyfile.dat
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ ls
archivo clave.dat
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ chmod 777.
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ /krypton/krypton2/encrypt /etc/issue
krypton2@melinda:/tmp/tmp.Wf2OnCpCDQ$ ls
archivo de claves de texto cifrado.dat
### Credentials
ssh krypton2@krypton.labs.overthewire.org -p 2231
pass: ROTTEN
### Solution
```shell

```
