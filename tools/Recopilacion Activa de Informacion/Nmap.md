| Opcion | Accion|
|---------|----|
|-sn | realizar un escaneo de descubrimiento de host sin realizar un escaneo de puertos. se utiliza para determinar qué hosts están activos en una red sin escanear los puertos abiertos en esos hosts  |
|-PS| Esta opción se utiliza para descubrir qué puertos están abiertos en un host mediante el envío de paquetes TCP SYN.|
|-sS| hace lo mismo que la opción -Ps co la diferencia de que no termina de hacer las conexiones haciendo que sea menos intrusivo|
|-sV|Especifica que se realice un escaneo de versiones de servicios. Esto implica que Nmap intentará determinar la versión de los servicios que se están ejecutando en los puertos abiertos.|
|-P-|se utiliza para realizar un escaneo de todos los puertos en un host.|
|-O|En otras palabras, esta opción se utiliza para obtener información sobre el sistema operativo que está activo en un host|
|-sC| es un atajo para –script=default, que ejecuta los scripts de Nmap que se consideran seguros y útiles para el escaneo de puertos12. Estos scripts pueden proporcionar información adicional sobre los servicios, vulnerabilidades o configuraciones de los puertos escaneados2.|
|-oX|exporta los resultados a un fichero xml|
|-sU|La opción -sU de Nmap es un atajo para –scan-type=udp, que realiza un escaneo de puertos UDP12. Los puertos UDP son aquellos que usan el protocolo UDP, que es un protocolo de transporte sin conexión que no garantiza la entrega de los paquetes2. Algunos servicios que usan puertos UDP son DNS, SNMP, DHCP, etc2.|
|-A|va realizar la misma operación que con `-O` y varias cosas adicionales. Por ejemplo, activa el motor de scripts de nmap|
|--script|para usar alguno de los scripts automatizados de nmap|

![[Pasted image 20231019223557.png]]