---
Capitulo     : Capítulo 10
Titulo       : Programación orientada a objetos, Parte 2
Descripción  : Los objetos PHP son instancias de clases. En este curso vamos a aprender más sobre clases y veremos otros temas, como la herencia.
---

## Métodos de clase y objeto
¿Te acordás de que vimos funciones integradas en PHP? Bueno, podemos combinar esa idea con lo que sabemos de clases y objetos: es decir, son funciones integradas en PHP que nos dan información interesante sobre las clases y objetos que hemos creado.

Mirá el ejemplo en el editor que está a la derecha. Pusimos una demostración de tres métodos integrados muy útiles: `is_a()`, que usamos para buscar si un objeto en particular es una instancia de una clase dada; `property_exists()`, para ver si un objeto tiene una propiedad dada; y `method_exists()`, para ver si un objeto tiene un método dado.

Fijate que el primer argumento es el objeto que estamos mirando y el segundo es el nombre de la clase, propiedad o método, como una cadena (`"string"`).

`@Solución`
```php
<?php
  class Persona {
    public $nombre = "";

    function __construct($nombre) {
      $this->nombre = $nombre;
    }

    public function bailar() {
      return "Estoy bailando";
    }
  }

  $yo = new Persona("Sabrina");
  if (is_a($yo, "Persona")) {
    echo "Soy una persona, ";
  }
  if (property_exists($yo, "nombre")) {
    echo "Tengo un nombre, ";
  }
  if (method_exists($yo, "bailar")) {
    echo "y se bailar.";
  }
?>
```
---
## Herencia
Como estuviste pensando en clases y objetos, te habrás dado cuenta de que una clase puede en realidad ser un tipo especial de otra clase. Por ejemplo, podés tenér una clase `Vehículo` y una clase `Camión` y seguramente te va a ahorrar un montón de tiempo de escribir si de alguna manera podés especificar que las instancias `Camión` deberían tener en forma automática muchas de las mismas propiedades y métodos que las instancias `Vehículos`.

PHP te permite lograr esto mediante un proceso que se llama **herencia**. Herencia es una forma que tiene una clase de tomar las propiedades o métodos de otra clase. Podés decir que una clase se **extiende** en la otra. Esto se usa para expresar una relación "is-a" —por ejemplo, un Camión "is-a" (es un) Vehículo, de modo que puede heredar de Vehículo, pero una Motocicleta no es un Camión, por ende no debería heredar de Camión (aunque ambos pueden heredar de Vehículo).

Podemos hacer que una clase de PHP herede de otra con la palabra clave extends.

`@Instrucciones`
- Mira el ejemplo. Creamos dos clases, `Forma` y `Cuadrado`, donde `Cuadrado` está heredando de `Forma`. No especificamos que `Cuadrado` tiene una propiedad `$tieneLados`, pero debe heredarla de `Forma`.
- Completá la sentencia `if` usando el método `property_exists()` para controlar si `$cuadrado` tiene la propiedad `'tieneLados'`.

`@CódigoBase`
```php
<?php
  class Forma {
    public $tieneLados = true;
  }

  class Cuadrado extends Forma {

  }

  $cuadrado = new Forma();
  // Agregá tu código a continuación.
  if ( ) {
    echo "Tengo lados.";
  }
?>
```

`@Solución`
```php
<?php
  class Forma {
    public $tieneLados = true;
  }

  class Cuadrado extends Forma {

  }

  $cuadrado = new Forma();
  // Agregá tu código a continuación.
  if ( property_exists($cuadrado, "tieneLados") ) {
    echo "Tengo lados."; // Imprime "Tengo lados."
  }
?>
```
---
## Sobreescribir métodos padre
¡Muy bien!

Algunas veces queremos una clase hijo (o **subclase**) para poder sobreescribir una propiedad o un método de su clase padre (o **superclase**).

Por ejemplo, podemos tener una clase `Forma` con una propiedad `$lados` establecida como `true`, pero podemos querer que `Cuadrado` sobreescriba esta propiedad y establezca `$lados` como 4 (dado que un cuadrado siempre tiene cuatro lados). Eso quedaría así:

```php
<?php
  class Forma {
    $lados = true;
  }

  class Cuadrado extends Forma {
    $lados = 4;
  }
?>
```

Es bastante fácil, recién creaste una nueva propiedad o método en la clase hijo con el mismo nombre del de la clase padre, y la versión hijo siempre tendrá primacía sobre la versión heredada.

`@Instrucciones`
- Creamos una clase `Vehiculo` en el editor. Creá una clase hijo, `Bicicleta`, que sobreescriba de la clase `Vehiculo` a `public function bocinazo()` y la reemplace con una función que devuelva usando la función `return "¡Pip Pip!"`.

- Creá una instancia `$bicicleta` de la clase `Bicicleta` y mostrá usando `echo` el resultado de llamar el método `bocinazo()`.

`@CódigoBase`
```php
<?php
  class Vehiculo {
    public function bocinazo() {
      return "HONK HONK!";
    }
  }
  // Agregá tu código a continuación.

?>
```

`@Solución`
```php
<?php
  class Vehiculo {
    public function bocinazo() {
      return "HONK HONK!";
    }
  }
  // Agregá tu código a continuación.
  class Bicicleta extends Vehiculo {
    public function bocinazo() {
      return "¡Pip Pip!";
    }
  }
  $bicicleta = new Bicicleta();
  echo $bicicleta->bocinazo(); // Imprime "¡Pip Pip!".
?>
```
---
## Palabras finales
Cuando eras chico, quizás alguno de tus padres te dijo algo así: "No podés hacer eso y no se habla más. ¡Terminemos, es mi decisión _final_!"

En PHP, una clase padre puede evitar que sus hijos sobreescriban sus métodos con —adivinaste— la palabra clave final.

Usás la palabra clave `final` en tu código para controlar qué métodos pueden modificar las subclases de una clase. Por ejemplo, podés querer que todos los `Vehiculos` tengan el mismo método de `manejar()` sin importar cual, de modo que vas a prefijar la definición del método con `final`, así:

```php
<?php
class Vehiculo {
  final public function manejar() {
    return "¡Estoy manejando!";
  }
}
?>
```

`@Instrucciones`
- Actualizá tu código del último ejercicio para usar la palabra clave `final` para la función `bocinazo()` dentro del `Vehiculo`. Observá cómo en vez de obtener `"¡Pip Pip!"`, obtenemos un error. ¡No se puede sobreescribir acá!

`@CódigoBase`
```php
<?php
  class Vehiculo {
    public function bocinazo() {
      return "HONK HONK!";
    }
  }
  // Agregá tu código a continuación.
  class Bicicleta extends Vehiculo {
    public function bocinazo() {
      return "¡Pip Pip!";
    }
  }
  $bicicleta = new Bicicleta();
  echo $bicicleta->bocinazo(); // Imprime "¡Pip Pip!".
?>
```

`@Solución`
```php
<?php
  class Vehiculo {
    final public function bocinazo() {
      return "HONK HONK!";
    }
  }
  // Agregá tu código a continuación.
  class Bicicleta extends Vehiculo {
    public function bocinazo() {
      return "¡Pip Pip!";
    }
  }
  $bicicleta = new Bicicleta();
  echo $bicicleta->bocinazo();
  // Arroja error: No se puede sobreescribir el método final de Vehiculo::bocinazo().
?>
```
---
## Constantes de clase y resolución de alcance
Hablamos mucho sobre cambiar variables en PHP, pero a veces queremos variables que no cambien. Estas están prefijadas con la palabra clave `const` (abreviatura de **constante**).

PHP nos deja establecer constantes sobre una base clase por clase. Cada clase tiene su propio alcance, que es el contexto en el cual se puede usar la variable.

```php
<?php
  class Inmortal extends Persona {
    // ¡Los inmortales no mueren nunca!
    const vivo = true;
  }

  // Si verdadero...
  if (Immortal::vivo) {
    echo "Yo vivo para siempre.";
  }
  // echo muestra en pantalla "Yo vivo para siempre."
?>
```

En el ejemplo anterior, usamos `::` para acceder a la constante vivo dentro de la clase `Inmortal`.

Observá que las constantes **NO** empiezan con `$`.

`@Instrucciones`
- Creamos una clase `Ninja` para vos en el editor. Establecé una constante `stealth` para hacer la cadena `"MAXIMO"`.
- Después mostrá en la pantalla con la función echo y usando `Ninja::stealth`. Esto `::` es el operador de resolución de alcance.

`@CódigoBase`
```php
<?php
  class Persona {

  }
  class Ninja extends Persona {
    // Agregá tu código acá...

  }
  // ...y acá.

?>
```

`@Solución`
```php
<?php
  class Persona {

  }
  class Ninja extends Persona {
    // Agregá tu código acá...
    const stealth = "MAXIMO";
  }
  // ...y acá.
  echo Ninja::stealth;
?>
```
---
## La palabra clave Static
¡Buen trabajo!

Probablemente notaste que podemos acceder a la constante de la clase `Ninja` sin crear realmente una instancia de `Ninja`, y si sos muy vivo te podés estar preguntando si es posible acceder a las propiedades o métodos de la clase sin crear una instancia de la clase. La respuesta es que sí.

La palabra clave `static` te deja usar una propiedad o método de clase sin haber creado una instancia de esa clase. Funciona así:

```php
<?php
  class Persona {
    public static $estaVivo = "¡Sip!"
    public static function saludo() {
      echo "¡Hola ahi!";
    }
  }

  echo Persona::$estaVivo;
  // muestra "¡Sip!"
  Persona::saludo();
  // muestra "¡Hola ahí!"
?>
```

Cuando se combina con el operador de resolución de alcance, esto nos deja acceder a la información de la clase sin tener que ejemplificar nada. Genial, ¿no es cierto?

`@Instrucciones`
- Creamos una clase `Rey` con un método `anunciar()`. Empezá y llamá al método `anunciar()` usando la palabra clave `static` —no se necesita ninguna instancia.

`@CódigoBase`
```php
<?php
  class Rey {
    // Modificá el código en la línea 10...
    public function anunciar() {
      echo "Un anuncio real";
    }
  }
  // ...y llamá al método acá abajo.

?>
```

`@Solución`
```php
<?php
  class Rey {
    // Modificá el código en la línea 10...
    public static function anunciar() {
      echo "Un anuncio real";
    }
  }
  // ...y llamá al método acá abajo.
  Rey::anunciar();
?>
```
