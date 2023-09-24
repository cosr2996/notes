| Opcion | Accion|
|---------|----|
|-sn | realizar un escaneo de descubrimiento de host sin realizar un escaneo de puertos. se utiliza para determinar qué hosts están activos en una red sin escanear los puertos abiertos en esos hosts  |
|-PS| Esta opción se utiliza para descubrir qué puertos están abiertos en un host mediante el envío de paquetes TCP SYN.|
|-sS| hace lo mismo que la opción -Ps co la diferencia de que no termina de hacer las conexiones haciendo que sea menos intrusivo|
|-sV|Especifica que se realice un escaneo de versiones de servicios. Esto implica que Nmap intentará determinar la versión de los servicios que se están ejecutando en los puertos abiertos.|
|-P-|se utiliza para realizar un escaneo de todos los puertos en un host.|
|-O|En otras palabras, esta opción se utiliza para obtener información sobre el sistema operativo que está activo en un host|
|-sC||
|-oX|exporta los resultados a un fichero xml|
|-sU||
|-A|va realizar la misma operación que con `-O` y varias cosas adicionales. Por ejemplo, activa el motor de scripts de nmap|
|--script|para usar alguno de los scripts automatizados de nmap|
