---
ID: 2500
post_title: Ventajas de utilizar Node.js
author: JuanMa Garrido
post_excerpt: |
  <div>
  <h3>
  <strong>¿Qué es Node.js?</strong>
  </h3>
  </div>
  <p>
  <a href=
  "http://es.wikipedia.org/wiki/Node.js"><em>Node.js</em></a>&nbsp;<em>es
  un <strong>entorno JavaScript de lado de servidor</strong></em>
  que utiliza un modelo asíncrono y dirigido por eventos.&nbsp;
  </p>
  <p>
  Igual que se utiliza Ruby o Python en el servidor, ahora también
  se puede utilizar Javascript.&nbsp;
  </p>
  <p>
  Node.js <strong><em>usa el motor de JavaScript&nbsp;<a href=
  "http://code.google.com/p/v8/">V8</a>&nbsp;de
  Google</em></strong>: una maquina virtual (VM) tremendamente
  rápida y de gran calidad escrita por gente como <a href=
  "http://en.wikipedia.org/wiki/Lars_Bak_(computer_programmer)">Lars
  Bak</a>, uno de los mejores ingenieros del mundo especializados
  en VMs.&nbsp;
  </p>
  <div>
  <h3>
  ¿Cuándo es aconsejable utilizar Node.js?
  </h3>
  </div>
  <p>
  Basicamente Node es adecuado cuando necesitas hacer muchas cosas
  al mismo tiempo, sobre todo muchas operaciones I/O (acceso a
  ficheros, bases de datos,...) a la vez.
  </p>
  <p>
  Y <em><strong>es especialmente bueno para aplicaciones
  realtime</strong></em>, que necesitan mantener una conexión
  persistente entre el browser y el servidor (juegos online, chats,
  herramientas de colaboración, etc ).&nbsp;
  </p>
  <p>
  Si lo que necesitas es trabajo intensivo de CPU (codificacion de
  video, manipulación de imagen, etc) utilizar Node no supone
  ninguna ventaja
  </p>
  <h3>
  Más ventajas de utilizar Node.js
  </h3>
  <ol>
  <li style="margin-top: 15px;">Con Node puedes utilizar
  <em>javascript como lenguaje de scripting</em> en tu consola
  (como bash, perl, etc.)
  </li>
  <li style="margin-top: 15px;">Está <em>basado en eventos</em>,
  asi que toda la filosofia asíncrona que ya utiizamos con AJAX en
  el cliente la podemos pasar al servidor.
  </li>
  <li style="margin-top: 15px;">Te permite utilizar el <em>mismo
  lenguaje (javascript) tanto en el cliente como en el
  servidor</em>
  </li>
  <li style="margin-top: 15px;">
  <em>Muy buena gestion de paquetes</em> gracias a NPM (si
  quieres hacer algo, probablemente &nbsp;exista una
  librería/paquete que ya lo hace)
  </li>
  <li style="margin-top: 15px;">Detras de Node hay una
  <em>Comunidad</em> enorme documentando, haciendo turoriales y
  creando nuevos modulos.
  </li>
  <li style="margin-top: 15px;">Nos permite hacer en el servidor
  todo lo que necesitamos (acceso a ficheros, a bases de datos,
  conexiones de clientes.. )
  </li>
  </ol>
  <div>
  &nbsp;
  </div>
  <h2>
  Enlaces y mas:
  </h2>
  <ol>
  <li>
  <a href=
  "http://stackoverflow.com/questions/5062614/how-to-decide-when-to-use-nodejs">
  http://stackoverflow.com/questions/5062614/how-to-decide-when-to-use-nodejs</a>
  </li>
  <li>
  <a href=
  "http://codeofrob.com/entries/5-reasons-to-give-node.js-some-love.html">
  http://codeofrob.com/entries/5-reasons-to-give-node.js-some-love.html</a>
  </li>
  <li>
  <a href=
  "http://www.quora.com/Node-js/Why-should-I-use-Node-js">http://www.quora.com/Node-js/Why-should-I-use-Node-js</a>
  </li>
  <li>
  <a href=
  "http://debuggable.com/posts/understanding-node-js:4bd98440-45e4-4a9a-8ef7-0f7ecbdd56cb">
  http://debuggable.com/posts/understanding-node-js</a>
  </li>
  <li>
  <a href=
  http://blog.mixu.net/2011/02/01/understanding-the-node-js-event-loop/
  target=
  "_blank">http://blog.mixu.net/2011/02/01/understanding-the-node-js-event-loop/</a>
  </li>
  </ol>
  <p>
  &nbsp;
  </p>
  <p>
  ¿Que te ha parecido el articulo?¿Alguna ventaja más de utilizar
  Node.js que quieras añadir? ¿Alguna desventaja? Esperamos
  vuestros comentarios
  </p>
  <div>
  &nbsp;
  </div>
layout: post
permalink: >
  https://pixelovers.com/ventajas-utilizar-nodejs-1953900/
published: true
post_date: 2012-05-20 09:51:00
---
<img style="display: block; margin-left: auto; margin-right: auto;" title="" src="http://www.bonillaware.com/app/uploads/sites/7/nodejs.jpg" alt=" TAGS:" />

Hace unos días hicimos, <a href="https://twitter.com/carlosvillu" target="_blank">Carlos Villuendas</a> y yo, un workshop interno en <a href="http://www.softonic.com">Softonic.com</a> sobre Node.js.

En este workshop explicamos <a href="http://nodejs.org/" target="_blank">qué es Node.js</a>, las ventajas de la <a href="http://shinetech.com/thoughts/thought-articles/139-asynchronous-code-design-with-nodejs-" target="_blank">programacion asíncrona en el servidor</a>, la gestion de paquetes con <a href="http://www.nodehispano.com/2012/04/una-introduccion-a-npm-nodejs/" target="_blank">npm</a> y cómo funcionan el <a href="http://fernetjs.com/2012/02/modulos-en-nodejs/" target="_blank">require</a>, <a href="http://www.hacksparrow.com/node-js-exports-vs-module-exports.html" target="_blank">module.exports</a> y los <a href="http://nodejs-es.github.com/api/events.html">listeners</a>.

<!--more-->

En un descanso que hicimos, pedí un poco de feedback sobre el workshop y el amigo <a href="http://twitter.com/#!/tonipinel" target="_blank">Toni</a>, como siempre buscando la aplicación en el mundo real, me dijo:

<blockquote><em>El workshop me está molando, pero no termino de ver la aplicación practica de todo esto. Es decir ¿que ventajas tiene utilizar Node.js frente a PHP por ejemplo? ¿Cuándo es adecuado utilizar Node.js?</em></blockquote>

Buena pregunta, no?

Vamos a ver si somos capaces de responderla en este post...

<!-- pagebreak -->

<div>
<h3><strong>¿Qué es Node.js?</strong></h3>
</div>

<a href="http://es.wikipedia.org/wiki/Node.js"><em>Node.js</em></a> <em>es un <strong>entorno JavaScript de lado de servidor</strong></em> que utiliza un modelo asíncrono y dirigido por eventos.

Igual que se utiliza Ruby o Python en el servidor, ahora también se puede utilizar Javascript.

Node.js <strong><em>usa el motor de JavaScript <a href="http://code.google.com/p/v8/">V8</a> de Google</em></strong>: una maquina virtual (VM) tremendamente rápida y de gran calidad escrita por gente como <a href="http://en.wikipedia.org/wiki/Lars_Bak_(computer_programmer)">Lars Bak</a>, uno de los mejores ingenieros del mundo especializados en VMs.

<div>
<h3>¿Cuándo es aconsejable utilizar Node.js?</h3>
</div>

Basicamente Node es adecuado cuando necesitas hacer muchas cosas al mismo tiempo, sobre todo muchas operaciones I/O (acceso a ficheros, bases de datos,...) a la vez.

Y <strong><em>es especialmente bueno para aplicaciones realtime</em></strong>, que necesitan mantener una conexión persistente entre el browser y el servidor (juegos online, chats, herramientas de colaboración, etc ).

Si lo que necesitas es trabajo intensivo de CPU (codificacion de video, manipulación de imagen, etc) utilizar Node no supone ninguna ventaja

<h3>Más ventajas de utilizar Node.js</h3>

&nbsp;

<ul>
    <li style="margin-top: 15px;">Con Node puedes utilizar <em>javascript como lenguaje de scripting</em> en tu consola (como bash, perl, etc.)</li>
    <li style="margin-top: 15px;">Está <em>basado en eventos</em>, asi que toda la filosofia asíncrona que ya utiizamos con AJAX en el cliente la podemos pasar al servidor.</li>
    <li style="margin-top: 15px;">Te permite utilizar el <em>mismo lenguaje (javascript) tanto en el cliente como en el servidor</em></li>
    <li style="margin-top: 15px;"><em>Muy buena gestion de paquetes</em> gracias a NPM (si quieres hacer algo, probablemente  exista una librería/paquete que ya lo hace)</li>
    <li style="margin-top: 15px;">Detras de Node hay una <em>Comunidad</em> enorme documentando, haciendo turoriales y creando nuevos modulos.</li>
    <li style="margin-top: 15px;">Nos permite hacer en el servidor todo lo que necesitamos (acceso a ficheros, a bases de datos, conexiones de clientes.. )</li>
</ul>

&nbsp;

<div></div>

<h2>Enlaces y mas:</h2>

<ol>
    <li><a href="http://stackoverflow.com/questions/5062614/how-to-decide-when-to-use-nodejs"> http://stackoverflow.com/questions/5062614/how-to-decide-when-to-use-nodejs</a></li>
    <li><a href="http://codeofrob.com/entries/5-reasons-to-give-node.js-some-love.html"> http://codeofrob.com/entries/5-reasons-to-give-node.js-some-love.html</a></li>
    <li><a href="http://www.quora.com/Node-js/Why-should-I-use-Node-js">http://www.quora.com/Node-js/Why-should-I-use-Node-js</a></li>
    <li><a href="http://debuggable.com/posts/understanding-node-js:4bd98440-45e4-4a9a-8ef7-0f7ecbdd56cb"> http://debuggable.com/posts/understanding-node-js</a></li>
    <li><a href="http://blog.mixu.net/2011/02/01/understanding-the-node-js-event-loop/" target="_blank">http://blog.mixu.net/2011/02/01/understanding-the-node-js-event-loop/</a></li>
</ol>

&nbsp;

¿Que te ha parecido el articulo?¿Alguna ventaja más de utilizar Node.js que quieras añadir? ¿Alguna desventaja? Esperamos vuestros comentarios

<div></div>