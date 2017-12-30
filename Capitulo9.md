---
Capitulo     : Capítulo 9
Titulo       : Programación orientada a objetos, Parte 1
Descripción  : Los objetos son combinaciones de datos (variables) y acciones (funciones). En este curso, vamos a conocer cómo funcionan los objetos en PHP y a aprender cómo crear los nuestros.

---
## ¿Qué es la programación orientada a objetos?
PHP es un lenguaje de **programación orientado a objetos**, lo que significa que puede incluir variables y funciones.

Cuando hablamos de **objetos**, nos referimos a variables que pertenecen a esos objetos como **propiedades** (o atributos o campos), y las funciones se llaman **métodos**.

Estos objetos son esenciales cuando nos ocupamos de PHP, porque casi todo es un objeto: por ejemplo, un array es un objeto también.

Y esto muestra porqué usamos objetos: podemos tener nuestras funciones y datos en un lugar, podemos crear objetos fácilmente usando **clases** (constructores de objetos), así que podemos crear un montón de **instancias** (objetos, que han sido construidos mediante una clase), que contienen la mayor parte de la información, excepto algunas mínimas variantes.

A la derecha, hay una clase _Persona_ y una instancia almacenada en `$yo`. Después se llama el `saludo()` método del objeto `$yo` y el resultado se muestra usando `echo`.

`@Instrucciones`
- Intentá comprender el código que está a la derecha. (No te preocupes si una parte es un poco engañosa—vamos a repasarla) Después hacé clic en "Guardar y enviar".

`@Solución`
```php
<?php
  // El código que sigue crea la clase
  class Persona {
    // Crear algunas propiedades (variables atadas a un objeto)
    public $estaViva = true;
    public $nombre;
    public $apellido;
    public $edad;

    // Asignar valores
    public function __construct($nombre, $apellido, $edad) {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
    }

    // Crear un método (función atada a un objeto)
    public function saludo() {
      return "Hola mi nombre es " . $this->nombre . " " . $this->apellido . ". ¡Encantado de conocerte! :-)";
    }
  }

  // Crear una new persona llamada "aburrida 12345", que tiene 12345 años ;-)
  $yo = new Persona ('aburrida', '12345', 12345);

  // Mostrar, lo que devuelve el método saludo
  echo $yo->saludo();
?>
```
---
## Objetos de la vida real
Cómo se usa la programación orientada a objetos en la vida real se puede mostrar con un foro como en el siguiente ejemplo:

Cada _usuario_ (objeto) del foro tiene los mismos derechos: se puede _registrar_ y _escribir_ (métodos), puede contener ciertos _ajustes_ (propiedades), pero cada usuario tiene un _nombre_ (otra propiedad) diferente.

Cada usuario se crea fácilmente, como vos creás una nueva instancia de una clase de _Usuario_ cuando te registrás. Como ya vimos, hay algunas propiedades y métodos que tienen todas las instancias (como registrarse y escribir) y hay otras propiedades y métodos que son únicos (como el nombre de cada usuario).

Sin la programación orientada a objetos —**OOP** (por sus siglas en inglés) —esto no podría hacerse fácilmente.

Otro ejemplo: En el ejercicio anterior, hay una clase `Persona`, entonces cada `new Persona` tiene algunas propiedades, como `$estáViva` o `$nombre`, y un método `saludo()`.

Ahora hay una sola _instancia_ de la clase `Persona`: `$yo`. Pero vamos a reconstruir esta clase y vos vas a crear otra instancia de clase, así que tu nombre también se va a mostrar en la pantalla usando `echo`.

En el próximo ejercicio vamos a crear algunas clases, así que empecemos a hacer un código.

---
## Construir tu primera clase
Genial, ahora conocés los términos técnicos. Empecemos a hacer el código reconstruyendo la clase `Persona`.

La sintaxis básica de clase se ve de la siguiente manera:

```php
<?php
  class NombreDeClase {

  }
?>
```

La palabra clave `class` significa que vos creaste una nueva class; la sintaxis es muy similar a la sintaxis de la `function`.

Vos podés crear nuevas instancias de esta clase usando la siguiente sintaxis: `$obj1 = new nombreDeClase();`

La palabra clave `new` significa que vos creaste un objeto `new` y asegura que tus argumentos se agreguen como propiedades, entonces se inicializa el constructor (lo que vamos a tratar más adelante).

No necesitamos pasar ningún argumento, ya que no agregamos ninguna propiedad (que puede almacenar diferentes valores dependiendo de la instancia) por ahora.

`@Instrucciones`
- Creá una clase `Persona`.
- Creá dos instancias de la clase _Persona_ `$maestro` y `$estudiante`.

`@CódigoBase`
```php
<?php
  // La clase Persona acá

?>
```

`@Solución`
```php
<?php
  // La clase Persona acá
  class Persona {

  }
  $maestro = new Persona();
  $estudiante = new Persona();
?>
```
---
## Propiedades (1)
Buen trabajo, ahora podemos agregar algunas propiedades a nuestra clase.

Como te acordarás, las propiedades son piezas de datos agrupadas a un objeto, y podés imaginarte un objeto como un conjunto de información y acciones.

```php
<?php
  class Fruta {
    public $contar = 3;
    public $tipo;
  }

  $manzana = new Fruta();
  $manzana->tipo= "manzana;
  print $manzana->contar; // 3
  print $manzana->tipo;  // manzana
?>
```

1. En el ejemplo anterior, primero creamos una nueva clase que se llama `Fruta`.
2. Después agregamos una propiedad, `$contar`, y establecemos su valor en 3.
3. Luego, agregamos una propiedad, `$tipo`, pero no almacenamos nada todavía.
4. Después de la definición de clase, creamos una nueva instancia de `Fruta` y la almacenamos en `$manzana`.
5. Después establecemos la propiedad `$tipo` de `$manzana` a la cadena `"manzana"`.
6. Finalmente, mostramos las dos propiedades de `$manzana`.

Vamos a probar esto.

`@Instrucciones`
- Agregá una propiedad `public $estaViva` a la clase `Persona` y asigná el valor `true` (verdadero) a `$estaViva`, como la propiedad `$contar` antes mencionada.
- Agregá otras tres propiedades `public` a la clase `Persona`: `$nombre`, `$apellido` y `$edad`. No asignes ningún valor a estos como la propiedad $tipo indicada más arriba.
- Mostrá usando `echo` el valor de la propiedad `$maestro` `estaViva`.

`@CódigoBase`
```php
<?php
  class Persona {

  }
  $maestro = new Persona();
  $estudiante = new Persona();
?>
```

`@Solución`
```php
<?php
  class Persona {
    public $estaViva = true;
    public $nombre;
    public $apellido;
    public $edad;
  }
  $maestro = new Persona();
  $estudiante = new Persona();
  echo $maestro->estaViva;
?>
```
---
## Propiedades (2)
Muy bien. Ya tenemos algunas propiedades.
Pero ahora `$maestro` y `$estudiante` son iguales; esto tenemos que cambiarlo inmediatamente, ¿no?

La solución: tenemos que crear un constructor para crear diferentes objetos. Este constructor es también un método, pero no te preocupes por esto todavía.

La sintaxis:

```php
<?php
  public function __construct($prop1, $prop2) {
    $this->prop1 = $prop1;
    $this->prop2 = $prop2;
  }
?>
```

Tenés que acordarte de la palabra clave `public` y de la notación flecha.

Algunas cosas nuevas:

1. Estás creando una función unida a una clase (un **método**).
2. El método constructor **tiene que** llamarse `__construct()`.
3. Finalmente. la forma rara de asignar valores: `$esta->prop1 = $prop1` significa que el valor que vos pasás en la función `__construct()` por medio de la palabra clave `new` se asigna a `$this`, que representa el objeto que estás tratando, y `->prop1` es la propiedad real del objeto.

Al crear una nueva instancia usando la palabra clave `new`, justamente llamás a este método `__construct()`, el que construye el objeto. Es por eso que tenemos que pasar algunos argumentos cuando creamos una instancia de una clase, porque esta es la forma en que se establecen las propiedades.

`@Instrucciones`
- Agregá un constructor a una `Persona` con tres parámetros, `$nombre`, `$apellido` y `$edad`.
- En tu constructor, usá los tres parámetros para establecer las propiedades `public` `$nombreDePila`, `$apellido` y `$edad`.
- Cambiá tu ejemplificación `$maestro` para almacenar `new Persona("aburrida","12345",12345)`.
- Agregá tu `$nombre`, `$apellido` y `$edad` a `$estudiante` de la misma manera.
- Mostrá usando `echo` la `$edad` de `$estudiante`.

`@CódigoBase`
```php
<?php
  class Persona {
    public $estaViva = true;
    public $nombre;
    public $apellido;
    public $edad;
  }
  $maestro = new Persona();
  $estudiante = new Persona();
  echo $maestro->estaViva;
?>
```

`@Solución`
```php
<?php
  class Persona {
    public $estaViva = true;
    public $nombre;
    public $apellido;
    public $edad;
    public function __construct($nombre, $apellido, $edad) {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
    }
  }
  $maestro = new Persona("Cansado", "54321", 54321);
  $estudiante = new Persona("Manuel","Bojato",21);
  echo $estudiante->edad;
?>
```
---
## Un método para la locura
Muy bien, ya hicimos la parte más larga y difícil.

Como ya vimos, los **métodos** —funciones unidas a objetos— tienen la siguiente sintaxis:

```php
<?php
  public function funcnombre($parametroOpcional) {
    // Hacé algo
  }
?>
```

Ahora sabemos que la función `__construct` es una función especial, que se llama cuando se crea un nuevo objeto usando una nueva palabra clave llamada `new`.
Además, aprendimos que tenemos que usar la palabra clave `$this` si queremos acceder a algunas propiedades de una clase.

Si queremos que un método devuelva una oración que contenga el nombre, vamos a tener que usar `$this->nombre`. (Cómo ves, no hay $ cuando accedés a una propiedad en una clase.)

Llamar a un método es similar a acceder a una propiedad. Solo tenés que agregar los paréntesis: `$obj1 -> meth1();`

`@Instrucciones`
- Agregá un método llamado `saludo()` a tu clase. Este método debe devolver `return "Hola, mi nombre es " . $this->nombre . " " . $this->apellido .". ¡Encantado de conocerte!"`.
- Llamá a este nuevo método de `saludo()` en `$maestro` y `$estudiante` y mostrá el resultado en la página usando echo.

`@CódigoBase`
```php
<?php
  class Persona {
    public $estaViva = true;
    public $nombre;
    public $apellido;
    public $edad;
    public function __construct($nombre, $apellido, $edad) {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
    }
  }
  $maestro = new Persona("Cansado", "54321", 54321);
  $estudiante = new Persona("Manuel","Bojato",21);
  echo $estudiante->edad;
?>
```

`@Solución`
```php
<?php
  class Persona {
    public $estaViva = true;
    public $nombre;
    public $apellido;
    public $edad;
    public function __construct($nombre, $apellido, $edad) {
      $this->nombre = $nombre;
      $this->apellido = $apellido;
      $this->edad = $edad;
    }
    public function saludo() {
      return "Hola, mi nombre es " . $this->nombre . " " . $this->apellido . ". ¡Encantado de conocerte!";
    }
  }
  $maestro = new Persona("cansado", "54321", 54321);
  $estudiante = new Persona("Manuel","Bojato",21);
  echo $maestro->saludo();
  echo $estudiante->saludo();
?>
```
---
## Juntar todo, Parte I
¡Muy bien! Construiste la clase `Persona`.

Vamos a crear otra clase: la clase `Perro`. Debe tener una propiedad `public $cantidadDePatas`, que almacene el valor 4. Además, tiene que tener la posibilidad de darle a cada perro un `$nombre` usando un `__construct` (constructor).

Por supuesto también necesitamos un método, ya que un perro puede `ladrar()`. Nuestros perros también se pueden presentar, para `saludar()`, así que también vamos a necesitar un método para esto.
Por último necesitaremos dos lindos perros.

¡Empecemos!

`@Instrucciones`
- Creá una clase `Perro`.
- Agregá una propiedad public que se llame `$cantidadDePatas`, que almacena el valor 4 en la clase `Perro`.
- Agregá otra propiedad `Public` que se llame `$nombre`, que no contenga ningún valor.
- Agregá el `__construct()` o método, que acepta `$nombre` como parámetro.
- En este `__construct()` o método, agregá un código, de modo que `$this->nombre` contenga `$nombre`.

`@Solución`
```php
<?php
  class Perro {
    public $cantidadDePatas = 4;
    public $nombre;
    public function __construct($nombre) {
      $this->nombre = $nombre;
    }
  }
?>
```
---
## Juntar todo, Parte II
Buen, ya casi estamos. Ahora agreguemos dos métodos más y creemos algunos objetos.

`@Instrucciones`
- Agregá un método `public` a la clase `Perro` que se llama `ladrar()`, que nos (devuelve) `return"¡Guau!"`
- Agregá un método `public` que se llame `saludo()` a la clase `Perro`. Este método nos tiene que devolver una linda oración que contenga la propiedad `$nombre` del `Perro`, que se presenta solo.
- Creá dos instancias de la clase `Perro` y almacená la que tiene el `$nombre "Pluto"` en la variable `$perro1` y la otra con el `$nombre "Amigo"` en la variable `$perro2`.
- Como te imaginabas, llamá al método `ladrar()` en `$perro1` y mostrá el resultado con la función `echo`.
- El último: Llamá al método `saludo()` en `$perro2` y mostrá en pantalla el resultado con la función `echo`.

`@CódigoBase`
```php
<?php
  class Perro {
    public $cantidadDePatas = 4;
    public $nombre;
    public function __construct($nombre) {
      $this->nombre = $nombre;
    }
  }
?>
```

`@Solución`
```php
<?php
  class Perro {
    public $cantidadDePatas = 4;
    public $nombre;
    public function __construct($nombre) {
      $this->nombre = $nombre;
    }
    public function ladrar() {
      return "¡Guau!";
    }
    public function saludo() {
      return $this->nombre;
    }
  }
  $perro1 = new Perro("Pluto");
  $perro2 = new Perro("Amigo");
  echo $perro1->ladrar();
  echo $perro2->saludo();
?>
```
