# Preguntas para entrevista de frontend
### HTML
#### Preguntas
1. [¿Qué hace un `doctype`  (`<!DOCTYPE html>`)?](#1)
1. [¿Qué elementos componen HTML5?](#2)
1. [¿Para que sirven los atributos `data-`?](#4)
1. [¿Cuál es la diferencia entre `cookie` `localStorage`, `sessionStorage` e `indexedDB`?](#5)
1. [¿Qué diferencias existen entre `<script>`, `<script async>` y `<script defer>`?](#6)
1. [¿Puedo poner un tag `<link>` dentro del body?](#7)
1. [¿Donde es recomendado poner los tag `<script/>` después o antes del body? ¿Existen excepciones?](#8)
1. [¿Que es el Rendering Progresivo?](#9)
1. [¿Qué son y como afectan al performance el `Reflow` y `Repaint`?](#10)
1. [¿Qué estructura tiene el `DOM`?](#11)
1. [¿Qué diferencia existe entre `DOM` y `HTML`?](#12)
1. [¿Porqué usar tags como `<Section>` o `<Article>` pudiendo usar `<div />`?](#13)
1. [Si tengo 3 tags estilados exactamente iguales (`<button />`, `<a />` y `<div />`) ¿Qué debería elegir para interactuar con un usuario y porqué?](#14)
1. [¿Cómo puedes entregar una pagina con contenido en varios lenguajes?](#15)
1. [¿Qué cosas debería tener en consideraración para tener una página con contenido en varios lenguajes?](#16)
1. [¿Qué es un meta tag?](#17)


#### Respuestas
    1. ##### [¿Qué hace un `doctype`  (`<!DOCTYPE html>`)?](#1)
    <div id="#1" /> Es una declaración al comienzo de un documento HTML (previo al tag `<html>`), es una instrución que le deja saber al navegador en que version de HTML está este documento para interpretarlo correctamente.
Definir `<!Doctype html>` le dice al navegador que tiene que parsear el html basándose en el estandar HTML5.
En el caso de navegadores más viejos, interpretaran el html en un modo "compatible con html5" pero ignorarán las features que no soporten.
Es mucho más simple que las definiciones de doctype anteriores.
`<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"
"http://www.w3.org/TR/html4/strict.dtd">
`

1. ##### [¿Qué elemento componen "HTML5"?](#2)
    <div id="#2" />
      - Semántica - Text Markup más semántico (Mejor accesibilidad y descripción en el contenido web ... y facilidad en el SEO).
    - `<footer>`
    - `<canvas>`
    - `<article>`
    - `<main>`
    - `<nav>`
    - `<aside>`
    - `<dialog>`
    - `<section>`
    - Etc...
    - Nuevos elementos de form
      - `<datalist>`
      - `<keygen>`
      - `<output>`
  - Conectividad (Diferentes métodos de comunicación)
    - WebSockets
    - WebRTC
    - Eventos del Servidor (server-sent events)
  - OffLine Web
    - Caché de aplicacion
    - Web Workers
    - IndexedDB
    - Uso de archivos offline (File API / FileReader)
    - Detección de la conectividad (navigator.onLine)
  - Multimedia e interacción
    - `<Audio>` y `<Video>`
  - Trabájo Gráficos
    - WebGL
    - Canvas
    - SVG
  - JavaScript / INtegraciónes
    - Web Workers
    - History API
    - DragAndDrop
    - RequestAnimationFrame
    - FullScreenAPI
    - PointerLock
  - Acceso al dispositivo
    - Cámara
    - Eventos Touch
    - Orientación del dispositivo
    - Geolocalización
    - Web Bluetooth
    - WebVR
  - CSS3

1. ##### [¿Para que sirven los atributos `data-`?](#4)
  <div id="#4" />
  Es un atributo de HTML, un estándar que permite adjuntar o guardar información extra en un elemento.
  ```html
  <div
    id="unDivCualquiera"
    data-usuario="fforres"
    data-usuario-correo="felipe.torressepulveda@gmail.com" >
  ```

  El acceso está estándarizado, puedes acceder a la data de la siguiente manera:
  ```javascript
    const article = document.getElementById('unDivCualquiera');
    article.dataset.usuario // "fforres"
    article.dataset.usuarioCorreo // "felipe.torressepulveda@gmail.com"
  ```

1. ##### [¿Cuál es la diferencia una `cookie` `localStorage` y `sessionStorage`?](#5)
  <div id="#5" />
  - ** Cookie: **
    Pequeño set de información enviada por un sitio web y almacenado en el navegador de un usuario.
    Se guarda en el disco, por lo que esta data es persistente.
    Es posible guardar y recuperar la data usando JS de la siguiente manera.
    ```javascript
    document.cookie = "username=fforres";
    /*O darle una fecha de expiración*/
    document.cookie = "username=fforres; expires=Thu, 19 Feb 2019 11:59:59 UTC";
    const cookie = document.cookie;
    ```

    Cada llamada a `document.cookie = "(...)"` crea una nueva cookie.
    Las cookies se guardan en texto plano.
    Pueden guardar poca data (4kb)
    Son enviadas en cada Request.


  - ** sessionStorage: **
    La propiedad `sessionStorage` permite acceder al objeto local `Storage`, pero solo durante la sesion del usuario.
    Una sesión dura hasta que el navegador es cerrado. La data sobrevive a recargas de página.
    Una nueva "tab" o "ventana", genera una nueva sesión.
    ```javascript
    sessionStorage.setItem('usuario', 'fforres');
    /* guarda en la llave "usuario" el valor "fforres" */

    const usr = sessionStorage.getItem('usuario');  // usr retorna "fforres"

    sessionStorage.removeItem('usuario') // remueve la data guardada en esa llave

    sessionStorage.clear() //remueve toda la data de la sesión.
    ```
    ~5MB de storage por dominio



  - ** localStorage: **
    La propiedad `localStorage` permite acceder al objeto local `Storage`
    La data no tiene una fecha de expiración y es accesible desde multiples ventanas o tabs del mismo dominio y navegador.
    ```javascript
    const miStorage = localStorage;
    /* myStorage es ahora un objecto Storage */

    miStorage.setItem('usuario', 'fforres');
    /* guarda en la llave "usuario" el valor "fforres" */

    miStorage.usuario  // retorna "fforres"
    ```
    ~5MB de storage por dominio
    El acceso a localStorage diferencia por protocolo, si bien es posible compartir la data por dominio, la data queda aislada entre dominios iguales que usen `https` y `http`

1. ##### [¿Qué diferencias existen entre `<script>`, `<script async>` y `<script defer>`?](#6)
  <div id="#6" />
  -

1. ##### [¿Puedo poner un tag `<link>` dentro del body?](#7)
  <div id="#7" />
  -

1. ##### [¿Donde es recomendado poner los tag `<script/>` después o antes del body? ¿Existen excepciones?](#8)
  <div id="#8" />
  -

1. ##### [¿Que es el Rendering Progresivo?](#9)
  <div id="#9" />
  -

1. ##### [¿Qué son y como afectan al performance el `Reflow` y `Repaint`?](#10)
  <div id="#10" />
  -

1. ##### [¿Qué estructura tiene el `DOM`?](#11)
  <div id="#11" />
  -

1. ##### [¿Qué diferencia existe entre `DOM` y `HTML`?](#12)
  <div id="#12" />
  -

1. ##### [¿Porqué usar tags como `<Section>` o `<Article>` pudiendo usar `<div />`?](#13)
  <div id="#13" />
  -

1. ##### [Si tengo 3 tags estilados exactamente iguales (`<button />`, `<a />` y `<div />`) ¿Qué debería elegir para interactuar con un usuario y porqué?](#14)
  <div id="#14" />
  -

1. ##### [¿Cómo puedes entregar una pagina con contenido en varios lenguajes?](#15)
  <div id="#15" />
  -

1. ##### [¿Qué cosas debería tener en consideraración para tener una página con contenido en varios lenguajes?](#16)
  <div id="#16" />
  -

1. ##### [¿Qué es un meta tag?](#17)
  <div id="#17" />
  -
