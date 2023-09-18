## Para qué sirve Wireshark

Los problemas que este software es capaz de llegar a abordar van desde paquetes caídos, problemas de latencia y hasta actividad maliciosa en su red, por ejemplo, por medio de peticiones HTTP. Permite analizar la red como si viéramos una placa con un microscopio en un laboratorio por así decirlo y proporciona herramientas y comandos para filtrar y analizar con más detalles el tráfico de red, acercándose a la causa raíz del problema.

Los administradores de sistemas y de red lo usan para identificar dispositivos defectuosos que están descartando paquetes, problemas de latencia en peticiones causadas por máquinas defectuosas que enrutan el tráfico de red a cualquier lado del mundo posible y exfiltraciones de datos o incluso intento de ataque con malware o de piratería contra una organización.

Esté analizador de redes es una herramienta poderosa que requiere un conocimiento sólido de los conceptos de estas mismas. Eso se traduce para las empresas de hoy en día modernas en comprender sobre protocolos HTTP y sus servicios, la pila de TCP / IP, analizar y comprender los encabezados de los paquetes que se reciben con muchos metadatos a veces complejos, así como el enrutamiento y como se entrelazan unos a otros, el reenvío de puertos y DHCP, por ejemplo.

## Características Wireshark

Podríamos escribir solo un artículo nombrando las características principales y todos sus poderes y que abanico de oportunidades nos traen, pero solo las comentaremos brevemente por encima.

- Permite seguir el rastro a los paquetes TCP stream, podemos ver todo lo relacionado con dicho paquete, el antes y el después, pudiendo aplicarles filtros personalizados a estos mismos sin perder el flujo.
- Se puede decodificar los paquetes y exportar en formatos específicos y guardar dichos objetos.
- Permite ver **estadísticas de los paquetes capturados** incluyendo un resumen, jerarquía de protocolos, conversaciones, puntos finales y gráfica de flujos entre otros.
- Análisis fácil e informativo mediante resolución de nombres por mac, por red, etc… y reensamblaje de paquetes.
- Cuenta con una herramienta de líneas de comandos para ejecutar funcionalidades llamada TShark, similar al terminal de linux. Entre los comandos más destacados, podemos mencionar rawshark, editcap, mergecap, text2pcap.

## Wireshark: Ventajas y desventajas de uso

Whireshark siendo un software tan grande y robusto analizador de red y paquetes, es casi evidente que tiene más ventajas que desventajas, muchas más. Es lo que hace que sea un software tan usado y conocido. Cuando lo empiecen a usar se darán cuenta de todo lo que se puede llegar a hacer con él.

Entre sus ventajas más destacadas encontramos que tiene un soporte detrás de esas analíticas que saca brutal, con mucho personal a cargo de nuevas funciones, parches y solucionando errores que la comunidad detecta, eso incluye su **documentación extensa** y no muy laboriosa de leer y aplicar, aparte también cuenta con una comunidad enorme, que ayuda a la mínima de cambio cuando alguien necesita buscar algo muy específico en esos paquetes de red y disectores. Captura también todo tipo de paquetes al analizar la red. Muestra errores y problemas en niveles por debajo del protocolo HTTP. Guardar y restaurar los datos empaquetados capturados, en **ficheros pcap**.

Entre sus desventajas, que también tiene, aunque sean lo de menos importancia, cabe destacar que al analizar la red no se pueden modificar datos de los paquetes, solo mediante ficheros de red, sus pcap. Y la interfaz que usa no está mal, pero es poco intuitiva y se le podría dar un pulido y ponerla más funcional e intuitiva, por los tiempos en los que nos encontramos.