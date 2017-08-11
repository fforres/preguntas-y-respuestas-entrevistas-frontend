### Pregunta 1

1. Dada las siguientes funciones, ¿podrías decirme cuál es el resultado de las últimas 3 líneas?

  ```javascript
    var Foo = function( a ) {+
      var baz = function() {
        return a;
      };
      this.baz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return a;
      }
    };

    var f = new Foo( 7 );
    f.bar(); // bar function is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```

  ##### Respuesta

  ```javascript
  f.bar(); // bar function is not defined
  f.baz(); // 7
  f.biz(); // a undefined
  ```

2. ¿Podrías modificar el código de f.bar() para que retorne `7`?
  
  ##### Respuesta
  Solo necesitas agregar `baz` como una función del `this` en el constructor de `Foo`

  ```javascript
    var Foo = function( a ) {+
      this.bar = function() {
        return a;
      };
      this.baz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return a;
      }
    };

    var f = new Foo( 7 );
    f.bar(); // bar function is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```

3. ¿Podrías modificar el código para que `f.biz()` también retorne `7`?

  ##### Respuesta
  Necesitas agregar `a` como un parámetro del `this` en el constructor de `Foo`.
  De esa manera puedes acceder `a` desde la funcion `biz()`, utilizando `this.a`.

  ```javascript
    var Foo = function( a ) {
      this.a = a; // Add a reference to A
      this.bar = function() {
        return a;
      };
      this.baz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return this.a;
      }
    };

    var f = new Foo( 7 );
    f.bar(); // bar function is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```

4. Imagina que por alguna razón (Aliens 👽 probablemente), no podemos asignar la variable `a` a nada, por lo que realizar `this.a = a` no es posible.
¿Cómo podríamos obtener el mismo resultado que en la pregunta anterior? (Que `f.biz()` retorne `7`);

  ```javascript
    var Foo = function( a ) {+
      // this.a = a;
      this.bar = function() {
        return a;
      }
      this.baz = function() {
        return a;
      };
      this._biz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return this._biz();
      }
    };

    var f = new Foo( 7 );
    f.bar(); // here bar function is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```


### Pregunta 2

En tu perfil de LinkedIn la gente puede validar tus habilidades. Dado el siguiente array de validaciones:

```javascript
var endorsements = [
  { skill: 'css', user: 'Bill' },
  { skill: 'javascript', user: 'Chad' },
  { skill: 'javascript', user: 'Bill' },
  { skill: 'css', user: 'Sue' },
  { skill: 'javascript', user: 'Sue' },
  { skill: 'html', user: 'Sue' }
];
```

¿Cómo podrías ordenarlo de la siguiente forma?:

```javascript
[
  { skill: 'css', users: [ 'Bill', 'Sue', 'Sue' ], count: 2 },
  { skill: 'javascript', users: [ 'Chad', 'Bill', 'Sue' ], count: 3 },
  { skill: 'html', users: [ 'Sue' ], count: 1 }
]
```

  ##### Respuesta
  ```javascript
  const sortEndorsedArrays = (endorsements) => {
    const ob = {};
    endorsements.forEach(el => {
      if(!ob[el.skill]) {
        ob[el.skill] = {
          skill: el.skill,
          users: [],
          count: 0,
        }
      }
      ob[el.skill].user.push(el.user);
      ob[el.skill].count += 1;
    })

    let modifiedArray = [];
    Object.keys(ob).forEach(el => {
      modifiedArray.push(ob[el])
    })
    return modifiedArray;
  }
  ```

  > Bro tip: 
  > Un objeto A puede ser asignado en alguna parte a otro objeto B (o un array). Esa nueva asignación es solo una referencia al objeto A, así que podríamos cambiar el código para que haga uso de esto.
  > Y salvarnos toooooda una iteración! 💪

  ```javascript
  const sortEndorsedArrays = (endorsements) => {
    const ob = {};
    const modifiedArray = [];
    endorsements.forEach(el => {
      if(!ob[el.skill]) {
        /* It happen from here: ----> */
        const endorsementObject = {
          skill: el.skill,
          users: [],
          count: 0,
        }
        ob[el.skill] = endorsementObject;
        modifiedArray.push(endorsementObject);
        /*
        To here
        <-------
        */
      }
      ob[el.skill].user.push(el.user);
      ob[el.skill].count += 1;
    })
    return modifiedArray;
  }
  ```
  
  ##### Explicación

  Creamos el mismo `endorsementObject`, bastante parecido a la versión anterior, salvo que:
  
  1. Guardamos `endorsementObject` en el objeto y en el array.
  2. Esto nos sirve para usar las ventajas de un objeto con, por ejemplo, tiempos de búsqueda (Si usamos una llave única como `ob[el.skill]`)
  3. Como al mismo tiempo el mismo objeto lo ponemos en un array, asi la estructura final que buscábamos se completa a medida que iteramos sobre el array `endorsements`.
  4. Esto sucede porque como en ambos lados (`ob` y `modifiedArray`) el mismo objeto apunta a la misma referencia, entonces al modificarlo en el objeto `ob`, modificamos la referencia, por lo que se aprecian los cambios también en `modifiedArray`

  Lo que si, puede usar un poco más de memoria, pero la ventaja es que nos ahorramos toda una iteración en el array final. 
  Depende mucho del contexto en el que se use el problema.
  (Ordenar 10M de elementos en un smartwatch con poca memoria, no es lo mismo que en un server).

  -----


#### Pregunta 3
¿Puedes replicar el markup (HTML) de lo siguiente?
  ![](./user_line.png)

> Lo que nos interesa más en esta ocasión son los rows por usuario, no tanto el header y el body, o el padding del contenedor, etc.
> Queremos que el template para un solo elemento, podemos asumir que haremos un .map sobre el array y reutilizaremos el template para cada iteración.

Es una pregunta abierta, no tiene una respuesta válida.
Es mucho más facil usar un approach con flexbox, pero también puedes hacerlo de otras maneras (`position absolute`, `float left y right`, etc)
Comentar eso es buena idea :)

Como pregunta abierta, es siempre útil preguntar mucho para acotar el problema, aclarar cosas, y demostrar tu capacidad de análisis pre-código.

Por ejemplo, podrías preguntar lo siguiente:

- ¿Hay alguna accion que esto tenga que realizar? 
Si el botón de cerrado (`x`) tiene que eliminar la fila completa, o un efecto on-hover, etc.
¿La idea es crear CSS + HTML solamente, o JS también?
¿Debe ser responsivo?
¿Hay alguna limitación? (¿Debe ser mobile?)

###### Tips
  - Recuerda pensar en accesibilidad.
    - Usa `li` para los items de una lista (y no `divs`)
    - Usa botones para las acciones por sobre `div` o `a`.

```css
  .row {
    display: flex;
    justify-content: space-between;
    padding: 0.5em;
  }
  .image {
    width: 100px;
  }
  .rowBody {
    flex-grow:2;
    display: flex;
    flex-direction: column;
  }
  .close {
    align-self: flex-start;
    width: 40px;
  }
  .description .profileLink {
    text-decoration: none;
  }
  .rowBody .description .name {
    /* bold */
  }
```

```html
  <li class="row">
    <div class="image">
      <img />
    </div>
    <div class="rowBody">
      <div class="description">
        <a href="{url}" class="profileLink"><span class="name">Jack Smith</span></a>
        <span>kaskjlasjlas</span>
      </div>
      <button class="connectButton"> +Connect </button>
    </div>
    <button class="close">
      x
    </button>
  </li>
```
