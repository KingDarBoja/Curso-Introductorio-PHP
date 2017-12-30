---
Capitulo     : Capítulo 6
Titulo       : Ciclos While y Do-While
Descripción  : A veces no sabemos de antemano cuántos ciclos vamos a necesitar.  En esos casos, podemos usar una estructura diferente, un ciclo while.
---

## Recorrer el ciclo
Un ciclo es una estructura que le dice a una computadora que ejecute un conjunto de sentencias muchas veces. Si tenés un proceso que querés que se repita cientos de veces, vale la pena poner un ciclo, así no necesitas escribir cientos de líneas de códigos.

Si estás haciendo estos cursos en orden, ya habrás visto cómo un ciclo `for` puede permitir una cantidad determinada de iteraciones de ciclo. ¿Pero qué pasa en una situación en la que (debido quizás a la aleatoriedad) no sabés cuántas veces debe repetirse el ciclo? En ese caso, podés usar un ciclo `while`.

Se ejecutará el ciclo `while` siempre que una cierta condición sea verdadera. Por ejemplo, el ciclo que ves en el editor simulará el lanzamiento de una moneda siempre que la cantidad de caras consecutivas sea menor que 3.

`@Instrucciones`
- Mirá el código y fijate si entendés como va a funcionar.

`@Solución`
```php
<?php
$conteoDeCaras = 0;
$conteoDeLanzamientos = 0;
while ($conteoDeCaras < 3) {
  $lanzamientos = rand(0,1);
  $conteoDeLanzamientos ++;
  if ($lanzamientos){
    $conteoDeCaras ++;
    echo "<div class=\"coin\">C</div>";
  }
  else {
    $conteoDeCaras = 0;
    echo "<div class=\"coin\">S</div>";
  }
}
echo "<p>Se hicieron {$conteoDeLanzamientos} lanzamientos.</p>";
?>
```
---
## Sintaxis del bucle While
En el último ejercicio, ¿viste cómo se puede usar un ciclo `while` para repetir un conjunto de comandos una cantidad no determinada de veces? Ese ciclo usa la siguiente sintaxis:

```php
<?php
  while(cond) {
    // las sentencias de ciclo van acá
  }
?>
```

donde las sentencias van dentro de las llaves y se ejecutan `{` y `}` siempre que la condición cond se evalúe como verdadera. En el último ejercicio, `cond` era la condición de que la cantidad de caras consecutivas fuese menor de 3: `$ConteoDeCaras < 3`.

Es importante cuando se escribe un ciclo asegurarse de que el ciclo finalizará en algún punto. El ciclo
```php
<?php
while(2 > 1){
   // Code
}
?>
```
nunca va a terminar y es un ejemplo de un ciclo infinito. Evitá los ciclos infinitos como la peste. Es la razón por la cual necesitamos incluir `$loopCond = false` dentro de los paréntesis. Si enviás un ciclo infinito en uno de los ejercicios, necesitás recargar la página para detenerlo.

`@Instrucciones`
- Agregá una condición dentro del paréntesis `( )` que haga que se ejecute el ciclo while siempre que `$loopCond ==true`.
- Dentro de las llaves, usá `echo` para mostrar `"<p>El ciclo está funcionando.</p>"`
- Después hacé clic en "Guardar y enviar" para ejecutar tu primer ciclo `while` en PHP.

`@CódigoBase`
```php
<?php
  $loopCond = true;
  while (){
    //Mostrá con Echo tu mensaje que el ciclo se está ejecutando más abajo

    $loopCond = false;
  }
  echo "<p>Y ahora está terminado.</p>";
?>
```

`@Solución`
```php
<?php
  $loopCond = true;
  while ($loopCond ==true){
    //Mostrá con Echo tu mensaje que el ciclo se está ejecutando más abajo
    echo "<p>El ciclo está funcionando.</p>";
    $loopCond = false;
  }
  echo "<p>Y ahora está terminado.</p>";
?>
```
---
## Tu primer ciclo While
Ahora es momento de escribir tu propio ciclo `while` desde cero. Quizás podés reproducir el comportamiento de uno de los ciclos `for` del curso anterior, o podés tratar de escribir tu propio programa de lanzamiento de moneda. Lo bueno de programar es que podés hacer lo que quieras.

Salvo que quieras escribir un ciclo infinito a propósito (¡que no vas a querer!), **¡no escribas ciclos infinitos!** Si te das cuenta de que enviaste uno, recargá la página para detenerlo.

`@Instrucciones`
- Escribí el código para tu propio ciclo `while` debajo del comentario que está dentro de las etiquetas `<?php ?>`. Después hacé clic en "Guardar y enviar" para ver el resultado de tu ciclo.

`@Solución`
```php
<?php
  //Agregá un ciclo while a continuación
  $conteoCiclo = 0;
  while ($conteoCiclo<4){
     echo "<p>Número de iteración: {$conteoCiclo}</p>";
     $conteoCiclo ++;
  }
?>
```
---
## Uso de Endwhile
PHP ofrece la siguiente sintaxis alternativa para los ciclos `while`:
```php
<?php
  while(cond) :
  // las sentencias de ciclo van acá
  endwhile;
?>
```
Observá los dos puntos después del paréntesis final y el punto y coma después de la sentencia `endwhile`.

Cuando están integrados en HTML, los ciclos que usan esta sintaxis `endwhile` se pueden leer mejor que la sintaxis equivalente que incluye llaves.

```php
<?php
  while(cond) {
    // las sentencias de ciclos van acá
  }
?>
```
Podés usar cualquier sintaxis que prefieras...salvo en este ejercicio.

`@Instrucciones`
- Convertí tu ciclo `while` del último ejercicio en sintaxis `endwhile`. Después hacé clic en "Guardar y enviar" para asegurarte de que tu nuevo ciclo funciona como el ciclo anterior.

`@CódigoBase`
```php
<?php
  //Agregá un ciclo while a continuación
  $conteoCiclo = 0;
  while ($conteoCiclo<4){
    echo "<p>Número de iteración: {$conteoCiclo}</p>";
    $conteoCiclo ++;
  }
?>
```

`@Solución`
```php
<?php
  //Agregá un ciclo while a continuación
  $conteoCiclo = 0;
  while ($conteoCiclo<4) :
    echo "<p>Número de iteración: {$conteoCiclo}</p>";
    $conteoCiclo ++;
  endwhile;
?>
```
---
## ¿Cómo hacés Do-While?
Habrás notado que un ciclo while controla la condición de ciclo antes de cada iteración del código interno. Una alternativa lógica es controlar la condición después de cada iteración antes de que se inicie el ciclo. Un ciclo `do/while` hace justamente eso. Una consecuencia de esta diferencia es que el código que está dentro de un ciclo `while` puede ser ignorado completamente mientras que el código que está dentro de un ciclo `do/while` se ejecutará al menos una vez.

Esto significa que la condición del ciclo puede depender exclusivamente del código dentro del cuerpo del ciclo. Este es el caso para el código que está en el editor, donde cada iteración representa un lanzamiento de una moneda, y cada vez que el lanzamiento de la moneda sea cruz, el ciclo se detiene.

`@Instrucciones`
- Controlá el código del editor para ver si entendés como va a funcionar. Si no lo entendés no te preocupes. Hacé clic en "Guardar y enviar" y mirá lo que pasa.

`@Solución`
```php
<?php
	$conteoDeLanzamientos = 0;
	do {
		$lanzamiento = rand(0,1);
		$conteoDeLanzamientos ++;
		if ($lanzamiento){
			echo "<div class=\"coin\">H</div>";
		}
		else {
			echo "<div class=\"coin\">T</div>";
		}
	} while ($lanzamiento);
	$verbo = "fueron";
	$final = "lanzamientos";
  if ($conteoDeLanzamientos == 1) {
		$verbo = "fue";
		$final = "lanzamiento";
	}
	echo "<p> {$verbo} {$conteoDeLanzamientos} {$final}!</p>";
?>
```
---
## Terminar el ciclo
En el ejercicio anterior, viste cómo un `do/while` puede usarse para garantizar que el código de un ciclo se ejecute al menos una vez. Por ejemplo:

```php
<?php
  $i = 0;
  do {
    echo $i;
  } while ($i > 0);
?>
```

Este ciclo `do / while` solo se ejecuta una vez y después termina:

1. Primero establecemos `$i` igual a 0.
2. Después, el ciclo funciona una vez y se visualiza `$i`, que es 0.
3. Después se controla la condición `while ($i > 0)`. Dado que `$i` no es mayor que 0, la condición se evalúa como `false`, y el ciclo `do/while` se detiene.

`@Instrucciones`
- Hay un ciclo `do / while` que funciona solamente una vez y después termina. Pero le faltan las llaves `{ }`, los paréntesis `( )`, y los punto y coma `;`. Completá las llaves, paréntesis y puntos y comas que faltan `{ }`, `( )`; y asegurate de que el ciclo `do/while` se ejecute correctamente.

`@CódigoBase`
```php
<?php
  $loopCond = false;
  do
    echo "<p>El ciclo se ejecutó aún cuando la condición del ciclo era falsa.</p>"
  while $loopCond
  echo "<p>Ahora el ciclo terminó de ejecutarse.</p>";
?>
```

`@Solución`
```php
<?php
$loopCond = false;
  do {
    echo "<p>El ciclo se ejecutó aún cuando la condición del ciclo era falsa.</p>";
  } while ($loopCond);
  echo "<p>Ahora el ciclo terminó de ejecutarse.</p>";
?>
```
