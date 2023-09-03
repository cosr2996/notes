# Level-26 -> Level-27

### Level Goat
Good job getting a shell! Now hurry and grab the password for bandit27!
### Credentials
ssh bandit26@bandit.labs.overthewire.org -p 2220
password: **c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1**
### Solution
aplicamos lo mismo que en el nivel pasado reduciendo el tamaño de la terminal para iniciar more
![[Screenshot 2023-09-02 154203.png]]
Establecemos el bash que queremos que se use para ejecutar comandos desde vim 
![[Screenshot 2023-09-02 164657.png]]
abrimos una nueva instancia de shell
![[Screenshot 2023-09-02 164714.png]]
se abre una nueva ventana o pestaña que muestra el prompt del shell
![[Screenshot 2023-09-02 164731.png]]
```shell
bandit26@bandit:~$ ls -l                                                                                         
total 20                                                                                                            
-rwsr-x--- 1 bandit27 bandit26 14876 Apr 23 18:04 bandit27-do                           -rw-r----- 1 bandit26 bandit26   258 Apr 23 18:04 text.txt                                                          
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS                                                                                    
bandit26@bandit:~$
```
### Summary
La línea "set shell=/bin/bash" en Linux se utiliza en el contexto del editor de texto [Vim](https://www.google.com/search?q=Vim) para establecer el shell que se utilizará para ejecutar comandos externos desde Vim.

Cuando [Vim](https://www.google.com/search?q=Vim) necesita ejecutar un comando externo, como al utilizar la función "!command" o al utilizar ciertas características de [Vim](https://www.google.com/search?q=Vim) como la expansión de comandos (`:r !command`), utiliza el shell especificado en la variable de entorno `shell`.

En este caso, la línea "set shell=/bin/bash" establece el shell de Unix/Linux como [Bash](https://www.google.com/search?q=Bash), que es uno de los shells más comunes y potentes disponibles en la mayoría de las distribuciones de Linux.

Al establecer la variable `shell` en "/bin/bash", se le indica a [Vim](https://www.google.com/search?q=Vim) que utilice [Bash](https://www.google.com/search?q=Bash) como el shell preferido para ejecutar comandos externos dentro del editor. Esto puede ser útil si deseas aprovechar las características y funcionalidades específicas de [Bash](https://www.google.com/search?q=Bash) al ejecutar comandos desde [Vim](https://www.google.com/search?q=Vim).



La línea ":shell" en Vim en Linux se utiliza para abrir una subshell o una nueva instancia del shell en el entorno de [Vim](https://www.google.com/search?q=Vim). Esto te permite ejecutar comandos de shell sin abandonar [Vim](https://www.google.com/search?q=Vim) por completo.

Cuando ingresas ":shell" en [Vim](https://www.google.com/search?q=Vim), se abre una nueva ventana o pestaña que muestra el prompt del shell. Desde esta subshell, puedes ejecutar comandos de shell como lo harías normalmente en una terminal.

Una vez que hayas terminado de ejecutar comandos en la subshell, puedes salir de ella y regresar a [Vim](https://www.google.com/search?q=Vim) presionando Ctrl+D o escribiendo "exit" en el prompt del shell.

Esta función es útil cuando deseas realizar rápidamente algunas operaciones de shell sin cerrar [Vim](https://www.google.com/search?q=Vim) por completo. Te permite alternar entre [Vim](https://www.google.com/search?q=Vim) y el shell de forma conveniente y eficiente.
### FLAG
**flag** 