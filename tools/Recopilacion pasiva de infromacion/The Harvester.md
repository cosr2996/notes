**The Harvester** es una herramienta de código abierto que se utiliza para recopilar información de correo electrónico y nombres de dominio de diferentes fuentes públicas, como motores de búsqueda, sitios web, servidores DNS y mucho más. La herramienta es muy útil para los profesionales de la seguridad cibernética y los investigadores de inteligencia, ya que les permite recopilar información sobre una organización o individuo específico.

The Harvester se puede utilizar para buscar direcciones de correo electrónico y nombres de dominio que estén relacionados con una organización o individuo específico. La herramienta también se puede utilizar para buscar información sobre un nombre de dominio específico, como la dirección IP asociada con el dominio, los servidores DNS asociados con el dominio y mucho más.

The Harvester es una herramienta muy poderosa y puede ser utilizada para recopilar información sensible. Por lo tanto, es importante utilizar la herramienta con precaución y asegurarse de que se utiliza solo con fines legítimos.

### opciones
-f que te mande los resultados a un archivo 
-l n limitar a n peticiones
-b para decirle en que fuentes busque 
-d para decirle que busque información sobre una organización concreta 

### Ejemplo 

```shell
theHarvester -d microsoft.com -b baisu,yahoo,duckduckgo,bing -l 100 -f resultados
```
### Bloqueo temporal de dirección IP pública

Después de realizar algunas peticiones con TheHarvester es posible que os aparezca un error similar al siguiente:

![](https://img-b.udemycdn.com/redactor/raw/article_lecture/2022-05-23_18-30-54-bffa03d329e4e99f17f4ee0de78b1222.png)

Este error nos indica que Google ha bloqueado nuestra dirección IP pública. Lo que quiere decir que no nos deja realizar peticiones a su servicio desde ningún dispositivo que se encuentre dentro de nuestra red local.

Este comportamiento es muy frecuente y también debe tenerse en cuenta para las siguientes herramientas que se presentan en esta sección. Si realizas muchas peticiones automatizadas en poco tiempo a servicio como Google, Bing, Shodan... utilizando herramientas como theHarvester, estos servicios suelen bloquear temporalmente tu dirección IP pública para que no los satures.

Para resolver este problema tienes varias alternativas:

`1.` La más sencilla es esperar un tiempo hasta que el servicio correspondiente (ej. Google) desbloquee tu dirección IP pública. Esto suele tardar unos minutos o, como mucho, unas pocas horas. Probablemente si repites el mismo ejercicio dentro de unos minutos, comprobarás que ya te ha desbloqueado la IP

`2.` La segunda más sencilla es reiniciar tu router. En muchas ocasiones tu proveedor de Internet te asigna una dirección IP pública de manera dinámica, por lo tanto, apagando y encendiendo el router fuerzas a que se te asigne una dirección IP pública nueva que no estará bloqueada. Ten en cuenta que esto depende de tu proveedor de Internet y que no siempre funciona (puedes comprobar cuál es tu dirección IP pública aquí: https://www.whatsmyip.org/)

`3.` Puedes utilizar algún mecanismo de anonimización que te permita conectarte a internet a través de otra región y, por lo tanto, con otra dirección IP pública. El mecanismo más común es utilizar una VPN. Existen muchos servicios de VPN gratuitos, por mi experiencia personal, te recomiendo ProtonVPN. Este servicio tiene una versión gratuita que puedes utilizar. (Para más información sobre privacidad y anonimato te recomiendo mi curso de Udemy: _Curso de Ciberseguridad y Privacidad Online: VPN, Proxy, TOR)_

`4.` Por último, puedes cambiar la fuente en la que realizar la búsqueda y utilizar otras diferentes. Por ejemplo, si te bloquea Google, puedes realizar las peticiones a bing o duckduckgo, para ello utiliza la opción `-b` de theHarvester

Estas serían las opciones más sencillas para resolver el problema. También existirían otras alternativas interesantes un poco más complejas, como, por ejemplo, utilizar un proxy público para la salida a internet o conectarte mediante la red TOR.