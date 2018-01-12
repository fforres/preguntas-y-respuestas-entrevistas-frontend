> `TickTock`, un ejercicio interesante y facilmente "complicable" a medida que avanza el mismo.

> Es necesario realizar este ejercicio on-site y on-whiteboard. (Para poder ver como se desenvuelve el entrevistado).

> Si bien el ejercicio tiene un poco de trivia, por lo que es fácil que el entrevistado se incomode. La idea es hacerlo sentir cómodo e intentar eliminar el estrés propio de la entrevista (acentuado por trivia) para que realice preguntas, comente el ejercicio y las dudas que tenga.


## TickTock
Puedes crear una función `tickTock`, que por cada vez que se ejecute, imprima en consola alternadamente `tick` y luego `tock`

```javascript
tickTock()
// 'tick'
tickTock()
// 'tock'
tickTock()
// 'tick'
tickTock()
// 'tock'
... (y así hasta el infinito)

```

#### Parte 1

```javascript
let auxiliar = true;
let tickTock = () => {
  if (auxiliar) {
    console.log('tick');
  } else {
    console.log('tock');
  }
  auxiliar = !auxiliar;
}
```

#### Parte 2
Realizar lo mismo, pero sin estructuras de control `if` (normales o ternarios), `for` y/o `whiles` (do-whiles)

```javascript
let a = 0;
let tick = ['tick','tock']
let tickTock = () => {
  console.log(tick[0+a]);
  a = !a;
}
```

#### Parte 3
Pongámosnos en el caso de que ahora "tick" y "tock", son 2 funciones que manejan otros 2 equipos. La función `tick()`, devuelve `'tick'` y La función `tock()`, devuelve `'tock'`. 
¿Podrías modificar tu código para trabajar con esas funciones y no con los strings 'tick' y 'tock'?

```javascript
let a = 0;
var tick = () => {
  console.log('tick');
}
var tock = () => {
  console.log('tock');
}
const funcs = [tick, tock]
let tickTock = () => {
  funcs[0+a]();
  a = !a;
}
```

#### Parte 4
Asume que tienes un PM complicado para trabajar, y que es alérgico a los arrays.
¿Cómo harías el mismo ejercicio anterior si no pudieras usar arrays?

```javascript

/* 
  Opción 1: Usando nuevas funciones + eval. No es un buena práctica, pero soluciona el problema 
*/

let a = 0;
var tick = () => { console.log('tick'); }
var tock = () => { console.log('tock'); }
var tick0 = () => { tick() }
var tick1 = () => { tock() }
let tickTock = () => {
  eval(`tick${0+a}()`)
  a = !a;
}
/*
  Opción 2: Usando objetos.
  Aquí puedes decirle que tampoco puede usar objetos y pasar a la posible 'Opcion 3'
*/
let a = 0;
var tick = () => {
  console.log('tick');
}
var tock = () => {
  console.log('tock');
}
const funcs = { 0: tick, 1:tock }
let tickTock = () => {
  funcs[0+a]();
  a = !a;
}

/*
  Opción 3: Aprovechando la coerción de tipos `boolean` a `number`, para transformar valores decimales a caracteres y así poder usar `Function`
*/
let aux = true;
const tick = () => { console.log('tick'); }
const tock = () => { console.log('tock'); }

const tickTock = () => {
  const f = new Function(`t${String.fromCharCode(aux * 6 + 105)}ck()`);
  f();

  aux = !aux;
}
```
