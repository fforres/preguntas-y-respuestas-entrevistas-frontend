> `TickTock`, un ejercicio interesante y facilmente "complicable" a medida que avanza el mismo.

> Es necesario realizar este ejercicio on-site y on-whiteboard. (Para poder ver como se desenvuelve el entrevistado).

> Si bien el ejercicio tiene un poco de trivia, por lo que es facil que el entrevistado se incomode, la idea es hacerlo sentir cómodo e intentar eliminar el stress propio de la entrevista (Acentuado por trivia) para que realice preguntas comente el ejercicio y las dudas que tenga.



## TickTock
Puedes crear una función `ticktock` que por cada ves que se ejecute. imprima en consola alternadamente `tick` y luego `tock`

```javascript
ticktock()
// 'tick'
ticktock()
// 'tock'
ticktock()
// 'tick'
ticktock()
// 'tock'
... (y así hasta el infinito!)

```

#### Parte 1
```javascript
let auxiliar = true;
let ticktock = () => {
  if (auxiliar) {
    console.log('tick');
  } else {
    console.log('tock');
  }
  auxiliar = !auxiliar;
}
```

#### Parte 2
Puedes realizar lo mismo, pero sin estructuras de control `if` (normales o ternarios),  `for`, `whiles` (do-whiles)
```javascript
let a = 0;
let tick = ['tick','tock']
let ticktock = () => {
  console.log(tick[0+a]);
  a = !a;
}
```

#### Parte 3
Pongámosnos en el caso de que ahora "tick" y "tock", son 2 funciones que manejan otros 2 equipos.
La función `tick()`, devuelve `'tick'` y La función `tock()`, devuelve `'tock'`.
Podrías modificar tu código para trabajar con esas funciones y no con los strings 'tick' y 'tock'
```javascript
let a = 0;
var tick = () => {
  console.log('tick');
}
var tock = () => {
  console.log('tock');
}
const funcs = [tick, tock]
let ticktock = () => {
  funcs[0+a]();
  a = !a;
}
```

#### Parte 4
Asume que tienes un PM complicado para trabajar, y que es alérgico a los arrays.
Como harías el mismo ejercicio anterior ejercicio si no pudieras usar arrays?

```javascript
/*Opcion 1, "usando nuevas funciones + eval". No es un buena practica, pero soluciona el problema*/
let a = 0;
var tick = () => { console.log('tick'); }
var tock = () => { console.log('tock'); }
var tick0 = () => { tick() }
var tick1 = () => { tock() }
let ticktock = () => {
  eval(`tick${0+a}()`)
  a = !a;
}
/*
  Opcion 2, usando "objetos y no de array".
  Aquí puedes decirle que tampoco puede usar objetos y pasar a la posible 'Opcion   3'*/
let a = 0;
var tick = () => {
  console.log('tick');
}
var tock = () => {
  console.log('tock');
}
const funcs = { 0: tick, 1:tock }
let ticktock = () => {
  funcs[0+a]();
  a = !a;
}


/*
Opcion 3
Intercambiando en una variable `funct`, referencias a las funciones `tick` y `tock` con cada ejecución y llamando a 'funct' en la funcion `ticktock`
*/
const funct = tick;
const tick = () => {
  console.log('tick')
  funct = tock;
}
const tock = () => {
  console.log('tock');
  funct = tick;
}

const ticktock = () => {
  funct();
}
```
