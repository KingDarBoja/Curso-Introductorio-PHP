# Curso introductorio a PHP - tomado de Codeacademy

Este repositorio contiene todos los temas y capítulos del antiguo curso de _"Introducción a PHP"_ presentado por Codeacademy.

La finalidad es tener una base de aprendizaje de este lenguaje de programación del lado del servidor de una página web dinámica. Para mayor información o tutoriales de PHP, el manual de PHP está disponible en su [sitio oficial](http://php.net/manual/es/)

Actualmente el lenguaje se encuentra en su versión 7.2, mientras que la versión de PHP utilizada para el curso es la 5.3.10. Por ende, lo más probable es que varias cosas presentes en este curso esten obsoletas. Esto vendría a ser mejorar al curso como tal si alguno desea contribuir al repositorio.

## ¿Qué es PHP?

PHP es un lenguaje de programación de próposito general de código del lado del servidor para desarrollar sitios web dinámicos (acorde a la [wikipedia](https://es.wikipedia.org/wiki/PHP)) y cuyas siglas son un acrónimo recursivo de _PHP: Hypertext Preprocessor_ (es decir, no explica el significado completo de PHP). Actualmente es utilizado en el 83.1 % de sitios web como parte de su tecnología _Back-End_ según el [ 2017 W3Tech market report](https://w3techs.com/technologies/details/pl-php/all/all).

PHP es capaz de hacer muchas cosas más, desde _"scripts"_ del lado del servidor hasta aplicaciones de escritorio, según el [manual oficial de PHP](http://php.net/manual/es/intro-whatcando.php). El lenguaje es fácil de aprender y de utilizar (en mi poca experiencia, me ha servido sin problemas) con buena documentación y soporte universal, básicamente funciona en cualquier sistema operativo y soporta la programación orientada a objetos (POO).

## ¿Puedo programar páginas web del lado del servidor con otro lenguaje?

¡Por supuesto! En la programación existe gran variedad de lenguajes que han sido desarrollados para funcionar del lado del servidor a tráves de los denominados _frameworks_ (o entornos de trabajos). Un claro ejemplo es Python, el cual es un lenguaje de próposito general multiplataforma, enfocado al desarrollo científico y a una fácil legibilidad de código. Este puede ser utilizado como lenguaje de servidor a tráves de _frameworks_ como: _Django_ (el más popular de todos), _Flask_, _web2py_, _TurboGears_, [entre otros](https://wiki.python.org/moin/WebFrameworks).

Si quieres conocer más sobre el top de los lenguajes para aprender en 2018, les dejo este artículo [Web Development 101: Top Web Development Languages to Learn in 2018](https://www.upwork.com/blog/2017/11/top-web-development-languages-2018/) (en inglés).

## Lista de capitulos
1. [Introducción a PHP](Capitulo1.md)
2. [Condicionales - Control de Flujo: If/Else](Capitulo2.md)
3. [Control de Flujo: Switch](Capitulo3.md)
4. [Arrays (o Arreglos)](Capitulo4.md)
5. [Ciclos For](Capitulo5.md)
6. [Ciclos While y Do-While](Capitulo6.md)
7. [Funciones en PHP, Parte 1](Capitulo7.md)
8. [Funciones en PHP, Parte 2](Capitulo8.md)
9. [Programación orientada a objetos, Parte 1](Capitulo9.md)
10. [Programación orientada a objetos, Parte 2](Capitulo10.md)
11. [Arrays (Arreglos) avanzados](Capitulo11.md)


## Plantilla para los capítulos

Cada sección de ejercicios para cada capítulo contiene los siguientes bloques: `@Descripción`, `@Instrucciones`, `@CódigoBase` y `@Solución`. La `@Descripción` contiene la información referente a la programación y lo que se hará en el ejercicio. `@Instrucciones` tendrán los pasos para llegar a la solución del ejercicio propuesto. `@CódigoBase` será el ejemplo a editar para llegar al código solución, el cual vendría siendo el bloque `@Solución`.

#### Ejemplo de ejercicio

`@Descripción`
PHP nos permite mostrar de una manera fácil y sencilla un texto en nuestro navegador, solo basta con utilizar la función _`echo`_ **(no es una función como tal)** dentro de las etiquetas de apertura y cierre `<?php ?>`.

Por ejemplo, al utilizar `echo "¡Hola mundo!"` dentro de las etiquetas, aparecera en nuestro documento html el texto _¡Hola mundo!_.

`@Instrucciones`
- Incluye dentro de las etiquetas una función _echo_ con el texto _"Hola, ¡Estoy programando en PHP!"_

`@CódigoBase`
```php
<?php

?>
```

`@Solución`
```php
<?php
  echo Hola, ¡Estoy programando en PHP!
?>
```

:heavy_exclamation_mark: **Nota:** Para habilitar el resaltado de código en php, se debe agregar _php_ justo despúes de las etiquetas de apertura de código así:

```
```php * Aquí comienza el bloque de código
<?php
  echo Hola, ¡Estoy programando en PHP!
?>
``` * Aquí termina el bloque de código
```
