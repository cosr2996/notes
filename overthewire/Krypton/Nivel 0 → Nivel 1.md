
### Level Goat
¡Bienvenido a Krypton! El primer nivel es fácil. La siguiente cadena codifica la contraseña usando Base64:

```
S1JZUFRPTklTR1JFQVQ=
```

Utilice esta contraseña para iniciar sesión en krypton.labs.overthewire.org con nombre de usuario krypton1 usando SSH en el puerto 2231. Puede encontrar los archivos para otros niveles en /criptón/

### Credentials
ssh krypton1@krypton.labs.overthewire.org -p 2231
pass: KRYPTONISGREAT

### Solution
```shell
┌──(kali㉿kali)-[~]
└─$ echo "S1JZUFRPTklTR1JFQVQ=" | base64 -d          
KRYPTONISGREAT 
```

