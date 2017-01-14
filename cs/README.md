# Preguntas para entrevista de frontend
## Coding / CS


### Preguntas

1. ¿Cuál es el valor de `bar`?
  ```javascript
  var bar = 10 + '20';
  ```

1.  ¿Como harías para crear una función `add` que cumpla con lo siguiente?
  ```javascript
  add(2, 5) // retorna: 7
  add(2)(5) // retorna: 7
  ```

1.  ¿Que retorna lo siguiente?
  ```javascript
  "Me gusta JavaScript".split('').reverse().join('');
  ```

1. ¿Que retorna lo siguiente?
  ```javascript
  "me gusta JavaScript".split(' ').map(function(el) {
    return el.split('').reverse().join('');
  }).join(' ');
  ```

1. ¿Que valor toma `foo` luego de lo siguiente?
  ```javascript
    (window.foo || (window.foo = "bar"))
  ```

1. ¿Qué ocurre al ejecutar lo siguiente?
  ```javascript
  var foo = "Hello";
  (function() {
    var bar = " World";
    alert(foo + bar);
  })();
  alert(foo + bar);
  ```

1. En el siguiente código: ¿Que imprimirán las lineas `console.log(foo.length);`?
  ```javascript
  var foo = [];
  foo.push(1);
  foo.push(2);
  console.log(foo.length); // ??
  foo[100] = 0;
  console.log(foo.length); // ??
  ```

1. ¿Cuál es el valor de `foo.x`?
  ```javascript
  var foo = {n: 1};
  foo.x = foo = {n: 2};
  ```

1. ¿Qué imprime el siguiente código?
  ```javascript
  console.log('one');
  setTimeout(function() {
    console.log('two');
  }, 0);
  console.log('three');
  ```

1. ¿Qué retorna `null === undefined`?

1. ¿Qué imprime el siguiente código?
  ```javascript
  console.log('one');
  setTimeout(function() {
    console.log('two');
  }, 0);
  console.log('three');
  ```

1. Dado el siguiente input:
  ```javascript
  function ASD() {
    this.text = 'asd';
  }
  ASD.prototype.test = function(cb){
    cb();
    console.log(this);
  }
  ASD.prototype.test2 = function(cb){
    cb.bind(this)();
    console.log(this);
  }
  var asd = new ASD();
  var testFunction = function() {
    console.log(this)
  };
  ```
  ¿Qué retorna lo siguente?
  ```javascript
  asd.test(testFunction)
  asd.test2(testFunction)
  ```
