---
Capitulo     : Capítulo 7
Titulo       : Funciones en PHP, Parte 1
Descripción  : Las funciones son pedazos de código reutilizables que podemos usar para hacer que nuestros programas sean más eficientes. PHP tiene más de 700 funciones incorporadas, ¡aprendamos algunas!
---

## Introducción a las funciones
Las funciones son partes de código reutilizables que podés usar durante toda la aplicación, sin tener que copiar y pegar tanto.

PHP tiene muchas funciones integradas y vamos a aprender algunas en estos ejercicios. El primer set de funciones que vamos a aprender son las funciones para el manejo de cadenas.

`strlen()` es una de las funciones de Cadena más común en PHP. Si le pasamos una cadena o variable que contiene una cadena, devuelve la cantidad de caracteres de la cadena. Un ejemplo sería:

```php
<?php
  // obtené el largo de la cadena y
  // escribilo en la pantalla
  $largo = strlen("Manuel");
  print $largo;
?>
```

`@Instrucciones`
- Usá la etiqueta index.php para escribir tu propio código. Obtené el largo de tu propio nombre, como hice con el mío, y escribilo en la pantalla.

`@CódigoBase`
```php
<?php
  // Obtené el largo de tu nombre
  // y mostralo en la pantalla.

?>
```

`@Solución`
```php
<?php
  // Obtené el largo de tu nombre
  // y mostralo en la pantalla.
  $largo = strlen("Tu Nombre");
  print $largo
?>
```
---
## Funciones de cadena I
Otra función de cadena muy común es `substr()`. Esta función te permite volver a una subcadena (parte de) de tu cadena.

Le pasás a esta función la cadena de la cual querés obtener una subcadena, el caracter de tu cadena por dónde empezar, y cuántos caracteres querés después de tu punto de partida. Un ejemplo sería:

```php
<?php
  $miNombre = "David";
  // podés manejar cadenas fácilmente con funciones integradas también.
  $parcial = substr($miNombre, 0, 3);
  print $parcial;
  // escribe "dav";
?>
```
NOTA: el segundo parámetro (el caracter de inicio) está basado en un array indexado empezando con el cero (es decir, el primer caracter de tu cadena es el número 0, no el número 1).

Otras dos funciones útiles son `strtoupper()` y `strtolower()`, que hace hacen que la cadena completa esté en MAYÚSCULAS o minúsculas. Un ejemplo de cada una:

```php
<?php
  $mayuscula = strtoupper($miNombre);
  print $mayuscula;
  // muestra "DAVID"

  $minuscula = strtolower($mayuscula);
  print $minuscula;
  // muestra "david"

  // También podes llamar estas funciones en una cadena directamente, así:  
  print strtolower("David");
  // muestra "david"
?>
```

`@Instrucciones`
- Usá la etiqueta index.php para escribir tu propio código.
Obtené una cadena parcial dentro de tu propio nombre y mostrala en la pantalla. Después probá tu nombre en mayúsculas y en minúsculas y mostralos también en la pantalla.

`@CódigoBase`
```php
<?php
  // Obtené una cadena parcial desde tu propio nombre
  // y motrala en la pantalla.

  // Poné tu nombre en mayúsculas y mostralo en la pantalla:

  // Poné tu nombre en minúsculas y mostralo en la pantalla:

?>
```

`@Solución`
```php
<?php
  // Obtené una cadena parcial desde tu propio nombre
  // y motrala en la pantalla.
  $miNombre = "Manuel";
  $parcial = substr($miNombre, 1, 4);
  print $parcial;  // Imprime anue
  // Poné tu nombre en mayúsculas y mostralo en la pantalla:
  print strtoupper("Manuel"); // Imprime: MANUEL
  // Poné tu nombre en minúsculas y mostralo en la pantalla:
  print strtolower("Manuel"); // Imprime: manuel
?>
```
---
## Funciones de cadena II
La función `strpos()` encontrá la posición de la primera ocurrencia de una subcadena en una cadena.

```php
<?php
  strpos("emilia", "e");   // 0
  strpos("emilia", "i");   // 2
  strpos("emilia", "ilia"); // 2
  strpos("emilia", "zxc"); // falso
?>
```

Los parámetros pasados a `strpos()` son el `pajar` y la `aguja`. La función trata de encontrar la `aguja` en el `pajar`.

Y devuelve el índice del primer caracter o `false` si la `aguja` no se puede encontrar.

```php
<?php
  if (strpos("david","h") === false) {
    print "Disculpá, no hay 'h' en 'david'";
  }  
  // escribir el mensaje "Disculpá"
?>
```

Usá el editor para crear tus propias combinaciones de pajar y aguja. Podés usar variables tanto para pajar como para aguja.

`@Instrucciones`
- Usá `strpos()` pasando tu nombre como pajar y una letra de tu nombre como aguja.
- Probá `strpos () == false` cuando la aguja no está en el pajar. Escribí un mensaje de error dentro de tu bloque `if`.

`@CódigoBase`
```php
<?php
  // Mostrá la posición de una letra que esté en tu nombre

  // Buscá un valor falso de una letra que no esté
  // en tu nombre y mostrá un mensaje de error

?>
```

`@Solución`
```php
<?php
  // Mostrá la posición de una letra que esté en tu nombre
  print strpos("Manuel", "u");
  // Buscá un valor falso de una letra que no esté
  // en tu nombre y mostrá un mensaje de error
  if (strpos("Manuel", "x") == false) {
      print "No se encuentra esa letra en el nombre específicado";
  }
?>
```
---
## Funciones matemáticas I
Vamos a entrar en el terreno de la aritmética. La función matemática más común que vas a usar es `round()`. Esta función redondea los números de punto flotante (números que incluyen decimales) hacia arriba o hacia abajo.

Podés usar `round()` para redondear el número a un número entero o redondear hacia abajo números de punto flotante complejos a una cantidad específica de decimales. Esto se logra pasando un segundo parámetro opcional a `round()`, diciéndole cuántos decimales querés tenga el número.

Acá hay un ejemplo:

```php
<?php
  /// Redondeá pi hacia abajo desde 3,1416...
  $redondear = round(M_PI);
  print $redondear;  // escribí 3

  // Esta vez, redondeá pi con 4 decimales
  $redondear_decimal = round(M_PI, 4);
  print $redondear_decimal; // escribe 3,1416
?>
```

NOTA: `M_PI` es una constante de PHP que es igual a pi.

`@Instrucciones`
- Usá la ventana del ejercicio para tratar de redondear algunos números vos solo. Podés usar M_PI si preferís; es mi número de punto flotante favorito.

`@CódigoBase`
```php
<?php
  // Intentá redondear un número de punto flotante a un número entero
  // y mostralo en la pantalla

  // Intentá redondear un número de punto flotante usando 3 decimales
  // y mostralo en la pantalla

?>
```

`@Solución`
```php
<?php
  // Intentá redondear un número de punto flotante a un número entero
  // y mostralo en la pantalla
  $redondear1 = round(2.14155);
  print $redondear1; // Imprime 2
  // Intentá redondear un número de punto flotante usando 3 decimales
  // y mostralo en la pantalla
  $redondear2 = round(2.14154, 3);
  print $redondear2; // Imprime 2.142
?>
```
---
## Funciones matemáticas II
Una función muy común y útil es `rand()`. Esta función devuelve un número aleatorio entre dos números. Opcionalmente, podés proveer tu número `min` y `max` como parámetros, así:

```php
<?php
// escribí un número entre 0 y 32767
print rand();

// escribí un número entre 1 y 10
print rand(1,10);
?>
```

`@Instrucciones`
- Usá el editor para escribir un número aleatorio.
- Creá una nueva variable `$nombre` y almacená tu nombre en la variable.
- Después escribí un caracter al azar de tu nombre. Usá lo que sabés de `strlen(cadena)`, `rand(min, max)`, y `substr(cadena, inicio, tamaño)` para hacer esto. Recuerda que el argumento `tamaño` hace referencia a la cantidad de caracteres a devolver.

_Consejo útil:_ Acordate de que `substr()` trata los caracteres en una cadena como un array indexado empezando con el cero (la primera letra está en la posición cero). Esto significa que el último caracter en la cadena estará en la posición `largo - 1`.

`@CódigoBase`
```php
<?php
  // Usá rand() para mostrar un número al azar en la pantalla

  // Usá lo que sabés de strlen(), substr(),y rand() para
  // mostrar un caracter de tu nombre al azar, en la pantalla.

?>
```

`@Solución`
```php
<?php
  // Usá rand() para mostrar un número al azar en la pantalla
  print rand();
  // Usá lo que sabés de strlen(), substr(),y rand() para
  // mostrar un caracter de tu nombre al azar, en la pantalla.
  $miNombre = "Manuel";
  $largo = strlen($miNombre);
  $numran = rand(0, $largo - 1);
  print substr($miNombre, $numran, 1);
?>
```
---
## Funciones de arreglos (array) I
Los array se usan mucho en programación. De hecho, el `array()` es en realidad una función. Muy bien, vos ya usaste una función array.

Aparte de la función `array()`, se puede decir que `array_push()` es la función más común y útil para el manejo de los array.

`array_push()` toma dos argumentos: un array y un elemento para agregar al final de ese array. Acá hay un ejemplo:

```php
<?php
$bandas_fav = array();
array_push($bandas_fav, "Sumo");
array_push($bandas_fav, "Divididos");
array_push($bandas_fav, "Babasónicos");
array_push($bandas_fav, "Tan Biónica");
array_push($bandas_fav, "Soda Stereo");
?>
```

Otra función array genial es `count()`. Si se pasa un array a `count()` se recibe la cantidad de elementos que hay en el array. Así:

```php
<?php
  print count($bandas_fav); // escribe 5
?>
```

`@Instrucciones`
- Usá el editor para crear un array y usá array_push() para agregarle por lo menos 5 elementos. Una vez que agregaste todos los elementos, mostrá con print la cantidad de elementos que tiene tu array.

`@CódigoBase`
```php
<?php
  // Creá un array, insertá 5 elementos sobre ese array, después  
  // mostrá en pantalla la cantidad de elementos en tu array.

?>
```

`@Solución`
```php
<?php
  // Creá un array, insertá 5 elementos sobre ese array, después  
  // mostrá en pantalla la cantidad de elementos en tu array.
  $colores = array();
  array_push($colores, "azul", "rojo", "verde", "amarillo", "naranja");
  print count($colores); // Mostrará 5 como resultado.
?>
```
---
## Funciones de array II
Otra función común para hacer con los array es ordenarlos. ¡Qué conveniente! PHP tiene una función `sort()` justo para eso.

```php
<?php
  $array = array(5, 3, 7, 1);
  sort($array);
  print join(", ", $array);
  // muestra "1, 3, 5, 7"
?>
```

PHP también tiene la función opuesta: `rsort()`.

```php
<?php
  $array = array(5, 3, 7 ,1);
  rsort($array);
  print join(":", $array);
  // muestra "7:5:3:1"
?>
```

Por último, usamos `join (junta, array)` para mostrar fácilmente las representaciones de los array ordenados en este ejercicio.

Para este ejercicio usamos una coma (`,`) para unirlos.

`@Instrucciones`
- Usá `array()` para crear un array con varios elementos y almacenarlo en `$el_array`.
- Después, `sort()` el array.
- Después, mostrá `join(","$el_array)`.
- Luego `rsort()` el array.
- Finalmente, `join()` y print el array devuelto a la pantalla.

`@CódigoBase`
```php
<?php
  // Creá un array que tenga varios elementos,
  // después ordenalo y mostrá en pantalla los elementos unidos.

  // Invertí la forma en que está ordenado tu array y mostrá en pantalla los elementos unidos.

?>
```

`@Solución`
```php
<?php
  // Creá un array que tenga varios elementos,
  // después ordenalo y mostrá en pantalla los elementos unidos.
  $el_array = array("PHP","Python","Perl","Ruby","Clojure");
  sort($el_array);
  print join(", ", $el_array); // Imprime Clojure, PHP, Perl, Python, Ruby
  // Invertí la forma en que está ordenado tu array y mostrá en pantalla los elementos unidos.
  $el_array = array("PHP","Python","Perl","Ruby","Clojure");
  rsort($el_array);
  print join(", ", $el_array); // Imprime Ruby, Python, Perl, PHP, Clojure
?>
```
