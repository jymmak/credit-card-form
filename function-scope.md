# Function Scope Js
En este ejercicio vamos a identificar:las funciones globales, locales, funciones de callback, function expressions, function statements, closure, scope, contextos de ejecución, qué funciones forman parte de la pila de ejecución (stack execution) y qué funciones forman parte de la cola de eventos (event queue).


## Funciones globales

Son las funciones que no se encuentran dentro de otra función.

En este caso, '$(document).ready()', en la línea 1.

## Funciones locales

Son aquellas que se encuentran dentro de una función.

En este caso son: 

* 'console.log()' => línea 3
* Función  que  llama al evento 'input'  => línea 14
* Función 'activeButton()'  => línea 19
* Función 'desactivButton()'  => línea 24
* Función 'longitud(input)'  => linea 29
* Función 'soloNumeros(input)'  => línea 36
* Función 'isValidCreditCard(numberCard)'  => línea 44

## Funciones de callback

Son las funciones que son pasadas como argumentos de otra función.

En este caso son: 

* La función anónima y statement declara en la linea 1 , escucha el evento ready del objeto document.
* La función anónima y statement declarada en la linea 14 , escucha el evento input.
* Función 'longitud' utilizada como argumento de la función 'soloNumeros'  => línea 45

## Funciones expressions

Asigna el resultado de una función como expresión a la variable y puede ser llamada a través de esa variable.

En este caso: No se  encontró ninguna  function expression.

## Funciones statements

Declara una nueva variable, crea una función de un objeto y asigna la función a la variable.

En este caso: 

* function 'activeButton()'  => línea 19
* function 'desactiveButton()'  => línea 24
* function 'longitud(input)'  => línea 29
* function 'soloNumeros(input)'  => línea 36
* function 'isValidCreditCard(numberCard)'  => línea 44

## Clousure 

Es la habilidad que tienen las funciones para recordar el contexto en que fueron creadas, incluso cuando se les invoca en un contexto diferente.

En este caso: 

* La función activeButton y la función desactiveButton pueden hacer referencia a la variable $buttonNext ya que recuerda el entorno donde fue creada.

## Scope 

> Scope Global

En este caso las siguientes variables dentro de la función statement que escucha el evento ready del objeto document son:


*  var $inputCard = $('#card-number'); => línea 6
*  var $inputMonth = $('.input-month'); => línea 7
*  var $inputYear = $('.input-year');  => línea 8
*  var $buttonNext = $('#next'); => línea 9
*  var regexOnlyNumbers = /^[0-9]+$/;  => línea 10
*  var labelErrorOrSuccessMessages = $('label[for="card-number"]'); => línea 11

> Scope Local

*  var regex = /^[0-9]+$/;  => línea 37
*  var creditCardNumber = soloNumeros(longitud(numberCard)); línea  => 45
*  var arr = [];  => línea 47
*  var sumaTotal = 0;  => línea 48


## Contextos de ejecución  

> Stack Execution 

Funciones forman parte de la pila de ejecución.

En este caso: 

*  $(document).ready() => línea 1
*  console.log() => línea 3

> Event Queue 

Funciones que forman parte de la cola de eventos.

* Función longitud(input) => línea 29
* Función isValidCreditCard() => línea 44
* Función soloNumeros(input) => línea 36
* Función activeButton() => línea 19
* Función desactiveButton() => línea 24
* Event handler vinculado a la variable $inputCard => línea 14