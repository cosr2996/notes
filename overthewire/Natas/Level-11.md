# Level-10 -> Level-11

### Credentials

```
Username: natas11
Password: 1KFqoJXi6hRaPluAmk8ESDW4fSysRoIg
URL:      http://natas11.natas.labs.overthewire.org
```
### Solution
Código fuente del reto 
![[Captura de pantalla 2023-10-01 235459.png]]
Vemos las cookies y copiamos el value de data
![[Captura de pantalla 2023-10-01 235741.png]]
Vemos que el texto tiene un cifrado de URL nos damos cuenta por que termina en %3D
![[Captura de pantalla 2023-10-01 235939.png]]
copiamos el Código para usar la misma función pero con los datos que ya teníamos  y con esto conseguimos la llave que se uso para cifrar la cookie original
```php
<?php
$cookie = "MGw7JCQ5OC04PT8jOSpqdmkgJ25nbCorKCEkIzlscm5oKC4qLSgubjY=";

function xor_encrypt($in) {
    $key = json_encode(array( "showpassword"=>"no", "bgcolor"=>"#ffffff"));
    $text = $in;
    $outText = '';
  
    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
        $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}

echo xor_encrypt(base64_decode($cookie));
?>
```

```
Output:
KNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLK
```

con esto podemos usar esa llave para crear una cookie cambiando  el showpassword a yes 
```php
<?php
$defaultdata = array( "showpassword"=>"yes", "bgcolor"=>"#ffffff");

function xor_encrypt($in) {
    $key = "KNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLK";
    $text = $in;
    $outText = '';
  
    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
        $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}

echo base64_encode(xor_encrypt(json_encode($defaultdata)));
?>
```

```
Output:
MGw7JCQ5OC04PT8jOSpqdmk3LT9pYmouLC0nICQ8anZpbS4qLSguKmk2
```





### Summary

 ¿Qué es el cifrado XOR?

El cifrado XOR es un tipo de encriptación que **se basa en el uso de puertas lógicas XOR para codificar y verificar la autenticidad de los datos**. Es una operación al igual que la suma o la multiplicación, pero que funciona con bits, es decir, un sistema binario de unos (1) y ceros (0). Esta operación se utiliza en casi todos los **algoritmos criptográficos**.

 ¿Cómo funciona el cifrado XOR?: La tabla XOR

Ya que sabes qué es el cifrado XOR, hablemos del funcionamiento. Comúnmente, una puerta lógica XOR tiene dos entradas binarias, pero podría tener más. Independientemente de la cantidad de entradas, siempre habrá solo una salida, que también estará en el [lenguaje binario](https://economipedia.com/definiciones/sistema-binario.html) de unos y ceros.

Para determinar la salida que se produce el cifrado XORa partir de un conjunto de dos entradas con XOR, se produce una tabla conocida como «**tabla de la verdad**» o tabla XOR, que establece las cuatro posibles combinaciones de entradas binarias y su resultado correspondiente.

|   |   |   |
|---|---|---|
|**Entrada A**|**Entrada B**|**Salida**|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

Tabla de verdad XOR o tabla XOR

Como se puede observar en la tabla de verdad, hay **dos tipos diferentes de salida** de la función XOR. El 0 corresponde a cuando la Entrada A y la Entrada B son iguales, es decir, que contienen los valores (0,0) o (1,1). El 1 representa el caso de que las dos entradas sean diferentes, es decir, que contengan los valores (0,1) o (1,0).

Estos dos tipos de salida de XOR se conocen como:

- **Nivel alto**: 1
- **Nivel bajo**: 0

El cifrado XOR es aquel que utiliza este tipo de puertas lógicas **para encriptar y desencriptar información**. La técnica de cifrado XOR por sí sola es demasiado [vulnerable](https://keepcoding.io/blog/que-es-una-vulnerabilidad-en-ciberseguridad/) ante ataques, por lo que se suele usar en conjunto con más herramientas y funciones. Sin embargo, la función XOR se encuentra presente en casi todos los algoritmos criptográficos que se utilizan en la actualidad.

**Es vulnerable por el echo de que si tienes dos de los 3 datos consigues el tercero ejemplo**
	si tienes 3 datos A+B=C
	y conoces C y A obtienes B
	o si conoces C y B obtienes A

### FLAG
**flag** 