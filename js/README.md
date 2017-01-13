# Preguntas para entrevista de frontend
### JavaScript

### Preguntas
1. Explica la delegación de eventos
1. Explica como funciona `this` en JavaScript
1. Explica como funciona la herencia de prototipos
1. ¿Que opiniones tienes de AMD versus CommonJS?
1. Porqué este snippet no funciona como una funcion autoejecutable: `function hola(){console.log('mundo')}()` si tiene el paréntesis al final? ¿Como debería ser?
1. ¿Cuál es la diferencia entre una variable: `null`, `undefined` y no declarada?
1. ¿Qué es un closure? ¿Cómo y porqué usarías uno? ¿Podrías darme un ejemplo de uso?
1. ¿Qué es una función anónima? ¿Dónde usarías una? ¿Cual es la desventaja de ellas?
1. ¿Cual es la diferencia entre un objeto "host" y un objeto "nativo"?](#9) http://stackoverflow.com/questions/7614317/what-is-the-difference-between-native-objects-and-h
1. ¿En qué difieren las siguientes expresiones `function Hola() {}`, `var hola = new Hola()` y `var hola = Hola()`?
1. ¿En que se diferencias `Function.call()` y `Function.apply()`?
1. ¿Explícame `Function.prototype.bind` ?
1. ¿Cuál es la diferencia entre deteccion de features, inferencia de features y usar el string UA?
1. ¿Explícame AJAX?
1. ¿Qué ventajas y desventajas tiene el usar AJAX?
1. ¿Qué es JSONP?
1. ¿Explícame Hoisting?
1. ¿Cuales son las ventajas/desventajas de usar clases en ES6?
1. ¿Describe el 'event bubbling'?
1. ¿Cuál es la diferencia entre `==` y `===`?
1. Has que esto funcione:
    ```javascript
    [2,3,5,6].replicate()   // [2,3,5,6,2,3,5,6]
    [2,3,5,6].replicate(1)  // [2,3,5,6,2,3,5,6]
    [2,3,5,6].replicate(2)  // [2,3,5,6,2,3,5,6,2,3,5,6]
    ```
1. ¿Tienes un ejemplo de una expresión ternaria? ¿Porqué "ternaria"?
1. ¿Porqué es generalmente una buena idea no agregar cosas a scope global de un sitio web? (window) ?
1. ¿Porqué usarías el evento "load"? ¿Ventajas y desventajas? ¿Alternativas?
1. ¿Cómo harías una SPA (Single page application) "SEO Friendly"?
1. ¿Qué ventajas tiene el usar promesas?
1. Además de callbacks. ¿Qué otras maneras existen de trabajar con asincronía en JavaScript?
1. Teniendo lo siguiente:
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

1. ¿Porqué debería usar o no usar un lenguaje que transpile o compile a JavaScript? ¿Qué ventajas o desventajas existen?
1. ¿Como debugueas tu código de JavaScript?
1. ¿Cómo puedo iterar sobre un objeto y un array?
1. ¿Conoces como funciona `[].map()`? (Explicar como funciona `[].map()`)
  - Crea una función que realice lo mismo pero para objetos. Que reciba como 1er parámetroun objeto, y como 2do parametro una función que se ejecutará sobre cada par llave/valor.
    - Cambia la función para que pueda recibir como primer parámetro un Array o un Objeto
  - Puedes replicar `[].map()` en `{}.map()`?
1. Explícame la diferencia entre `let`, `const` y `var`.
1. Explícame la diferencia entre síncrono y asíncrono.
1. ¿Qué es event loop?
  1. ¿Cual es la diferencia entre `call stack` y `task queue`?
1. Además de "porque se ve más bonito" ¿Por que debería usar arrow functions `() => {}`?
1. Qué diferencia existe en el uso de `hola` entre `function hola(){}`, `var hola = function(){}` y `var hola = ()=>{}`
1. ¿Qué es y Porqué usar o no Babel?
1. ¿Que proposals de JavaScript es la que más te gustaría/interesa que sea aprobada?
