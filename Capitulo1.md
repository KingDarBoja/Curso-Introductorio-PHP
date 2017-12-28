---
Capitulo     : Capítulo 1
Titulo       : Introducción a PHP
Descripción  : Este tutorial te presentará PHP, un lenguaje de programación del lado del servidor que podés usar para hacer sitios web dinámicos y aplicaciones web.
---

## PHP en Acción

PHP es un lenguaje de programación que puede hacer todo tipo de cosas: evaluar datos de formularios enviados desde un navegador, construir contenido web a medida para el navegador, hablar a una base de datos, e incluso enviar y recibir cookies (pequeños paquetes de datos que tu navegador usa para recordar cosas, como por ejemplo, si te registraste en Codecademy.com).

Mirá el código del editor. ¿Te parece conocido, no? Eso es porque mucho de lo que ves es HTML, que ya conocés. El código PHP se escribe en <?php y ?>. ¿Ves cómo genera números, crea listas y agrega texto directamente en tu página web?

`@Instrucciones`

- Haz clic en "Guardar y enviar" para comenzar a aprender cómo funciona.

`@Solución`

Archivo index.html
```php

<!DOCTYPE html>
<html>
  <head>
    <link type='text/css' rel='stylesheet' href='style.css'/>
    <title>PHP!</title>
  </head>
  <body>
    <img src="http://i1061.photobucket.com/albums/t480/ericqweinstein/php-logo_zps408c82d7.png"/>
    <div class="header"><h1>
      <?php
      $bienvenido = "¡Empecemos con PHP!";
      echo $bienvenido;
      ?>
    </h1></div>
    <p><strong>Generá una lista:</strong>
      <?php
      for ($numero = 1; $numero <= 10; $numero++) {
        if ($numero <= 9) {
            echo $numero . ", ";
        } else {
            echo $numero . "!";
        }
      }; ?>
    </p>
    <p><strong>Cosas que podés hacer:</strong>
      <?php
        $cosas = array("Hablar a bases de datos",
        "Enviar cookies", "Evaluar formularios de datos",
        "Construir páginas web dinámicas");
        foreach ($cosas as $cosa) {
            echo "<li>$cosa</li>";
        }
        unset($cosas);
      ?>
    </p>
    <p><strong>Esta oración desordenada cambiará cada vez que hagas clic en Guardar y Enviar<strong></p>
    <p>
      <?php
        $palabras = array("el ", "rápido ", "marrón ", "zorro ",
        "saltó ", "sobre ", "el ", "vago ", "perro ");
        shuffle($palabras);
        foreach ($palabras as $palabra) {
            echo $palabra;
        };

        unset($palabra);
        phpinfo();
      ?>
    </p>
  </body>
</html>

```

Archivo style.css

```css
header {
    width: 300px;
    height: 25px;
    background-color: #5A68A5;
    border-radius: 10px;
}

img {
    width: 200px;
    float: right;
}

h1 {
    font-family: Verdana, sans-serif;
    font-size: 18px;
    text-align: center;
    color: #ffffff;
}

p {
    font-family: Tahoma, sans-serif;
}

li {
    font-family: Tahoma, sans-serif;
    list-style-type: square;
}

input {
    width: 280px;
}
```

:warning: **Nota:** En este ejercicio se presenta un esquema general de como funciona un código php dentro de una página web a tráves del uso de las etiquetas `<?php ?>`. En el resto de ejercicios no se repetirán dichos archivos, para enfocarse solamente en la programación php.

---
## ¿Por qué aprender PHP?

"¿Para qué?" podés preguntarte. "Si puedo hacer eso con JavaScript". Es verdad. Pero el conocimiento de JavaScript puede ser limitado.

JavaScrip generalmente se ejecuta en el navegador, o **cliente**. Esto significa que solo sabe lo que pasa en tu navegador, además de cualquier otra información que obtenga de lo/s sitio/s web con los que te conectás.

Por otra parte, PHP, se ejecuta en la misma computadora que el sitio web que estás visitando, que se conoce como **servidor**. Esto significa que tiene acceso a toda la información y archivos de esa máquina, que permite construir páginas HTML a medida para enviar a tu navegador, administrar cookies y ejecutar tareas o calcular datos de ese sitio web.

`@Instrucciones`

- Ya escribimos un poco de PHP en el editor que está a la derecha, pero no está completo. En la línea 8, escribí `¡Mi primera línea en PHP!` entre las "".

`@CódigoBase`
```php
<?php
  echo "";
?>
```

`@Solución`
```php
<?php
  echo "¡Mi primera línea en PHP!";
?>
```

---
## PHP y HTML
El código PHP puede escribirse directamente en tu HTML, de esta forma:
```php
<body>
  <p>
    <?php
      echo "¡Estoy aprendiendo PHP!";
    ?>
  </p>
</body>
```
Tu código PHP va dentro de los delimitadores `<?php` y `?>`. Acá usamos la función `echo` para mostrar `¡Estoy aprendiendo PHP!` También terminamos la línea con un punto y coma.

`@Instrucciones`
- Probá. En la línea 8, usá `echo` para mostrar tu nombre. Asegurate de terminar tu línea con un punto y coma.

`@Solución`
```php
<?php
  echo "Tu nombre";
?>
```

---
## Archivos PHP
Quizás notaste que nuestro archivo principal ahora es `index.php` en lugar de `index.html`. Esto es importante. Le dice al intérprete de PHP que ahí, en el archivo, hay un código PHP para evaluar.

---
## Echo
La función echo muestra las cadenas. Si escribís

```php
<?php
  echo "¡Hola!";
?>
```
PHP mostrará `¡Hola!`.

Asegurate de terminar tu línea de PHP con un punto y coma.

`@Instrucciones`
- En la línea 8 entre `<?php` y `?>` usá `echo` para mostrar `"Estoy aprendiendo PHP"`. Asegurate de terminar tu código PHP con un punto y coma.

`@Solución`
```php
<?php
  echo "Estoy aprendiendo PHP";
?>
```

---
## Strings (Cadenas)

Una cadena es una palabra o frase entre citas, así: "¡Hola mundo!"

Podés escribir una cadena toda de una sola vez, así:

```php
<?php
  echo "¡Hola mundo!";
?>
```

O utilizar el operador de concatenación, que une varias cadenas:

```php
<?php
   echo "¡Hola," . " " . "mundo" . "!";
?>
```

El operador de concatenación es solo un punto (`.`). (Si estás aprendiendo PHP pero ya conocés JavaScript, te contamos que el punto hace lo mismo para las cadenas que el `+` en JavaScript)

`@Instrucciones`
- Seguí adelante y mostrá cualquier cadena que quieras en la pantalla, usando `echo` en la línea 8. ¡Intentá usar el operador de concatenación si te sentís seguro!

`@Solución`
```php
<?php
  echo "¡Hola mundo!" . " " . "Estoy en PHP";
?>
```

---
## Aritmética
Además de mostrar las cadenas, PHP también puede hacer operaciones matemáticas.
```php
<?php
  echo 5 * 7;
?>
```
Acá usamos la función `echo` para multiplicar 5 por 7, y terminamos nuestra línea de código con un punto y coma. PHP mostrará `35`.

`@Instrucciones`
En la línea 8 entre `<?php` y `?>`, usá la función echo para calcular `17` por `123`. Asegurate de terminar tu código PHP con un punto y coma.

`@Solución`
```php
<?php
  echo 17 * 123;
?>
```

---
## Variables
Hasta ahora mostramos cadenas e hicimos operaciones matemáticas en la pantalla.

Para hacer programaciones más complejas necesitamos una forma de "guardar" estos valores. Podemos hacer esto con el uso de variables. Una variable puede almacenar una cadena o un número y le da, a esa cadena o número, un nombre que distingue entre mayúsculas y minúsculas.

**Ejemplos:**

- `$miNombre = "María";`
- `$miEdad = 32;`

Todos los nombres de variables en PHP comienzan con el signo pesos ( `$` ).

`@Instrucciones`
- En la línea 8, creá una variable que se llame `$miNombre` y establecela para que sea igual a tu nombre. Asegurate de terminar tu código PHP con un punto y coma.


`@Solución`
```php
<?php
  $miNombre = "Tu nombre aquí";
?>
```

---
## Punto y Coma
Probablemente te diste cuenta de que nuestras líneas de código PHP terminan en punto y coma (`;`). PHP requiere punto y coma en cada sentencia, que es la unidad más corta de un código independiente. (Por ejemplo, `echo "¡Hola!";` o `2 + 2;`),

Podés suponer que una sentencia es un pensamiento PHP completo. `19` + o `echo` no son pensamientos completos, así que no deberías poner punto y coma al final.

```php
<?php
  echo "¡Usá los punto y coma";
?>
```

`@Instrucciones`
- Sin querer nos olvidamos de poner el punto y coma en la línea 8. ¡Agregalo!

`@CódigoBase`
```php
<?php
  echo "¡Vamos todavía!"
?>
```

`@Solución`
```php
<?php
  echo "¡Vamos todavía!";
?>
```

---
## Comentarios
Así como algunas veces ponemos comentarios en nuestro lenguaje CSS (usando `/* de esta forma */`) o en nuestro lenguaje HTML (usando `<!-- de esta forma -->`), ¡también podemos poner comentarios en nuestro código PHP! Lo hacemos usando dos barras (`//`), así:

```php
<?php
    echo "¡Estoy en pantalla!";
    // ¡Yo no! Soy un comentario.
?>
```

`@Instrucciones`
- Continuá y agregá un comentario a tu código PHP. ¡Podés decir lo que quieras!

`@CódigoBase`
```php
<?php
  echo "¡Vamos todavía!";

?>
```

`@Solución`
```php
<?php
  echo "¡Vamos todavía!";
  // ¡Soy un comentario!
?>
```


---
## Practicando con PHP
- **_Crear una variable:_** ¡La práctica hace al maestro! Vamos a empezar creando una variable y dándole un valor.

- **_Dejá que la máquina haga las cuentas:_** Recuerda que las computadoras se crearon para hacer lo que nosotros no queremos hacer, eso incluye hacer cuentas complicadas.

- **_¡Echo!:_** ¡Buen trabajo! Pero no apareció en tu documento .php porque no lo mostramos usando echo. ¡Solucionemos eso!

`@Instrucciones`
- Declará una variable, `$miNombre`, y dale tu nombre como cadena.
- Después de tu primera variable, creá una segunda variable, `$miEdad`, y ajustala igual que tu edad como número. Acordate: no hay que encerrar los números con comillas.
- Terminemos esto. Debajo del código PHP que ya tenés, usá `echo` para mostrar en pantalla tu nombre y tu edad.

`@Solución`
```php
<?php
  $miNombre = "Tu nombre";
  // Cualquier número como edad
  $miEdad = 30;
  echo $miNombre;
  echo $miEdad;
?>
```
