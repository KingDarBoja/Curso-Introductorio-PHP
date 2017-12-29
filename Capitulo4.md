---
Capitulo     : Capítulo 4
Titulo       : Arrays (o Arreglos)
Descripción  : Los array te permiten almacenar listas de información en una única variable.
---

## ¿Qué es un array?
Un array es una lista de ítems, como una lista de compras. Te permite almacenar más de un ítem en una sola variable.

Pensalo de esta forma: Cuando hacés la lista del supermercado, podés usar un pedazo de papel para cada ítem que necesites comprar (una variable). Sin embargo esto es tonto e innecesario ¿te podés imaginar lo difícil que sería llevar todos esos papeles con vos? Por eso usás un solo papel para todos tus ítems. Este pedazo de papel es tu array.
¿Podés ver en el editor el pedazo de texto que empieza con `$array =?` Ese es tu array. No te preocupes por todos los detalles todavía, te los vamos a explicar después. Por ahora, fijate si podés entender lo que está pasando.

`@Solución`
```php
<?php
  $array = array("Huevo", "Tomate", "Chauchas");
?>    
```
---
## Sintaxis de array
¿Algo te pareció conocido al principio de tu array? ¡Claro! porque empieza de la misma manera que una variable, con el signo `$`, y después un nombre, seguido del signo `=`.
Sin embargo, acá es cuando las cosas empiezan a ser diferentes. Cuando creamos un array, tenemos que usar `array()`. Esto básicamente le dice a PHP que `$array` es un array y no otra cosa, como por ejemplo una de las conocidas variables comunes.
A esta altura, estoy seguro de que te diste cuenta del texto que está dentro del `(` y `)`. Estos son los ítems del array. Entonces, en este momento, tu array tiene los ítems, "huevos", "tomates" y "chauchas". Podés agregar cualquier tipo de información en un _array_, y se hace casi de la misma manera que cuando se crean variables. Usá `""` cuando agregás cadenas, y solo ingresá el número cuando agregues números enteros.
Sin embargo, siempre te tenés que acordar de que cada ítem en un array tiene que estar separado por una coma: ,.

`@Instrucciones`
- Agregá dos ítems más en tu _array_, `"Papas"` y `"Salchichas"`.

`@CódigoBase`
```php
<?php
  // Agregá los elementos del array después de
  // "Chauchas" y antes del último ")"
  $array = array("Huevo", "Tomate", "Chauchas" );
?>
```

`@Solución`
```php
<?php
  // Agregá los elementos del array después de
  // "Chauchas" y antes del último ")"
  $array = array("Huevo", "Tomate", "Chauchas", "Papas", "Salchichas" );        
?>
```
---
## Creá tu primer *array*
¡Buen trabajo! Ahora, hagamos un *array* desde cero.

`@Instrucciones`
- Creá un array que se llame `$amigos` y poné los nombres de tres amigos tuyos. Cada nombre de un amigo es una cadena así que asegurate de escribirlos entre comillas.

`@Solución`
```php
<?php
  $amigos = array("Jhon", "Susan", "Mark");
?>
```

---
## Acceso mediante Offset con [ ]

Cada ítem en un array está numerado comenzando por el 0. Por ejemplo, cuando creamos un array:
```php
<?php
  $miArray = array("do", "re", "mi");
?>
```
Cada ítem está numerado comenzando desde el 0, así:

```
+------+------+------+
| "do" | "re" | "mi" |
+------+------+------+
   0      1      2
```

El ítem `"do"` está en la posición 0, el ítem `"re"` está en la posición 1, y etc.

Por lo tanto, podemos acceder a un ítem en particular del _array_ utilizando su posición, así:

```php
<?php
$miArray = array("do", "re", "mi");
echo $miArray[0]
// Salida: "do"
?>
```

1. Primero creamos un array que se llame `$miArray`.
2. Después usamos echo para visualizar en pantalla el primer ítem en `$miArray`. Dado de los ítems están numerados empezando desde 0, `"do"` está en la posición 0.

`@Instrucciones`
- Usá `echo` para ver en pantalla el tercer ítem en `$decenas`. Acordate de que los ítems están numerados empezando desde 0.

`@CódigoBase`
```php
<?php
  $decenas = array(10, 20, 30, 40, 50);
?>
```

`@Solución`
```php
<?php
  $decenas = array(10, 20, 30, 40, 50);
  echo $decenas[2];
?>
```

---
## Acceso mediante Offset con { }

PHP es un lenguaje muy flexible. Cuando se accede a los array mediante offset, podés usar dos tipos diferentes de sintaxis: los corchetes `[]`, sintaxis que ya vimos, o podés usar las llaves (`{}`). Las llaves se usan de la misma manera que los corchetes:

```php
<?php
 $miArray = array("do", "re", "mi");
 print $miArray{2};
 // Imprime "mi";
?>
```
Ambas formas son equivalentes, y usar una u otra depende totalmente de vos.

`@Instrucciones`
- Actualizá tu código anterior para usar la sintaxis {} en lugar de [].

`@CódigoBase`
```php
<?php
  $decenas = array(10, 20, 30, 40, 50);
  echo $decenas[2];
?>
```

`@Solución`
```php
<?php
  $decenas = array(10, 20, 30, 40, 50);
  echo $decenas{2};
?>
```

---
## Modificar elementos del arreglo (array)

Un ítem en un arreglo puede cambiarse especificando su posición y proporcionando un nuevo valor; así:

```php
<?php
$miArray = array("rojo", "azul", "amarillo");

echo $miArray[1];
// muestra en pantalla "azul"

$miArray[1] = "verde";

echo $miArray[1];
// muestra en pantalla "verde"
?>
```

1. Primero creamos un nuevo array $miArray con una lista de colores.

2. Después visualizamos en pantalla el ítem de la posición 1. Dado que los ítems están numerados empezando desde 0, "azul" está en la posición 1.

3. Después cambiamos el ítem de la posición 1por "verde".

4. Ahora si visualizamos el ítem de la posición 1, obtenemos "verde".

`@Instrucciones`
- Hay un arreglo llamado $lenguajes. Cambiá un ítem en el array `$lenguajes`. Podés elegir cualquiera.
- Después usá echo para visualizar `$lenguajes`.

`@CódigoBase`
```php
<?php
  $lenguajes = array("HTML/CSS",
  "JavaScript", "PHP", "Python", "Ruby");

  // Escribí el código para modificar
  // el arreglo $lenguajes.

?>
```

`@Solución`
```php
<?php
  $lenguajes = array("HTML/CSS",
  "JavaScript", "PHP", "Python", "Ruby");

  // Escribí el código para modificar
  // el arreglo $lenguajes.
  $lenguajes[0] = "Clojure";
  echo $lenguajes[0];
?>
```

---
## Borrar elementos del array
Finalmente, podés eliminar los elementos usando `unset`:

```php
<?php
  $miArray = array("rojo", "azul", "amarillo");
  unset($array[2]);
?>
```

Hasta podés eliminar todo el array:

```php
<?php
  unset($array);
?>
```

`@Instrucciones`
- Eliminá `"Python"` del array `$lenguajes` usando `unset()`.

`@CódigoBase`
```php
<?php
  $lenguajes = array("HTML/CSS",
  "JavaScript", "PHP", "Python", "Ruby");
  // Escribí el código para eliminar Python acá.

  // Escribí el código sobre esta línea. No
  // te preocupes por el código de abajo todavía. Lo estamos
  // usando para mostrarte el nuevo array a vos.
  foreach($lenguajes as $leng) {
    print "<p>$leng</p>";   
  }
?>
```

`@Solución`
```php
<?php
  $lenguajes = array("HTML/CSS",
  "JavaScript", "PHP", "Python", "Ruby");
  // Escribí el código para eliminar Python acá.
  unset($lenguajes[3]);
  // Escribí el código sobre esta línea. No
  // te preocupes por el código de abajo todavía. Lo estamos
  // usando para mostrarte el nuevo array a vos.
  foreach($lenguajes as $leng) {
    print "<p>$leng</p>";   
  }
?>
```
