---
Capitulo     : Capítulo 11
Titulo       : Arrays (Arreglos) avanzados
Descripción  : En este curso veremos usos más avanzados de la estructura de datos de los array (arreglos).
---

## Repaso de los array
os array son útiles para almacenar múltiples valores, como números, cadenas e incluso otros array:

`$miArray = array(1, 2, 3);`

Acá creamos un array de tres números. Acordate de que las posiciones de los array empiezan desde 0; por lo tanto, para acceder al tercer ítem en este array, escribimos:

`$miArray[2];`

`@Instrucciones`
- Establecé `$frutas` igual a un array de tres cadenas: `'bananas'`, `'manzanas'` y `'peras'`.
- Modificá la sentencia `echo` para mostrar la fruta en el medio del array (es decir, debe mostrar, con la función `echo`, `"manzanas"`).

`@CódigoBase`
```php
<?php
  $frutas = // Tu código acá.
  echo 'Me encanta comer ' . /* Tu código. */ . ' también';
?>
```

`@Solución`
```php
<?php
  $frutas = array("bananas","manzanas","peras");
  echo 'Me encanta comer ' . $frutas[1] . ' también';
?>
```
---
## Los array asociativos
Hasta ahora estuviste accediendo a los valores de un array usando números enteros. Esto está todo bien, pero si querés ser más descriptivo con tu información, podés usar algo que se llama **array asociativo**.

Un array asociativo usa los pares (`clave => valor`). Algunos lenguajes pueden separar los array de los array asociativos pero PHP trata a ambos de la misma forma.

En el editor, vas a ver una sentencia con dos variables como array. Mirá el primer array y fijate si podés adivinar ¿a qué ítem se refieren esos valores?

Ahora mirá el array que está debajo. Este es un array asociativo. Se define como array igual que el primero pero ¿viste como especifiqué claves para cada uno de los valores?

Ambos array contienen los mismos valores, pero en el array asociativo podemos acceder al valor usando una "clave" especificada.

`@Instrucciones`
- Trata de entender que hace el código.

`@Solución`
```php
<?php
  // Este es un array que usa números enteros como índices...
  $miArray = array(2012, 'azul', 5);

  // ...y este es un array asociativo:
  $miArrayAsociativo = array('año' => 2012, 'color' => 'azul', 'puertas' => 5);

  // Este código muestra "azul"...
  echo $miArray[1];
  echo '<br />';

  // ... y esto también muestra "azul"!
  echo $miArrayAsociativo['color'];
?>
```
---
## Uso de los array como mapas
Podés imaginarte un array asociativo (también llamado **mapa**) como un array normal, pero en lugar de usar un número entero para referir el valor, se usa una clave definida.

Mientras que los índices numéricos pueden ser buenos para recorrer un array y enumerar todos los valores, ¿qué pasa si necesitamos cambiar un cierto valor de un array?

`@Instrucciones`
- Para cada array del editor, agregá el valor `"Fiat"` al final del array. Para el array asociativo, usá `"marca"` como clave. Podés agregar una clave tal como se muestra en el editor: `'clave' => valor`. _Vas a ver un error en PHP hasta que agregues los elementos faltantes del array_.

`@CódigoBase`
```php
<?php
  // Este es un array que usa números enteros como índices.
  // Agregá 'Fiat' como el último elemento del array
  $auto = array(2012, 'azul', 5);

  // Este es un array asociativo.
  // Agregar marca => 'Fiat' par clave/valor*
  $autoAsoc = array('año' => 2014, 'color' => 'azul', 'puertas' => 5);

  // Este código debe mostrar "Fiat"...
  echo $auto[3];
  echo '<br />';

  // ...y también esto.
  echo $autoAsoc['marca'];
?>
```

`@Solución`
```php
<?php
  // Este es un array que usa números enteros como índices.
  // Agregá 'Fiat' como el último elemento del array
  $auto = array(2012, 'azul', 5, 'Fiat');

  // Este es un array asociativo.
  // Agregar marca => 'Fiat' par clave/valor*
  $autoAsoc = array('año' => 2014, 'color' => 'azul', 'puertas' => 5, 'marca' => 'Fiat');

  // Este código debe mostrar "Fiat"...
  echo $auto[3];
  echo '<br />';

  // ...y también esto.
  echo $autoAsoc['marca'];
?>
```
---
## Acceder a los array asociativos
Cuando se accede a los valores desde alguno de los tipos de array, la única diferencia es si usás un número entero o una clave especificada:

```php
<?php
  echo $auto[1];
  // muestra 2012

  echo $autoAsoc['año'];
  // muestra 2012
?>
```

Este ejercicio demostrará lo útiles que son las claves en un array.

`@Instrucciones`
- Usá los array del ejercicio anterior, escribí una sentencia 'echo' para hablar de un auto (además del hecho de que es azul). Intentá usar ambos array para describir el auto. ¿Cuál te resulta más fácil?

`@CódigoBase`
```php
<?php
  // Este es un array que usa números enteros como índices.
  // Agregá 'Fiat' como el último elemento del array
  $auto = array(2012, 'azul', 5, 'Fiat');

  // Este es un array asociativo.
  // Agregar marca => 'Fiat' par clave/valor*
  $autoAsoc = array('año' => 2014, 'color' => 'azul', 'puertas' => 5, 'marca' => 'Fiat');

  // Este código debe mostrar "Fiat"...
  echo $auto[3];
  echo '<br />';

  // Agregá tu código acá.

?>
```

`@Solución`
```php
<?php
  // Este es un array que usa números enteros como índices.
  // Agregá 'Fiat' como el último elemento del array
  $auto = array(2012, 'azul', 5, 'Fiat');

  // Este es un array asociativo.
  // Agregar marca => 'Fiat' par clave/valor*
  $autoAsoc = array('año' => 2014, 'color' => 'azul', 'puertas' => 5, 'marca' => 'Fiat');

  // Este código debe mostrar "Fiat"...
  echo $auto[3];
  echo '<br />';

  // Agregá tu código acá.
  echo 'Quiero un ' . $autoAsoc['año'] . ' ' . $autoAsoc['marca'] . '. Que sea ' . $autoAsoc['color'] . ' y que tenga ' . $autoAsoc['puertas'] . ' puertas';
?>
```
---
## Iterar sobre los array asociativos
Recorrer el array asociativo es tan fácil como recorrer un ciclo en un array normal, pero obtenés el valor de una clave especificada, no de un número entero. Igual que en el ejercicio anterior.

Si solo necesitamos recorrer los valores de un array podemos usar for. Mirá el editor para ver un ejemplo en que se usa esto.

Acordate: cuando se usa un ciclo `for`. primero tenés que calcular la longitud del array.

Después mirá el ciclo `foreach` para ver cómo podemos obtener la clave y valor para cada par en el array.

`@Solución`
```php
<?php
  $comida = array('pizza', 'ensalada', 'hamburguesa');
  $ensalada = array('lechuga' => 'con', 'tomate' => 'sin', 'cebollas' => 'con');

  // Recorrer un array usando "for".
  // Primero, obtenemos el largo del array.
  $largo = count($comida);

  // Acordate, los array en PHP empiezan con el cero:
  for ($i = 0; $i < $largo; $i++) {
    echo $comida[$i] . '<br />';
  }

  echo '<br /><br />Quiero mi ensalada:<br />';

  // Recorré el array asociativo usando "foreach":
  foreach ($ensalada as $ingrediente=>$incluir) {
    echo $incluir . ' ' . $ingrediente . '<br />';
  }
?>
```
---
## Los array multidimensionales
No solo podés almacenar números enteros y cadenas en los array, también podes almacenar...¡otros array! Esto se llama un **array multidimensional**.

¿Cómo hacemos esto? Bueno, igual que con un array normal con valores separados con comas, pero vas a poner array separados con comas en su lugar, igual que el código que está en el editor.

`$maso` es un array que contiene 3 hileras y cada una es un naipe. Dentro de cada hilera está el nombre del naipe, junto con el valor. Para recuperar el naipe, primero debemos obtener la hilera para ese naipe, después debemos obtener el valor que queremos (ya sea mostrar el naipe o calcular el total del jugador).

Si accedemos a `$maso[2]`, podemos obtener la tercera hilera (acordate de que los array empiezan por 0 en PHP).

Eso nos va a devolver otro array que contenga 2 valores: el primero (0) que es una cadena que tiene el valor "7 de espada" y el segundo (1) que es un número entero con valor 7.

Si queremos la cadena "7 de espada", simplemente vamos a usar `$maso[2][0]`. ¡Fácil!


`@Solución`
```php
<?php
  $maso = array(array('2 de oro', 2), array('5 de basto', 5), array('7 de espada', 7));

  // Imaginate que la primera carta que se elige es un 7 de espada.
  // Así es como le mostraremos al usuario qué carta le tocó:
  echo 'Tenés el ' . $maso[2][0] . '!';
  // Imprime "Tenés el 7 de espada!"
?>
```
