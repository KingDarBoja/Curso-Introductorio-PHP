---
Capitulo     : Capítulo 5
Titulo       : Ciclos For
Descripción  : Los Array son geniales, pero iterar sobre ellos para usar cada elemento en el array es todavía mejor. ¡Podemos hacer eso con los ciclos!
---

## ¿Qué es un ciclo?
Programar es difícil y se hace más difícil cuando tenés que hacer las mismas cosas en forma repetida. Si queremos mostrar usando `echo` una lista de años bisiestos (http://en.wikipedia.org/wiki/Leap_year) en el editor vas a pensar que tenemos que escribir:

```php
<?php
    echo 2004;
    echo 2008;
    echo 2012;
    // etc.
?>
```
Pero hay una forma mejor.

Un *ciclo* es un bit de código muy útil, que repite una serie de instrucciones. Por ejemplo, en vez de escribir `echo` muchas veces como hicimos antes, simplemente podemos usar el código en el editor que está a la derecha.

`@Instrucciones`
- Mirá el ciclo `for` que se está en el editor. ¿Ves cómo muestra mediante `echo` el valor para `$bisiesto`, le agrega cuatro y después se repite?

`@Solución`
```php
<?php
  for ($bisiesto = 2004; $bisiesto < 2050; $bisiesto = $bisiesto + 4) {
    echo "<p>$bisiesto</p>";
  }
?>
```

---
## Sintaxis del ciclo "For"
Qué bueno, ¿no? Revisemos la sintaxis despacio, paso a paso. Acá te damos un ejemplo que muestra en pantalla usando `echo` los números del 0 al 9:

```php
<?php
  for ($i = 0; $i < 10; $i++) {
      echo $i;
  }
// muestra en pantalla 0123456789
?>
```
Se descompone así:

1. Un ciclo `for` empieza con la palabra clave `for`. Esto le dice a PHP que se prepare para hacer un ciclo.

2. Después viene el conjunto de paréntesis (`()`). Dentro de los paréntesis, le decimos a PHP tres cosas, separadas por punto y coma (`;`): dónde empezar el ciclo; dónde terminar el ciclo; y qué hacer para llegar a la próxima iteración del ciclo (por ejemplo, contar de a uno).

3. Después de la parte entre paréntesis, la parte en llaves (`{}`) le dice a PHP qué código ejecutar para cada iteración del ciclo.

  Entonces, el ejemplo anterior dice: "Empezá a recorrer con `$i` en 0, detené el ciclo antes de que `$i` llegue a 10, contá de a 1 por vez y, para cada iteración, mostrá usando echo el valor actual de `$i`".

  (`$i++` es la forma abreviada de `$i = $i + 1`. Vas a ver esto muchas veces.)

`@Instrucciones`
- Completá el ciclo for en el editor reemplazando el ___ con la sintaxis de ciclo correcta.

`@CódigoBase`
```php
<?php
  // Muestra usando echo los primeros cinco números pares
  ___ ($i = 2; $i < 11; $i = $i + 2) ___
    echo $i;
  ___
?>
```

`@Solución`
```php
<?php
  // Muestra usando echo los primeros cinco números pares
  for ($i = 2; $i < 11; $i = $i + 2) {
    echo $i;
  }
?>
```
---
## Cómo escribir tu primer ciclo "For"
¡Buen trabajo! Ahora juntemos nuestro primer ciclo `for` desde el principio hasta el final.

Un ciclo `for` que muestra los números del 1 al 10 se ve así:

```php
<?php
  for ($i = 0; $i < 11; $i++) {
      echo $i;
  }
?>
```

Este ciclo `for` cuenta de a 1 cada vez, hasta 10.

Podés cambiar la tercera parte del ciclo `for` para que cuente de a 5, de esta forma:

```php
<?php
  for ($i = 0; $i < 11; $i = $i + 5) {
      echo $i;
  }
?>
```

En vez de $i++, tenemos $i = i + 5 para contar de a 5, hasta llegar a 10.

:warning: **Nota:** Tené mucho cuidado cuando construís el ciclo. Asegurate especialmente de que el ciclo esté escrito con las condiciones que le permitirán finalizar.

Por ejemplo, si escribís `$i + 1` en lugar de `$i++` o `$i = $i + 1` para el tercer bit del ciclo for, la variable $i nunca se va a actualizar, y tu ciclo va a continuar para siempre. Esto se llama **ciclo infinito** y tendrás que recargar la página. ¡Cuidado!

`@Instrucciones`
- Escribí un ciclo `for` que cuente de a 10 hasta llegar a 100 (es decir 10, 20, 30...) Dentro del ciclo for, mostrá en pantalla el valor actual de $i utilizando `echo`, igual que en los ejemplos anteriores.

`@CódigoBase`
```php
<?php
  // ¡Escribí el ciclo for a continuación!

?>
```

`@Solución`
```php
<?php
  // ¡Escribí el ciclo for a continuación!
  for ($i = 10; $i < 101; $i = $i + 10) {
      echo $i;
  }
?>
```
---
## Cuándo usar "For"
¡Buenísimo! Los ciclos `for` son muy útiles para ejecutar el mismo código una y otra vez, especialmente cuando sabés con anterioridad cuantas veces necesitás hacer el ciclo. (Hay otros tipos de ciclos, como `while` y `do/while` que podemos usar cuando no sabemos con anterioridad cuántas veces vamos a necesitar hacer el ciclo, pero vamos a ver esos ciclos en otra lección.)

También hay otro tipo de ciclo que se llama `foreach` que usamos para actualizar o mostrar cada elemento en una lista —por ejemplo, un array. Veamos el ciclo `foreach`.

---
## Ciclos + arrays = ForEach
El ciclo `foreach` se usa para iterar sobre cada elemento de un objeto, lo que lo hace perfecto para usar con los array.

Podés imaginarte el ciclo `foreach` como si saltaras de un elemento a otro del array y ejecutaras el código entre `{}` para cada uno de esos elementos.

`@Instrucciones`
- Mirá el código que está en el editor. ¿Ves cómo la variable `$lenguaje` toma el valor de cada elemento en `$lenguajes`, uno a uno, y después muestra ese elemento en la página usando `echo`?

`@Solución`
```php
<?php
  $lenguajes = array("JavaScript", "HTML/CSS", "PHP", "Python", "Ruby");
  foreach ($lenguajes as $lenguaje) {
      echo "<li>$lenguaje</li>";
  }
  unset($lenguajes);
?>
```
---
## Practicar con ForEach
Veamos la sintaxis de `foreach` paso a paso. Primero hay un ciclo `foreach` que itera sobre un array y muestra cada elemento que encuentra:

```php
<?php
  $numeros = array(1, 2, 3);
  foreach($numeros as $item) {
      echo $item;
  }
?>
```

Primero creamos nuestro array usando la sintaxis `array()` que aprendimos en el capítulo pasado.

Después, usamos la palabra clave `foreach` para empezar el ciclo, seguido de paréntesis. (Esto es muy similar a lo que hicimos con los ciclos `for`.)

Entre los paréntesis, usamos la sintaxis `$numeros as $item` para decirle a PHP: "Para cada cosa en `$numeros`, asigná esa cosa temporalmente a la variable `$item`". (No tenemos que usar el nombre `$item`, como en los ciclos `for`; podemos ponerle cualquier nombre a nuestra variable temporal).

Finalmente, ponemos el código que queremos ejecutar entre las llaves. En este caso, solo mostramos usando echo cada elemento a la vez .

`@Instrucciones`
- Completá el ciclo foreach en el editor reemplazando el ___ con la sintaxis de ciclo correcta.

`@CódigoBase`
```php
<?php
  $oracion = array("Estoy ", "aprendiendo ", "PHP!");
  ___ ($oracion as $palabra)  ___
    echo $palabra;
  ___
?>
```

`@Solución`
```php
<?php
  $oracion = array("Estoy ", "aprendiendo ", "PHP!");      
  foreach ($oracion as $palabra) {
    echo $palabra;
  }
?>
```
---
## Creando mi primer ciclo "Foreach"
¡Muy bien! Ahora veamos cómo escribís un ciclo `foreach` vos solo.

`@Instrucciones`
- En el código hay un array que se llama `$jugadaDeFutbol`. Escribí un ciclo `foreach` que itere sobre el array y use echo sobre cada elemento para mostrarlo en la página.

`@CódigoBase`
```php
<?php
  $jugadaDeFutbol = array("primer pase... ", "segundo pase... ", "centro al área... ", "cabezaaa... ");

  // Escribí tu ciclo foreach debajo de esta línea


  // Escribí tu ciclo foreach encima de esta línea
  echo "¡Gooooool!";
?>
```

`@Solución`
```php
<?php
  $jugadaDeFutbol = array("primer pase... ", "segundo pase... ", "centro al área... ", "cabezaaa... ");

  // Escribí tu ciclo foreach debajo de esta línea
  foreach ($jugadaDeFutbol as $jg) {
    echo $jg;
  }
  // Escribí tu ciclo foreach encima de esta línea
  echo "¡Gooooool!";
?>
```
