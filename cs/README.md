# Preguntas para entrevista de frontend
## Coding / CS


### Preguntas

1. [¿Cuál es el valor de `bar`?](#1)
  ```javascript
  var bar = 10 + '20';
  ```

1. [¿Como harías para crear una función `add` que cumpla con lo siguiente?](#2)
  ```javascript
  add(2, 5) // retorna: 7
  add(2)(5) // retorna: 7
  ```

1. [¿Que retorna lo siguiente?](#3)
  ```javascript
  "Me gusta JavaScript".split('').reverse().join('');
  ```

1. [¿Que retorna lo siguiente?](#4)
  ```javascript
  "me gusta JavaScript".split(' ').map(function(el) {
    return el.split('').reverse().join('');
  }).join(' ');
  ```

1. [¿Que valor toma `foo` luego de lo siguiente?](#5)
  ```javascript
    (window.foo || (window.foo = "bar"))
  ```

1. [¿Qué ocurre al ejecutar lo siguiente?](#6)
  ```javascript
  var foo = "Hello";
  (function() {
    var bar = " World";
    alert(foo + bar);
  })();
  alert(foo + bar);
  ```

1. [En el siguiente código: ¿Que imprimirán las lineas `console.log(foo.length);`?](#7)
  ```javascript
  var foo = [];
  foo.push(1);
  foo.push(2);
  console.log(foo.length); // ??
  foo[100] = 0;
  console.log(foo.length); // ??
  ```

1. [¿Cuál es el valor de `foo.x`?](#8)
  ```javascript
  var foo = {n: 1};
  foo.x = foo = {n: 2};
  ```

1. [¿Qué imprime el siguiente código?](#9)
  ```javascript
  console.log('one');
  setTimeout(function() {
    console.log('two');
  }, 0);
  console.log('three');
  ```

1. [¿Qué retorna `null === undefined`?](#10)

1. [¿Qué imprime el siguiente código?](#11)
  ```javascript
  console.log('one');
  setTimeout(function() {
    console.log('two');
  }, 0);
  console.log('three');
  ```

1. [Dado el siguiente input:](#12)
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




### Respuestas

- [¿Cuál es el valor de `bar`?](#1)
  <div id="1" />
  ```javascript
  ```


- [¿Como harías para crear una función `add` que cumpla con lo siguiente?](#2)
  <div id="2" />
  ```javascript
  ```


- [¿Que retorna lo siguiente?](#3)
  <div id="3" />
  ```javascript
  ```

- [¿Que retorna lo siguiente?](#4)
  <div id="4" />
  ```javascript
  ```


- [¿Que valor toma `foo` luego de lo siguiente?](#5)
  <div id="5" />
  ```javascript
  ```


- [¿Qué ocurre al ejecutar lo siguiente?](#6)
  <div id="6" />
  ```javascript
  ```


- [En el siguiente código: ¿Que imprimirán las lineas `console.log(foo.length);`?](#7)
  <div id="7" />
  ```javascript
  ```

- [¿Cuál es el valor de `foo.x`?](#8)
  <div id="8" />
  ```javascript
  ```


- [¿Qué imprime el siguiente código?](#9)
  <div id="9" />
  ```javascript
  ```

- [¿Qué retorna `null === undefined`?](#10)
  <div id="10" />
  ```javascript
  ```

- [¿Qué imprime el siguiente código?](#11)
  <div id="11" />
  ```javascript
  ```

- [Dado el siguiente input:](#12)
  ¿Qué retorna lo siguente?
  ```javascript
  ```
