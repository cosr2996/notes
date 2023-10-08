#Injection #vitualMachine #php #script
# Descripción:
Derived from the fact that the company does not have funds to buy a new sales system, it has been decided to request an intern or social service to carry out this system. The system is ready and for being the first program the student does it looks very good. Is it really a secure system?
# Solución:

![[Captura de pantalla 2023-10-05 201337.png]]
![[Captura de pantalla 2023-10-05 201345.png]]
![[Pasted image 20231005201630.png]]
el script que se suvio
```php
<?php

$resultado = exec("less /etc/passwd");

print "Salida: $resultado\n"; 

?>
```

# Bandera:
flagMX{Code inyection is always in the top ten of vulnerabilities}
# Resumen:
descargamos un archivo que es una pagina web con dos enlaces que descargan un archivo .ova (para virtual box) el otro no importa ya que solo sirve para comprobar que funcione bien la maquina virutal.

después de montar la maquina virtual vemos que se trata de un login , pero si vemos detenidamente arriba hay una dirección ip que al buscarla en el navegador vemos que es una pagina para subir archivos y visualizarlos.

aprovecharemos el echo de que nos deje subir archivos al servidor, creamos un script con php ya que la pagina usa php, este escript tendrá la función de leer el archivo /etc/passwd y mostrarlo.

lo subimos y visualizamos y copiamos la bandera