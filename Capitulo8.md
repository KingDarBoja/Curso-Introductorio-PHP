---
Capitulo     : Capítulo 8
Titulo       : Funciones en PHP, Parte 2
Descripción  : PHP también permite definir nuestras propias funciones. ¡Aprendamos a hacerlo!
---

## Recordando las funciones
No te repitas. Este es un principio muy simple pero fundamental en programación.

Cuando creas que necesitás reescribir un bloque de código, acordate de que probablemente puede escribirse como una función. Ya viste algunas funciones integradas de PHP, pero también podés definir la tuya.

Al usar una función en lugar de varios bloques del mismo código, podés reducir el desorden en tu documento y mantener tu código claro y ordenado.

---
## Sintaxis de una función
La estructura típica de una función es la siguiente:

```php
<?php
  function nombre(parámetros) {
    sentencia;
  }
?>
```
1. La palabra clave `function` indica que el código siguiente va a ser una función definida por el usuario.
2. `nombre` indica el nombre de la función, que no distingue mayúsculas y minúsculas. El nombre de una función puede contener números, letras, subrayados o guiones.
3. Los **argumentos**, o **parámetros**, serán la entrada opcional que usa una función para realizar cálculos.
4. Por supuesto, las sentencias van a ser el código que la función ejecuta cuando se la llama.

`@Instrucciones`
- Mirá la función `holaMundo()` que está a la derecha. No tiene parámetros, y cuando se la llama simplemente va a mostrar la cadena `"¡Hola mundo!"`.

`@Solución`
```php
<?php
  // Acá definimos la función...
  function holaMundo() {
  echo "¡Hola mundo!";
  }

  // ...y acá la llamamos
  holaMundo();
?>
```
---
## Tu primera función
Escribir nuestro nombre puede ser aburrido si no tenemos funciones que nos diviertan. En este ejercicio, vamos a escribir nuestra primera función PHP definida por el usuario ¡que sí nos va a divertir!

`@Instrucciones`
- Escribí una función que se llame `mostrarNombre`; no lleva ningún parámetro y mostrará en pantalla usando echo una cadena que contiene tu nombre. Mirá el consejo si necesitás ayuda.

`@CódigoBase`
```php
<?php
  // Escribí tu función a continuación.

?>
```

`@Solución`
```php
<?php
  // Escribí tu función a continuación.
  function mostrarNombre() {
    echo "Manuel";
  };
?>
```
---
## LLamar a tu función
Al definir nuestra función esta se hace disponible para que la usemos, pero no la podemos usar hasta que la llamamos.

Para llamar la función, simplemente escribí el nombre de la función seguido de cualquier parámetro: `nombreDeLaFunción(parámetros);`

`@Instrucciones`
- En la línea después de tu función, intentá llamarla. Deberías ver tu nombre en la pantalla en el panel de resultados.

`@CódigoBase`
```php
<?php
  // Escribí tu función a continuación.
  function mostrarNombre() {
      echo "Manuel";
  };

?>
```

`@Solución`
```php
<?php
  // Escribí tu función a continuación.
  function mostrarNombre() {
      echo "Manuel";
  };
  mostrarNombre();
?>
```
---
## La palabra clave Return
En vez de mostrar algo en la pantalla, ¿qué pasa si querés que sea el valor que la función muestre para que lo puedas usar en cualquier otra parte de tu programa? En PHP, la palabra clave `return` hace justamente eso. Nos devuelve un valor con el que podemos trabajar. La diferencia entre esto y `echo` o `print` es que en realidad no muestra el valor.

Pensá que es como una calculadora que resuelve un problema matemático que lleva varios pasos para completarlo. Se calcula el valor de cada paso pero no vemos el resultado hasta que llegamos a la respuesta final. Es decir, cada valor se devuelve con `return` y la respuesta final se muestra usando `echo` en la pantalla.

`@Instrucciones`
- Escribí una función que se llame returnNombre que devuelva tu nombre.
- Fijate que no se muestra nada en el panel de resultados. Aunque no se ve, si llamamos a nuestra función nos devuelve nuestra cadena; y eso que todavía no hicimos nada con ella.

`@Solución`
```php
<?php
  function returnNombre () {
    return "Manuel";
  }
?>
```
---
## Parámetros y argumentos
Las funciones no serían tan útiles si no fueran capaces de incorporar algo. Acá hablaremos de **parámetros** o **argumentos**. Estos son variables o entradas que usan una función para hacer cálculos.

```php
<?php
  function valorCuadrado($numero) {
    echo $numero * $numero;
  }

  $n = 6;
  valorCuadrado($n); // muestra 36
?>
```

La función `valorCuadrado` anterior toma un parámetro que se multiplica por sí mismo y después muestra en pantalla el resultado usando `echo`. Los nombres de los parámetros se utilizan internamente dentro de la función, de modo que se les puede poner un nombre que resulte útil.

También podés usar parámetros múltiples siempre que estén separados por comas.

`@Instrucciones`
- Escribí una función que se llame `saludos`.
- Debe llevar `$nombre`, como un parámetro.
- La función debe mostrar en pantalla usando echo una cadena igual a `"Saludos, " . $nombre . "!"`.
- Después llamá `saludos()` con tu nombre para probarlo.

`@Solución`
```php
<?php
  function saludos($nombre) {
    echo "Saludos, " . $nombre . "!";
  }
  saludos("Manuel");
?>
```
