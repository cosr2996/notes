#### Description

What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

### Solution
la primera bandera es una p
la segunda una i 
la tercera una c

Sabemos esto porque la sugerencia proporcionada indica que la bandera tiene el formato PICOCTF{}, por lo tanto, las primeras 7 banderas representan P I C O C T F respectivamente.

Esto es muy interesante pero conociendo estas 7 banderas no es suficiente para conseguir la bandera.

Después de investigar un poco , pude descubrir que estos símbolos son, de hecho, banderas de señales marítimas internacionales, consulte [Wikipedia](https://en.wikipedia.org/wiki/International_maritime_signal_flags).

Sabiendo esto, el reto ahora es sencillo, solo es cuestión de hacer coincidir la bandera con la letra asociada.
![[flag.png]]


### Flag
PICOCTF{F1AG5AND5TUFF}