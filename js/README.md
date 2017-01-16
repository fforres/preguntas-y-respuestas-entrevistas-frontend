# Preguntas para entrevista de frontend
### JavaScript

### Preguntas
1. [ ] [Explica la delegación de eventos](#1)
1. [ ] [Explica cómo funciona `this` en JavaScript](#2)
1. [ ] [Explica cómo funciona la herencia de prototipos](#3)
1. [ ] [¿Qué opiniones tienes de AMD versus CommonJS?](#4)
1. [ ] [¿Porqué este snippet no funciona como una funcion autoejecutable, si tiene el paréntesis al final? ¿Cómo debería ser?](#5)
    ```javascript
    function hola(){
        console.log('mundo');
    }()
    ```

1. [ ] [¿Cuál es la diferencia entre una variable: `null`, `undefined` y no declarada?](#6)
1. [ ] [¿Qué es un closure? ¿Cómo y porqué usarías uno? ¿Podrías darme un ejemplo de uso?](#7)
1. [ ] [¿Qué es una función anónima? ¿Dónde usarías una? ¿Cuál es la desventaja de ellas?](#8)
1. [ ] [¿Cuál es la diferencia entre un objeto "host" y un objeto "nativo"?](#9) [Revisa aqui](http://stackoverflow.com/questions/7614317/what-is-the-difference-between-native-objects-and-h)
1. [ ] [¿En qué difieren las siguientes expresiones?](#10)
    ```javascript
    // expresión 1
    function Hola() {}

    // expresión 2
    var hola = new Hola()

    // expresión 3
    var hola = Hola()
    ```

1. [ ] [¿En que se diferencias `Function.call()` y `Function.apply()`?](#11)
1. [ ] [¿Explícame `Function.prototype.bind` ?](#12)
1. [ ] [¿Cuál es la diferencia entre deteccion de features, inferencia de features y usar el string UA?](#13)
1. [ ] [Explícame AJAX.](#14)
1. [ ] [¿Qué ventajas y desventajas tiene el usar AJAX?](#15)
1. [ ] [¿Qué es JSONP?](#16)
1. [ ] [Explícame Hoisting](#17)
1. [ ] [¿Cuáles son las ventajas/desventajas de usar clases en ES6?](#18)
1. [ ] [Describe el 'event bubbling'](#19)
1. [ ] [¿Cuál es la diferencia entre `==` y `===`?](#20)
1. [ ] [Haz que esto funcione](#21)
    ```javascript
    [2,3,5,6].replicate()   // [2,3,5,6,2,3,5,6]
    [2,3,5,6].replicate(1)  // [2,3,5,6,2,3,5,6]
    [2,3,5,6].replicate(2)  // [2,3,5,6,2,3,5,6,2,3,5,6]
    ```

1. [ ] [¿Tienes un ejemplo de una expresión ternaria? ¿Porqué "ternaria"?](#22)
1. [ ] [¿Porqué es generalmente una buena idea no agregar cosas al scope global de un sitio web (window)?](#23)
1. [ ] [¿Porqué usarías el evento "load"? ¿Ventajas y desventajas? ¿Alternativas?](#24)
1. [ ] [¿Cómo harías una SPA (Single page application) "SEO Friendly"?](#25)
1. [ ] [¿Qué ventajas tiene el usar promesas?](#26)
1. [ ] [Además de callbacks, ¿qué otras maneras existen de trabajar con asincronía en JavaScript?](#27)
1. [ ] [Teniendo lo siguiente:](#28)
    ```javascript
    function buscarTextoAsíncronamente(texto, callback) {
      const resultado = funcionQueBuscaTextoEnUnOrigen(texto);
      if (resultado) {
        callback(null, resultado);
      } else {
        callback(error, result)
      }
    }
    ```

    ¿Qué se debería hacer para poder usar la misma funcionalidad pero con promesas?

1. [ ] [¿Porqué debería usar o no usar un lenguaje que transpile o compile a JavaScript? ¿Qué ventajas o desventajas existen?](#29)
1. [ ] [¿Cómo debugueas tu código de JavaScript?](#30)
1. [ ] [¿Cómo puedo iterar sobre un objeto y un array?](#31)
1. [ ] [¿Conoces como funciona `[].map()`?](#32)
  - Crea una función que realice lo mismo pero para objetos. (Que reciba como 1er parámetro un objeto, y como 2do parámetro una función que se ejecutará sobre cada par llave/valor).
  - Cambia la función para que pueda recibir como primer parámetro un Array o un Objeto
  - Puedes replicar `[].map()` en `{}.map()`?
1. [ ] [Explícame la diferencia entre `let`, `const` y `var`.](#33)
1. [ ] [Explícame la diferencia entre síncrono y asíncrono.](#34)
1. [ ] [¿Qué es event loop?](#35)
1. [ ] [¿Cuál es la diferencia entre `call stack` y `task queue`?](#36)
1. [ ] [Además de "porque se ve más bonito" ¿por qué debería usar arrow functions `() => {}`?](#37)
1. [ ] [¿Qué diferencia existe en el uso de `hola` entre estas expresiones?](#39)
    ```javascript
    // expresión 1
    function hola(){}

    // expresión 2
    var hola = function(){} 

    // expresión 3
    var hola = () => {}
    ```
1. [ ] [¿Qué es y porqué usar o no Transpiladores? (Babel o buble)](#39)
1. [ ] [¿Qué propuestas de JavaScript es la que más te gustaría/interesa que sea aprobada?](#40)



### Respuestas

1.  [Explica la delegación de eventos](#1)
    <div id="1" />

1.  [Explica como funciona `this` en JavaScript](#2)
    <div id="2" />

1.  [Explica como funciona la herencia de prototipos](#3)
    <div id="3" />

1.  [¿Qué opiniones tienes de AMD versus CommonJS?](#4)
    <div id="4" />

1.  [Porqué este snippet no funciona como una funcion autoejecutable: `function hola(){console.log('mundo')}()` si tiene el paréntesis al final? ¿Cómo debería ser?](#5)
    <div id="5" />

1.  [¿Cuál es la diferencia entre una variable: `null`, `undefined` y no declarada?](#6)
    <div id="6" />

1.  [¿Qué es un closure? ¿Cómo y porqué usarías uno? ¿Podrías darme un ejemplo de uso?](#7)
    <div id="7" />

1.  [¿Qué es una función anónima? ¿Dónde usarías una? ¿Cuál es la desventaja de ellas?](#8)
    <div id="8" />

1.  [¿Cuál es la diferencia entre un objeto "host" y un objeto "nativo"?]](#9)
    <div id="9" />

// http://stackoverflow.com/questions/7614317/what-is-the-difference-between-native-objects-and-h
1.  [¿En qué difieren las siguientes expresiones `function Hola() {}`, `var hola = new Hola()` y `var hola = Hola()`?](#10)
    <div id="10" />

1.  [¿En que se diferencias `Function.call()` y `Function.apply()`?](#11)
    <div id="11" />

1.  [¿Explícame `Function.prototype.bind` ?](#12)
    <div id="12" />

1.  [¿Cuál es la diferencia entre deteccion de features, inferencia de features y usar el string UA?](#13)
    <div id="13" />

1.  [¿Explícame AJAX?](#14)
    <div id="14" />

1.  [¿Qué ventajas y desventajas tiene el usar AJAX?](#15)
    <div id="15" />

1.  [¿Qué es JSONP?](#16)
    <div id="16" />

1.  [¿Explícame Hoisting?](#17)
    <div id="17" />

1.  [¿Cuáles son las ventajas/desventajas de usar clases en ES6?](#18)
    <div id="18" />

1.  [¿Describe el 'event bubbling'?](#19)
    <div id="19" />

1.  [¿Cuál es la diferencia entre `==` y `===`?](#20)
    <div id="20" />

1.  [Has que esto funcione:](#21)
    <div id="21" />
    ```javascript
    [2,3,5,6].replicate()   // [2,3,5,6,2,3,5,6]
    [2,3,5,6].replicate(1)  // [2,3,5,6,2,3,5,6]
    [2,3,5,6].replicate(2)  // [2,3,5,6,2,3,5,6,2,3,5,6]
    ```

1.  [¿Tienes un ejemplo de una expresión ternaria? ¿Porqué "ternaria"?](#22)
    <div id="22" />

1.  [¿Porqué es generalmente una buena idea no agregar cosas a scope global de un sitio web? (window) ?](#23)
    <div id="23" />

1.  [¿Porqué usarías el evento "load"? ¿Ventajas y desventajas? ¿Alternativas?](#24)
    <div id="24" />

1.  [¿Cómo harías una SPA (Single page application) "SEO Friendly"?](#25)
    <div id="25" />

1.  [¿Qué ventajas tiene el usar promesas?](#26)
    <div id="26" />

1.  [Además de callbacks. ¿Qué otras maneras existen de trabajar con asincronía en JavaScript?](#27)
    <div id="27" />

1.  [Teniendo lo siguiente:](#28)
    <div id="28" />
    ```javascript
    function buscarTextoAsíncronamente(texto, callback) {
      const resultado = funcionQueBuscaTextoEnUnOrigen(texto);
      if (resultado) {
        callback(null, resultado);
      } else {
        callback(error, result)
      }
    }
    ```

    Que debería hacer para poder usar la misma funcionalidad pero con promesas?

1.  [¿Porqué debería usar o no usar un lenguaje que transpile o compile a JavaScript? ¿Qué ventajas o desventajas existen?](#29)
    <div id="29" />

1.  [¿Cómo debugueas tu código de JavaScript?](#30)
    <div id="30" />

1.  [¿Cómo puedo iterar sobre un objeto y un array?](#31)
    <div id="31" />

1.  [¿Conoces como funciona `[].map()`?](#32)
    <div id="32" />
    - Crea una función que realice lo mismo pero para objetos. (Que reciba como 1er parámetro un objeto, y como 2do parametro una función que se ejecutará sobre cada par llave/valor).
    - Cambia la función para que pueda recibir como primer parámetro un Array o un Objeto
    - Puedes replicar `[].map()` en `{}.map()`?

1.  [Explícame la diferencia entre `let`, `const` y `var`.](#33)
    <div id="33" />

1.  [Explícame la diferencia entre síncrono y asíncrono.](#34)
    <div id="34" />

1.  [¿Qué es event loop?](#35)
    <div id="35" />

1.  [¿Cuál es la diferencia entre `call stack` y `task queue`?](#36)
    <div id="36" />

1.  [Además de "porque se ve más bonito" ¿Por qué debería usar arrow functions `() => {}`?](#37)
    <div id="37" />

1.  [Qué diferencia existe en el uso de `hola` entre `function hola(){}`, `var hola = function(){}` y `var hola = ()=>{}`](#39)
    <div id="39" />

1.  [¿Qué es y Porqué usar o no Transpiladores (Babel, o buble)?](#39)
    <div id="39" />

1.  [¿Qué proposals de JavaScript es la que más te gustaría/interesa que sea aprobada?](#40)
    <div id="40" />
