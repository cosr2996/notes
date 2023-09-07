### Que es?

es una herramienta de seguridad de red que se utiliza para responder a solicitudes de protocolos de red comunes como SMB, HTTP y FTP. [Esta herramienta se utiliza para realizar ataques de tipo “man-in-the-middle” y puede ser utilizada para robar contraseñas y credenciales de usuario](https://www.kali.org/tools/responder/)

creada por los genios de SpiderLabs para hacernos la vida más fácil a la hora de realizar auditorías principalmente en entornos Windows; su objetivo principal es la obtención de credenciales de usuario y hashes.

Se trata de una herramienta bastante sencilla de utilizar y que no necesita de profundos conocimientos técnicos para obtener resultados, pero también puede tener consecuencias inesperadas en el funcionamiento normal de la red si no se conoce como pueden afectarle las distintas funcionalidades de Responder.

### Funcionamiento

El comando básico para iniciar Responder con las opciones por defecto es:

Responder -i [IP]

Donde [IP] es la dirección IP donde queremos redirigir el tráfico (generalmente la nuestra).

La potencia de Responder radica principalmente en la implementación de los siguientes ataques:

- LLMNR (Link-Local Multicast Name Resolution) Poisoning.
- NBT-NS (NetBIOS Name Service) Poisoning.
- ICMP (Internet Control Message Protocol) Redirect.
- DHCP (Dynamic Host Configuration Protocol) Inform.

Para refrescarnos la memoria, explicaré brevemente en qué consisten estos protocolos y sus respectivos ataques:

**1.- LLMNR y NBT-NS Poisoning**

Cuando un equipo Windows necesita resolver un nombre, utiliza estos servicios de resolución de nombres con la siguiente prioridad:

_Localhost file -> DNS -> LLMNR (A partir de Windows Vista) -> NBT-NS_

Tanto LLMNR como NBT-NS utilizan peticiones multicast, por lo que cuando un host pregunta por un nombre y fallan las resoluciones (a través del archivo localhost y la petición DNS), una petición multicast es enviada (LLMNR en caso de Windows Vista o superiores y NBT-NS en el caso contrario). Es entonces cuando Responder aprovecha para enviarle una respuesta envenenada al solicitante indicándole que el nombre por el que pregunta corresponde con nuestra máquina (o la que hayamos indicado con la opción obligatoria “-i”)

Aunque por defecto contesta a todas las peticiones, es capaz de filtrar a quien contesta y a quien no basándose en la IP o el nombre NBT/LLMNR. Esto se consigue editando los campos RespondTo, RespondToName, DontRespondTo y DontResponToName respectivamente en el fichero Responder.conf.

**2.- ICMP Redirect**

El envío legítimo de un paquete ICMP Redirect sucede en la siguiente situación:

Una puerta de enlace G1 recibe un paquete P de un host de su red. Entonces G1 consulta su tabla de rutas y obtiene la dirección de la siguiente puerta de enlace G2 para que P llegue a su destino en la red X. Si G2 pertenece a la red del host originador del paquete, entonces G1 envía un _ICMP Redirect_ al host para que cambie su tabla de rutas, diciéndole que si quiere enviar un paquete a la red X, utilice como puerta de enlace directamente G2, ya que es un camino más corto hasta X.

Responder envía paquetes ICMP Redirect no legítimos haciéndose pasar por la pasarela original e indicando que nuestro equipo es la mejor ruta para llegar al destino, haciendo que la víctima envíe el tráfico a nuestro equipo en vez de a la verdadera puerta de enlace.

**3.- DHCP Inform**

Los hosts con Windows 2003/XP están enviando periódicamente peticiones DHCP Inform sin comprobar si la respuesta a esta petición es legítima, lo que permite sobrescribir la configuración de red del equipo generador de la petición.

Además, para sacarle provecho a los ataques anteriormente mencionados Responder implementa una serie de Rogue servers de autenticación con el fin de capturar los usuarios, hashes NTLMv1, NTLMv2, NTLMSSP, MSKerberosv5, credenciales en claro y autenticación básica. Entre los que se encuentran:

- HTTP/S.
- LDAP.
- FTP.
- Kerberos.
- MSSQL.
- SMB.
- POP3.
- IMAP.
- SQL.
- SMTP.
- WPAD proxy.

Además implementa un pequeño servidor DNS que responde a consultas de tipo A, lo que es muy útil combinado con ataques de ARP spoofing o ICMP Redirect.

Por defecto se inician todos los servicios enunciados anteriormente, pero es posible desactivarlos a voluntad editando el valor de las variables de cada uno de ellos a “On” o “Off” en el fichero de configuración Responder.conf.

### Advertencias

Los Rogue servers SQL Server, HTTP, HTTPS y LDAP sólo serán utilizados por los equipos con un Windows igual o superior al Windows Vista, ya que hay que tener en cuenta que las versiones anteriores de Windows no implementan el protocolo LLMNR y Responder por defecto solo responde a peticiones NBT-NS correspondientes al servicio de _transferencia de archivos_ (SMB).

Si queremos que responda a peticiones NBT-NS del servicio _workstation name_ para que estos servicios tengan efecto en máquinas con un Windows anterior a Windows Vista, debemos añadir la opción “-r”, y para las peticiones de dominio debemos añadir “-d”. Ambas opciones no son recomendables para ejecutar en entornos delicados en producción o si queremos no llamar mucho la atención, ya que desestabilizará notablemente el funcionamiento de la red, y es por eso que vienen desactivadas por defecto.

Cabe destacar que a partir de la versión 2.0, Responder incluye un modo _Analyzer_ muy útil para hacer un descubrimiento pasivo de la red analizando las peticiones multicast sin responderlas, además de informarnos de la viabilidad de los ataques _ICMP redirect_. Para utilizar este modo sólo tendremos que ejecutar Responder de la siguiente manera:

```shell
Responder -i “nuestra_ip” –A.
```

### Resultados

Una vez ejecutado el ataque, Responder irá almacenando las credenciales obtenidas en archivos de texto independientes con el siguiente formato de nombre, para procesarlas posteriormente:

```shell
(SMB | MSSQL | HTTP)-(ntlm-v1 | v2 | clear-text)-Client_IP.txt
```

Que contendrá el hash en el siguiente formato:

```shell
usuario::DOMINIO:1122334455667788:2624988FCE9678E572E2F9F871F89135:01010000000000003AE
36AED1EA4D001F128XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXA007A
0070007A0064006900720066006E007000630061003A00380030000000000000000000
```

También se generará un fichero con el siguiente formato:

```shell
(Servicio)-Clear-Text-Password-Client_IP.txt
```

Que contendrá la siguiente información:

```shell
usuario:contraseña
```

Además del _output_ generado por la aplicación, todos los logs generados por esta sesión se guardarán en el archivo que indiquemos en la variable SessionLog del archivo de configuración Responder.conf, que por defecto es Responder-Session.log.