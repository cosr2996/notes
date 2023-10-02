### Level Goat

La contraseña para el nivel 2 está en el archivo 'krypton2'. Lo es 'encriptado' usando una rotación simple. También está en no estándar Formato de texto cifrado. Cuando se utilizan caracteres alfabéticos para el texto cifrado, es normal para agrupar las letras en 5 grupos de letras, independientemente de Límites de palabras. Esto ayuda a ofuscar cualquier patrón. Este archivo tiene Mantuvo los límites de las palabras de texto sin formato y los llevó al cifrado Mensaje de texto. ¡Disfrutar!
### Credentials

ssh krypton1@krypton.labs.overthewire.org -p 2231
pass: KRYPTONISGREAT
### Solution

```shell
krypton1@bandit:/krypton/krypton1$ ls
krypton2  README
krypton1@bandit:/krypton/krypton1$ cat README 
Welcome to Krypton!

This game is intended to give hands on experience with cryptography
and cryptanalysis.  The levels progress from classic ciphers, to modern,
easy to harder.

Although there are excellent public tools, like cryptool,to perform
the simple analysis, we strongly encourage you to try and do these
without them for now.  We will use them in later excercises.

** Please try these levels without cryptool first **


The first level is easy.  The password for level 2 is in the file 
'krypton2'.  It is 'encrypted' using a simple rotation called ROT13.  
It is also in non-standard ciphertext format.  When using alpha characters for
cipher text it is normal to group the letters into 5 letter clusters, 
regardless of word boundaries.  This helps obfuscate any patterns.

This file has kept the plain text word boundaries and carried them to
the cipher text.

Enjoy!
krypton1@bandit:/krypton/krypton1$ cat krypton2 
YRIRY GJB CNFFJBEQ EBGGRA
krypton1@bandit:/krypton/krypton1$ echo 'YRIRY GJB CNFFJBEQ EBGGRA' | tr 'A-Za-z' 'N-ZA-Mn-za-m'  
LEVEL TWO PASSWORD ROTTEN

```

