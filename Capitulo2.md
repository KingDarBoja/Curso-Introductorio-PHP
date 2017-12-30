---
Capitulo     : Capítulo 2
Titulo       : Condicionales - Control de Flujo If/Else
Descripción  : El Control de flujo es un programa que decide realizar una acción en lugar de otra. EN PHP podemos usar 'if' y 'else' para hacer esto.
---

## Comparaciones
Hasta ahora vimos:

- **cadenas** (es decir, `"¡los perros ladran!"`)
- **numeros** (es decir, `4`, `10`)
Ahora aprendamos sobre operadores de comparación.

Lista de operadores de comparación:

- `>` Mayor que
- `<` Menor que
- `<=` Menor que o igual a
- `>=` Mayor que o igual a
- `==` Igual a
- `!=` Distinto de

`@Instrucciones`
- Usá un operador de comparación para comparar dos números y que el resultado sea verdadero. Asegurate de terminar tu línea de PHP con un punto y coma.

`@Solución`
```php
<?php
  // Cualquier comparación aquí
  6 < 7;
?>
```

---
## Sentencias If
¡Buen trabajo con las comparaciones! Ahora vamos a ver cómo podemos usar las comparaciones para preguntar por "sí" o por "no".

Por ejemplo, si queremos escribir un programa que pregunte si tu nombre tiene más de 7 letras, si la respuesta es sí, podemos responder con "¡Tenés un nombre largo! Podemos hacer esto con una sentencia `if`:

```php
<?php
  $edad = 17;

  if( $edad > 16 ) {
    echo "¡Podés manejar!";
  }
?>
```

Una sentencia if se forma con la palabra clave `if`, una condición como la que vimos antes, y un par de llaves `{ }`. Si la respuesta a la condición es sí, se ejecutará el código que está dentro de las llaves.

`@Instrucciones`
- Ajustá `$items` igual a un número mayor que 5. Asegurate de poner un punto y coma al final de la línea.
- Editá la condición para que tu programa muestre en pantalla `Conseguis 10% de descuento`.

`@CódigoBase`
```php
<?php
  $items =
  // Si la condición es verdadera, se ejecutará el código que está entre las llaves.
  if($items < 5) {
    echo "Conseguis 10% de descuento";
  }
?>
```

`@Solución`
```php
<?php
  $items = 10;
  // Si la condición es verdadera, se ejecutará el código que está entre las llaves.
  if($items > 5) {
    echo "Conseguis 10% de descuento";
  }
?>
```

---
## Agregar Else
¡Muy bien! Usamos una sentencia `if` para hacer algo si la respuesta a la condición es sí o `true` (verdadera), como decimos en PHP.

Además de hacer algo si la condición es `true`, podemes hacer otra cosa si la condición es `false`(falsa). Podemos hacerlo usando una sentencia `if` /`else`:

```php
<?php
  $nombre = "Pedro";
  if ($nombre == "Juan") {
    print "¡Te conozco!";
  }
  else {
    print "¿Quién sos?";
  }
?>
```

Igual que antes, si la condición es `true`, solo el código dentro del primer par de llaves se va a ejecutar. De lo contrario, si la condición es `false`, solo se ejecutará el código que está dentro del segundo par de llaves luego de la palabra clave `else`.

En el ejemplo anterior la condición `$nombre == "Juan"` se evalúa como `false` ya que `$nombre` es `Pedro`. Dado que la condición es `false`, solo el código que está dentro de la llave después de la palabra clave `else` se ejecuta y escribe `¿Quién sos?`.

`@Instrucciones`
- Debajo de tu sentencia `if`, escribí una sentencia else para captar a las personas que solo compran 5 ítems o menos. En su caso, usá `echo` para mostrar `"¡Conseguís un 5% de descuento!"`.

`@CódigoBase`
```php
<?php
  $items = 3;

  if($items > 5) {
    echo "¡Conseguís 10% de descuento!";
  }


?>
```

`@Solución`
```php
<?php
  $items = 3;

  if($items > 5) {
    echo "¡Conseguís 10% de descuento!";
  }
  else {
      echo "¡Conseguís un 5% de descuento!";
  }
?>
```

---
## ¡Ahora todo junto!
¡Buen trabajo! Ahora practiquemos usar las sentencias `if` / `else`.

`@Instrucciones`
- Escribí una sentencia `if` / `else` como hicimos en el último ejercicio. Así se verá el código:

```php
<?php
  if (esta condición es verdadera) {
    // hacé este código
  }
  else {
    // mejor hacé este código
  }
?>
```

- Si tu condición es `true`, tu código debe mostrar usando `echo "La condición es verdadera"`.

- De lo contrario (`else`) cuando es falsa, tu código debe mostrar usando `echo "La condición es falsa"`.

- Asegurate de que tu condición evalúe a `false`, para que tu programa muestre `"La condición es falsa"`.

`@CódigoBase`
```php
<?php
  // Escribí tu sentencia if/elseif/else acá.

?>
```

`@Solución`
```php
<?php
  if(10 < 3) {
      echo "La condición es verdadera";
  }
  else {
      echo "La condición es falsa";
  }
?>
```
