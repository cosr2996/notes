**DNSRecon** es una herramienta o secuencia de comandos gratuita y de código abierto que está disponible en GitHub. Dnsrecon es uno de los scripts populares en la comunidad de seguridad que se utiliza para el reconocimiento de dominios. Este script está escrito en lenguaje python. Debe tener el lenguaje python instalado en su sistema operativo Kali Linux para poder usar el script. 

Este script verifica todos los registros DNS para AXFR, lo que puede ser útil para un investigador de seguridad para la enumeración de DNS en todo tipo de registros, como **SOA, NS, TXT, SVR, SPF** , etc. Este script también usó Google dorks para obtener subdominios indexados por robot de Google.

Los tipos de enumeración que realiza dnsrecon son los siguientes:

• Zona de Traspasos  
• Inversa  
• Dominios y host de fuerza bruta  
• Enumeración de grabación estándar (comodín, SOA, MX, A, TXT, etc)  
• Caché Snooping  
• Zona de Walking  
• Búsqueda de google