Puesto: Front End Engineer.

### Preguntas
1. [ ] En una matriz de NxN, con M puntos puestos en la matriz al azar, encontrar todos los puntos que pasan por una línea cualquiera.

1. [ ] Si tengo las siguientes funciones:

```javascript
function buscarEnFacebook(texto, callback) {
  /* Hace algunas cosas y las guarda en "result" */
  if (result.error) {
    callback(error, result.error)
  } else {
    callback(null, result.data);
  }
}
function buscarEnGithub(texto, callback) {
  /* Hace algunas cosas y las guarda en "result" */
  if (result.error) {
    callback(error, result.error)
  } else {
    callback(null, result.data);
  }
}
```

  - ¿Qué debería hacer para usar la funcionalidad con promesas y no callbacks?
  - ¿Puedes replicar la siguiente API?
    ```javascript
    buscador('hola')
    .facebook()
    .github()
    .then((data) => {
      // data[0] = data de Facebook
      // data[1] = data de GitHub
    })
    .catch(error => {
      // error[0] = error de Facebook
      // error[1] de GitHub
    })
    ```
  - A la solución anterior
    - ¿Cómo podrías mejorar la API de la función?
    - ¿Cómo podrías agregarle otra búsqueda?
    - ¿Cómo solucionas el problema de si una API entrega un error, mientras las otras devuelven data?

1. ¿Qué puntos débiles mejorarías de JavaScript?
