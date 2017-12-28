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
