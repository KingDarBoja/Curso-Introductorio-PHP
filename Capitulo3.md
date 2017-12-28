---
Capitulo     : Capítulo 3
Titulo       : Control de Flujo Switch
Descripción  : La sentencia switch te deja realizar operaciones de control de flujo más complejas sin usar cadenas interminables de  'if' y 'else'.
---

## Miremos lo que hicimos
Vamos a recordar lo que hicimos en el curso anterior sobre los condicionales `if` / `else`.

`@Instrucciones`
- Escribí una sentencia `if`/ `elseif`/ `else` dentro del editor y hacé que muestre en pantalla lo que quieras.

`@CódigoBase`
```php
<?php
  if (condición) {

  } elseif (condición) {

  } else {

  }
?>
```

`@Solución`
```php
<?php
// Cualquier cosa es válida para probar
  $dinero = 90;
  if ($dinero > 100) {
    echo "Eres multimillonario.";
  } elseif ($dinero == 100) {
    echo "Eres millonario.";
  } else {
    echo "Eres rico.";
  }
?>
```

---
## Vamos a meternos en las sentencias Switch
En el editor ves una simple sentencia switch. Una sentencia switch es útil cuando tenés una serie de sentencias `if`/`elseif`/`else` con múltiples expresiones que dependen del mismo valor. Las sentencias switch también dan eficiencia y fluidez. Las sentencias switch funcionan como las sentencias `if`; si una condición es verdadera, ejecuta un bloque de código.

`@Instrucciones`
- Intentá descubrir cuál de estos bloques `case` se ejecuta.

`@Solución`
```php
<?php
  switch (2) {
    case 0:
      echo 'El valor es 0';
      break;
    case 1:
      echo 'El valor es 1';
      break;
    // Se ejecuta el caso número 2.
    case 2:
      echo 'El valor es 2';
      break;
    default:
      echo "El valor no es ni 0, 1 ni 2";
  }
?>
```

---
## Sintaxis de Switch
Una sentencia `switch` es similar a una sentencia `if`/ `elseif` / `else` en que podés controlar muchas condiciones. Así se ve:

```php
<?php
$miNum = 2;

switch ($miNum) {
    case 1:
        echo "1";
        break;
    case 2:
        echo "2";
        break;
    case 3:
        echo "3";
        break;
    default:
        echo "Ninguna de las anteriores";
}
?>
```

1. Una sentencia `switch` se forma con la palabra clave `switch`, una variable para controlar, y un par de llaves `{ }`. Acá controlamos el valor de `$miNum`.

2. Hay un bloque `case` (caso) para cada comparación. Por ejemplo, el código de abajo controla si `$miNum` es igual a `1`. Si lo es, se muestra usando `echo` como "1", y usa `break` para salir de la sentencia `switch`.
```php
<?php
    case 1:
      echo "1";
      break;
?>
```
3. De lo contrario, se ejecuta el siguiente bloque `case`.

4. Si todos los `case` son falsos, se ejecuta el case `default` predeterminado.

`@Instrucciones`
- Completá los espacios `__` con el código correcto. Controlá los ejemplos anteriores.
- Agregá el case `default`.

`@CódigoBase`
```php
<?php
$fruta = "Manzana";

switch ($fruta) {
    __ 'Manzana':
        echo "Rica.";
        __;
}

?>
```

`@Solución`
```php
<?php
$fruta = "Manzana";

switch ($fruta) {
    case 'Manzana':
        echo "Rica.";
        break;
    default:
        echo "Ninguna de las anteriores";
}

?>
```

---
## Casos Múltiples
A veces querés hacer múltiples expresiones con el mismo resultado. Considerá la siguiente sentencia `if`:
```php
<?php
if ($i == 1 ||
    $i == 2 ||
    $i == 3) {
 echo '$i está en algún punto entre 1 y 3.';
}
?>
```
Con una sentencia `switch` podés hacer esto agregando varios `case` uno atrás del otro, sin interrupción. Esto se llama **falling through**. El código siguiente funciona exactamente igual que la sentencia `if`:

```php
<?php
case 1:
case 2:
case 3:
    echo '$i está en algún punto entre  1 y 3.';
    break;
?>
```

`@Instrucciones`
- Reemplazá los dos guiones bajos para hacer que el switch también controle 3 y 4.

`@CódigoBase`
```php
<?php
$i = 5;

switch ($i) {
    case 0:
        echo '$i es 0.';
        break;
    case 1:
    case 2:
    case _:
    case _:
    case 5:
        echo '$i está en algún lado entre  1 y 5.';
        break;
    case 6:
    case 7:
        echo '$i es 6 o 7.';
        break;
    default:
        echo '$i es igual o mayor que 8';
}
?>
```

`@Solución`
```php
<?php
$i = 5;

switch ($i) {
    case 0:
        echo '$i es 0.';
        break;
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        echo '$i está en algún lado entre  1 y 5.';
        break;
    case 6:
    case 7:
        echo '$i es 6 o 7.';
        break;
    default:
        echo '$i es igual o mayor que 8';
}
?>
```

---
## Usar "Endswitch".
Tenés dos formas de crear un switch. Primero, la forma en que hicimos los ejercicios anteriores:

```php
<?php
switch ($i) {

}
?>
```
Pero también podemos hacer esto:

```php
<?php
switch ($i):

endswitch;
?>
```
Esto se llama **sintaxis alternativa** o _"syntactic sugar"_.

No hay diferencia cuando se usa la sintaxis de llave (primer ejemplo) o la sintaxis alternativa (segundo ejemplo); solo da fluidez, por lo tanto se usa cuando se mezclan códigos HTML y PHP en el mismo archivo.

`@Instrucciones`
- En el editor tenés el **código del ejercicio anterior**. Hacé que el código use la **sintaxis alternativa** en lugar de la **sintaxis de llave**.

`@Solución`
```php
<?php
$i = 5;

switch ($i):
    case 0:
        echo '$i es 0.';
        break;
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        echo '$i está en algún lado entre  1 y 5.';
        break;
    case 6:
    case 7:
        echo '$i es 6 o 7.';
        break;
    default:
        echo '$i es igual o mayor que 8';
endswitch;
?>
```
