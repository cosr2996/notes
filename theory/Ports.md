## Lista de los puertos más importantes

Entre los más de 65 000 puertos TCP y UDP disponibles, hay algunos códigos de identificación que son muy importantes para la comunicación en internet. Aquí te presentaremos los puertos bien conocidos y registrados más importantes. Hay puertos que solo cuentan con autorización para uno de los dos protocolos (TCP o UDP). También hay puertos que no se han reservado oficialmente para un servicio determinado, pero que, en la práctica, se han ido asentando con el tiempo. Algunos puertos incluso cuentan con una ocupación doble.

### Well-known ports

|Puerto|TCP|UDP|Nombre|Descripción|
|---|---|---|---|---|
|1|✔|✔|tcpmux|Multiplexor TCP|
|5|✔|✔|rje|Entrada de tarea remota (remote job entry)|
|7|✔|✔|echo|Protocolo Echo|
|9|✔|✔|discard|Protocolo Discard (evaluación de conexiones)|
|11|✔|✔|systat|Información del sistema (enumera los puertos conectados)|
|13|✔|✔|daytime|Protocolo Daytime: indica fecha y hora|
|17|✔|✔|qotd|Envía la cita del día (quote of the day)|
|18|✔|✔|msp|Protocolo de envío de mensajes|
|19|✔|✔|chargen|Protocolo Chargen: envía una cadena infinita de caracteres|
|20|✔||ftp-data|Transmisión de datos FTP|
|21|✔|✔|ftp|Conexión FTP|
|22|✔|✔|ssh|Servicio Secure Shell|
|23|✔||telnet|Servicio Telnet|
|25|✔||smtp|Simple Mail Transfer Protocol|
|37|✔|✔|time|Protocolo de tiempo legible de forma mecanizada|
|39|✔|✔|rlp|Protocolo de envío de recursos (Resource Location Protocol)|
|42|✔|✔|nameserver|Servicio de nombres|
|43|✔||nicname|Servicio de directorio WHOIS|
|49|✔|✔|tacacs|Terminal Access Controller Access Control System|
|50|✔|✔|re-mail-ck|Protocolo de verificación de correo remoto (Remote Mail Checking)|
|53|✔|✔|domain|Resolución de nombres por DNS|
|67||✔|bootps|Protocolo Bootstrap (servidor)|
|68||✔|bootpc|Protocolo Bootstrap (cliente)|
|69||✔|tftp|Protocolo Trivial de Transferencia de Ficheros (Trivial File Transfer Protocol)|
|70|✔||gopher|Búsqueda de documentos|
|71|✔||genius|Protocolo Genius|
|79|✔||finger|Proporciona información de contacto de usuarios|
|80|✔||http|Protocolo de Transferencia de HiperTexto (Hypertext Transfer Protocol)|
|81|✔|||Torpark: Onion-Routing (no oficial)|
|82||✔||Torpark: Control (no oficial)|
|88|✔|✔|kerberos|Sistema de autenticación de red|
|101|✔||hostname|Servicios de nombres de host (NIC Host Name)|
|102|✔||Iso-tsap|Protocolo ISO-TSAP|
|105|✔|✔|csnet-ns|Servidor de correo|
|107|✔||rtelnet|Telnet remoto|
|109|✔||pop2|Post Office Protocol v2 para comunicación de correo electrónico|
|110|✔||pop3|Post Office Protocol v3 para comunicación de correo electrónico|
|111|✔|✔|sunrpc|Protocolo RPC para NFS|
|113||✔|auth|(Antiguo) servicio de autenticación|
|115|✔||sftp|Protocolo de transferencia de archivos seguros o Simple File Transfer Protocol (versión simplificada de FTP)|
|117|✔||uucp-path|Transmisión de datos entre sistemas Unix|
|119|✔||nntp|Transmisión se noticias en Newsgroups|
|123||✔|ntp|Protocolo de sincronización de tiempo|
|137|✔|✔|netbios-ns|NETBIOS Servicio de nombres|
|138|✔|✔|netbios-dgm|NETBIOS Servicio de envío de datagramas|
|139|✔|✔|netbios-ssn|NETBIOS Servicio de sesiones|
|143|✔|✔|imap|Internet Message Access Protocol para comunicación de correo electrónico|
|161||✔|snmp|Simple Network Management Protocol|
|162|✔|✔|snmptrap|Simple Network Management Protocol Trap|
|177|✔|✔|xdmcp|X Display Manager|
|179|✔||bgp|Border Gateway Protocol|
|194|✔|✔|irc|Internet Relay Chat|
|199|✔|✔|smux|SNMP UNIX Multiplexer|
|201|✔|✔|at-rtmp|Enrutamiento AppleTalk|
|209|✔|✔|qmtp|Quick Mail Transfer Protocol|
|210|✔|✔|z39.50|Sistema de información bibliográfico|
|213|✔|✔|ipx|Internetwork Packet Exchange|
|220|✔|✔|imap3|IMAP v3 para comunicación de correo electrónico|
|369|✔|✔|rpc2portmap|Coda Filesystem Portmapper|
|370|✔|✔|codaauth2|Servicio Coda Filesystem Authentication|
|389|✔|✔|ldap|Lightweight Directory Access Protocol|
|427|✔|✔|svrloc|Service Location Protocol|
|443|✔||https|HTTPS (HTTP a través de SSL/TLS)|
|444|✔|✔|snpp|Simple Network Paging Protocol|
|445|✔||microsoft-ds|SMB a través de TCP/IP|
|464|✔|✔|kpasswd|Modificación de contraseña para Kerberos|
|500||✔|isakmp|Protocolo de seguridad|
|512|✔||exec|Remote Process Execution|
|512||✔|comsat/biff|Mail Client y Mail Server|
|513|✔||login|Inicio de sesión en ordenador remoto|
|513||✔|who|Whod User Logging Daemon|
|514|✔||shell|Remote Shell|
|514||✔|syslog|Servicio Unix System Logging|
|515|✔||printer|Servicios de impresión Line Printer Daemon|
|517||✔|talk|Talk Remote Calling|
|518||✔|ntalk|Network Talk|
|520|✔||efs|Extended Filename Server|
|520||✔|router|Routing Information Protocol|
|521||✔|ripng|Routing Information Protocol para IPv6|
|525||✔|timed|Servidor de tiempo|
|530|✔|✔|courier|Courier Remote Procedure Call|
|531|✔|✔|conference|Chat a través de AIM y IRC|
|532|✔||netnews|Servicio Netnews Newsgroup|
|533||✔|netwall|Broadcast de emergencia|
|540|✔||uucp|Unix-to-Unix Copy Protocol|
|543|✔||klogin|Kerberos v5 Remote Login|
|544|✔||kshell|Kerberos v5 Remote Shell|
|546|✔|✔|dhcpv6-client|DHCP v6 Client|
|547|✔|✔|dhcpv6-server|DHCP v6 Server|
|548|✔||afpovertcp|Apple Filing Protocol a través de TCP|
|554|✔|✔|rtsp|Control de streams|
|556|✔||remotefs|Remote Filesystem|
|563|✔|✔|nntps|NNTP a través de SSL/TLS|
|587|✔||submission|Message Submission Agent|
|631|✔|✔|ipp|Internet Printing Protocol|
|631|✔|✔||Common Unix Printing System (no oficial)|
|636|✔|✔|ldaps|LDAP a través de SSL/TLS|
|674|✔||acap|Application Configuration Access Protocol|
|694|✔|✔|ha-cluster|Servicio Heartbeat|
|749|✔|✔|kerberos-adm|Kerberos v5 Administration|
|750||✔|kerberos-iv|Servicios Kerberos v4|
|873|✔||rsync|Servicios de transmisión de datos rsync|
|992|✔|✔|telnets|Telnet a través de SSL/TLS|
|993|✔||imaps|IMAP a través de SSL/TLS|
|995|✔||pop3s|POP3 a través de SSL/TLS|




### Registered ports

|Puerto|TCP|UDP|Nombre|Descripción|
|---|---|---|---|---|
|1080|✔||socks|SOCKS Proxy|
|1433|✔||ms-sql-s|Microsoft SQL Server|
|1434|✔|✔|ms-sql-m|Microsoft SQL Monitor|
|1494|✔||ica|Citrix ICA Client|
|1512|✔|✔|wins|Windows Internet Name Service|
|1524|✔|✔|ingreslock|Ingres DBMS|
|1701||✔|l2tp|Layer 2 Tunneling Protocol/Layer 2 Forwarding|
|1719||✔|h323gatestat|H.323|
|1720|✔||h323hostcall|H.323|
|1812|✔|✔|radius|Autenticación RADIUS|
|1813|✔|✔|radius-acct|Acceso RADIUS|
|1985||✔|hsrp|Cisco HSRP|
|2008|✔|||Teamspeak 3 Accounting (no oficial)|
|2010||✔||Teamspeak 3 Weblist (no oficial)|
|2049|✔|✔|nfs|Network File System|
|2102|✔|✔|zephyr-srv|Zephyr Server|
|2103|✔|✔|zephyr-clt|Zephyr Client|
|2104|✔|✔|zephyr-hm|Zephyr Host Manager|
|2401|✔||cvspserver|Concurrent Versions System|
|2809|✔|✔|corbaloc|Common Object Request Broker Architecture|
|3306|✔|✔|mysql|Servicio de bases de datos MySQL (también para MariaDB)|
|4321|✔||rwhois|Remote Whois Service|
|5999|✔||cvsup|CVSup|
|6000|✔||X11|Servicios X Windows System|
|11371|✔||pgpkeyserver|Keyserver público para PGP|
|13720|✔|✔|bprd|Symantec/Veritas NetBackup|
|13721|✔|✔|bpdbm|Symantec/Veritas Database Manager|
|13724|✔|✔|vnetd|Symantec/Veritas Network Utility|
|13782|✔|✔|bpcd|Symantec/Veritas NetBackup|
|13783|✔|✔|vopied|Symantec/Veritas VOPIE|
|22273|✔|✔|wnn6|Conversión Kana/Kanji|
|23399||||Skype (no oficial)|
|25565|✔|||Minecraft|
|26000|✔|✔|quake|Quake y otros juegos multijugador|
|27017||||MongoDB|
|33434|✔|✔|traceroute|Seguimiento de red|
