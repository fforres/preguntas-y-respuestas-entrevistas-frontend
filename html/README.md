# Preguntas para entrevista de frontend
## HTML
### Preguntas
1. [¿Qué hace un `doctype`  (`<!DOCTYPE html>`)?](#1)
1. [¿Qué elementos componen HTML5?](#2)
1. [¿Para que sirven los atributos `data-`?](#4)
1. [¿Cuál es la diferencia entre `cookie` `localStorage`, `sessionStorage` e `indexedDB`?](#5)
1. [¿Qué diferencias existen entre `<script>`, `<script async>` y `<script defer>`?](#6)
1. [¿Puedo poner un tag `<link>` dentro del body?¿Porqué no es recomendado?](#7)
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


### Respuestas
- #### [¿Qué hace un `doctype`  (`<!DOCTYPE html>`)?](#1)
  <div id="#1" />
  Es una declaración al comienzo de un documento HTML (previo al tag `<html>`), es una instrución que le deja saber al navegador en que version de HTML está este documento para interpretarlo correctamente.
  Definir `<!Doctype html>` le dice al navegador que tiene que parsear el html basándose en el estandar HTML5.
  En el caso de navegadores más viejos, interpretaran el html en un modo "compatible con html5" pero ignorarán las features que no soporten.
  Es mucho más simple que las definiciones de doctype anteriores.
  `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"
  "http://www.w3.org/TR/html4/strict.dtd">
  `



- #### [¿Qué elemento componen "HTML5"?](#2)
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



- #### [¿Para que sirven los atributos `data-`?](#4)
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

- #### [¿Cuál es la diferencia una `cookie` `localStorage` y `sessionStorage`?](#5)
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

    Una sesión dura hasta que el navegador es cerrado.

    La data sobrevive a recargas de página.

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

    ~5MB de storage por dominio.

    El acceso a localStorage diferencia por protocolo, si bien es posible compartir la data por dominio, la data queda aislada entre dominios iguales que usen `https` y `http`.




- #### [¿Qué diferencias existen entre `<script>`, `<script async>` y `<script defer>`?](#6)
  <div id="#6" />
  - ** script ** -> Descarga el file y ejecuta el file, pero tnto como la descarga como ejecucuión se desarrollan secuencialmente, por lo tanto detienen el parseo del HTML.

  - ** script async ** -> Descarga el file paralelamente a la descarga/parseo del resto del documento/assets, pero al momento de ejecturalo, detiene el parseo del HTML.

  - ** script defer ** -> Descarga el file paralelamente a la descarga/parseo del resto del documento/assets, pero pero espera hasta que todo el HTML esté parseado antes de ejectuar el script




- #### [¿Puedo poner un tag `<link>` dentro del body? ¿Porqué no es recomendado?](#7)
  <div id="#7" />
  - Si. No es recomendado, aunque posible.
  - Ejemplo de un proceso de descarga de un file html, con un css una imagen y un archivo JS
    - Descarga el "html"
    - Se parsea el HTML y ve que hay un archivo css, un archivo JS y una imagen
    - Se inicia la descarga de la imagen
    - Browser decide que no puede mostrar la página sin antes descargar el CSS y JS
      - Esta decisión se toma porque ambos archivos podrían alterar la visualizacion del DOM causando reflow o Repaint si el css tuviese un `display: none` o el JS un `Node.remove()`, por ejemplo.
    - Descarga por orden de aparicion (Css o JS)
    - Al descargar el CSS, lo lee, parsea, y se asegura que no llame nada más (un `@import` o `background:url('./imagen.jpg')`)
    - Al descargar el JS, lo lee, interpreta y ejecuta.
    - El browser decide que ahora si puede mostrar el DOM, por lo que empieza a pintar y estilar el DOM

  En este ejemplo, en el caso de tener un segundo `<link />` dentro del body, el proceso se ejecuta normalmente hasta que se parsea el DOM, dentro del body se encuentra con el `<link />`, y se detiene el parseo y pintado del DOM para descargar, parsear el CSS.

  Luego de eso y luego resumir el trabajo con el DOM y aplicar estilos de ser necesario.

  + Mas info sobre el [Critical Rendering Path acá](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/) y [acá](https://varvy.com/pagespeed/critical-render-path.html)




- #### [¿Donde es recomendado poner los tag `<script/>` después o antes del body? ¿Existen excepciones?](#8)
  <div id="#8" />
  - Depende mucho del contenido y acciones que ejecutarán dichos scripts.
  - Es más una "buena practica legacy" hoy en dia, se colocaban posterior al body para priorizar el mostrar contenido estilado y no detener la ejecución del sitio mientras se descargaba el css.
  - Actualment existen los atributos `async` o `defer`, que nos ayudan a definir descargas, parseos y ejecución diferidos.

- #### [¿Que es el Rendering Progresivo?](#9)
  <div id="#9" />
  - Un conjunto de técnicas y decisiones tomadas y aplicadas a fin de priorizar mostrar de una parte del contenido web lo mas rapidamente posible (El contenido de una noticia, el landing en un sitio web), y despriorizar la carga de otras secciones (Footer, banners, side-menus, etc).





- #### [¿Qué son y como afectan al performance el `Reflow` y `Paint`/`RePaint` ?](#10)
  <div id="#10" />
  - `RePaint` es el nombre que se le da al proceso que ejecuta el navegador cuando realiza cambios visuales a un elemento, pero no cambia su `layout`. (Color de fondo, visibilidad, outline)

  - `Reflow` es el proceso que ejecuta el navegador cuando los cambios que realiza a un elemento, cambian su layout (posicion, tamaño, etc) que obligan a recalcular y posiblemente reposicionar otros elementos en el documento.

  Ambos procesos son críticos a la hora de analizar y optimizar la performance, donde `ReFlow` afecta de manera mucho mayor.

  - Al mover un elemento que cause `ReFlow`, es necesario recalcular ** todos ** los otros elementos del DOM que podrían verse afectados por este cambio.

  - `RePaint` necesita verificar la visibilidad de todos los otros nodos y como estos afectan a la visibilidad de el/los nodos iniciales.
    - Ejemplo:

      El cambiar el color de fondo de un `<div id="#a" />` sobre el que hay un `<div id="b">` con una opacidad `0.5`, fuerza a recalcular el color de fondo y los efectos que tiene el `<div id="b">` sobre el A



- #### [¿Qué estructura tiene el `DOM`?](#11)
  <div id="#11" />
  -




- #### [¿Qué diferencia existe entre `DOM` y `HTML`?](#12)
  <div id="#12" />
  -




- #### [¿Porqué usar tags como `<Section>` o `<Article>` pudiendo usar `<div />`?](#13)
  <div id="#13" />
  -




- #### [Si tengo 3 tags estilados exactamente iguales (`<button />`, `<a />` y `<div />`) ¿Qué debería elegir para interactuar con un usuario y porqué?](#14)
  <div id="#14" />
  -




- #### [¿Cómo puedes entregar una pagina con contenido en varios lenguajes?](#15)
  <div id="#15" />
  -




- #### [¿Qué cosas debería tener en consideraración para tener una página con contenido en varios lenguajes?](#16)
  <div id="#16" />
  -




- #### [¿Qué es un meta tag?](#17)
  <div id="#17" />
  -
