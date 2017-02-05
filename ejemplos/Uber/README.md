Puesto: Front End Engineer.
### Preguntas
1. [ ] En una matriz de NxN, con M puntos puestos en la matriz al azar.
Encontrar todos los puntos que pasan por una linea cualquiera.

1. [ ] si tengo las siguientes funciónes:
```javascript
function buscarEnFacebook(texto, callback) {
  /*Hace algunas cosas y las guarda en "result"*/
  if (result.error) {
    callback(error, result.error)
  } else {
    callback(null, result.data);
  }
}
function buscarEnGithub(texto, callback) {
  /*Hace algunas cosas y las guarda en "result"*/
  if (result.error) {
    callback(error, result.error)
  } else {
    callback(null, result.data);
  }
}
```

  - ¿Que debería hacer para usar la funcionalidad con promesas y no callbacks?
  - ¿Puedes replicar la siguiente API?
    ```javascript
    buscador('hola')
    .facebook()
    .guithub()
    .then((data) => {
      // data[0] = data de facebook
      // data[1] = data de github
    })
    .catch(error => {
      // error[0] = error de facebook
      // error[1] de github
    })
    ```
  - A la solución anterior
    - ¿Cómo podrías mejorar la API de la función?
    - ¿Cómo podrías agregarle otra búsqueda?
    - ¿Cómo solucionas el problema de si una API entrega un error, mientras las otras devuelven data?

1. ¿Qué puntos debiles mejorarías de JavaScript?
