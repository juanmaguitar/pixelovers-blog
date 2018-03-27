---
ID: 2492
post_title: >
  ¿Cómo debemos crear Arrays, Objetos y
  Funciones en Javascript?
author: JuanMa Garrido
post_excerpt: |
  <p>
  Las respuesta nos viene de la mano de Douglas Crockford aquí:<br />
  <a href=
  "http://www.yuiblog.com/blog/2006/11/13/javascript-we-hardly-new-ya/">
  http://www.yuiblog.com/blog/2006/11/13/javascript-we-hardly-new-ya/</a>
  </p>
  <blockquote>
  <p>
  <em>JavaScript is a prototypal language, but it has a new
  operator that tries to make it look sort of like a classical
  language. That tends to confuse programmers, leading to some
  problematic programming patterns.</em>
  </p>
  <p>
  <em>&nbsp;</em><em>You never need to use new Object() in
  JavaScript. Use the object literal {} instead.</em>
  </p>
  <p>
  <em>&nbsp;</em><em>Similarly, don’t use new Array(), use the
  array literal [] instead. Arrays in JavaScript work nothing
  like the arrays in Java, and use of the Java-like syntax will
  confuse you.</em>
  </p>
  <p>
  <em>&nbsp;</em><em>Do not use new Number, new String, or new
  Boolean. These forms produce unnecessary object wrappers. Just
  use simple literals instead.</em><br />
  <em>Do not use new Function to create function values. Use
  function expressions instead.</em>
  </p>
  </blockquote>
  <p>
  En general es mas limpio (más claro) crear estos elementos con la
  notación literal y además:
  </p>
  <ul>
  <li>En el caso de new Number, new String y new Boolean lo que
  creamos&nbsp;son <strong>objetos</strong> contenedores de estos
  datos y no el tipo de dato primitivo (ocupa mas memoria
  innecesaria).
  </li>
  </ul>
  <p>
  Como los métodos del objeto los podremos usar igual (al
  llamarlos, JS convertirá el dato en objeto, llamará al método,
  devolverá el resultado y destruirá el objeto creado) no es
  necesario crear el objeto de primeras para utilizar sus métodos
  </p>
  <ul>
  <li>En el caso de new Function hace un eval del código que le
  pasamos, perdemos el lexical scope y mas cosas que hacen que no
  sea una buena manera de crear una función
  </li>
  </ul>
  <p>
  Es interesante el comentario de <a href=
  "http://www.nczonline.net/">Nicholas C. Zakas</a> en este post:
  </p>
  <blockquote>
  <p>
  <em>I think it’s also important to answer the question, “if I’m
  not supposed to do it, then why am I allowed to?”</em><br />
  <em>In the case of String, Number, Boolean, and Function, these
  constructors are available so that their prototypes can be
  augmented, not so they can be instantiated.</em><br />
  <em>Since these are used to create wrappers on the fly, it’s
  the only way to add new methods to this type of data.</em>
  </p>
  </blockquote>
  <p>
  Es por esto que la herramienta <a href=
  "http://www.jslint.com/">JSLint</a> (una herramienta muy
  recomendable para validar el código) no admite el uso de estas
  funciones constructoras:
  </p>
  <blockquote>
  <p>
  <em><strong>Constructors and new</strong></em>
  </p>
  <p>
  <em>Constructors are functions that are designed to be used
  with the new prefix. The new prefix creates a new object based
  on the function's prototype, and binds that object to the
  function's implied this parameter. If you neglect to use the
  new prefix, no new object will be made and this will be bound
  to the global object. This is a serious mistake.</em><br />
  <em>JSLint enforces the convention that constructor functions
  be given names with initial uppercase. So…</em>
  </p>
  <ul>
  <li>
  <em>JSLint does not expect to see a function invocation with
  an initial uppercase name unless it has the new prefix.</em>
  </li>
  <li>
  <em>JSLint does not expect to see the new prefix used with
  functions whose names do not start with initial uppercase.
  This can be controlled with the newcap option.</em>
  </li>
  <li>
  <em>JSLint does not expect to see the wrapper forms new
  Number, new String, new Boolean.</em>
  </li>
  <li>
  <em>JSLint does not expect to see new Object (use {}
  instead).</em>
  </li>
  <li>
  <em>JSLint does not expect to see new Array (use []
  instead).</em>
  </li>
  </ul>
  </blockquote>
  <p>
  <strong>Conclusion:</strong>
  </p>
  <p>
  Para crear <em>Strings</em>, <em>Numbers</em> o <em>Booleans</em>
  asignamos directamente a nuestra variable el tipo de dato.
  </p>
  <p>
  Para crear <em>Arrays</em>, <em>Objetos</em> o <em>Funciones</em>
  utilizaremos la notacion literal
  </p>
  <p>
  Es decir:
  </p>
  <ul>
  <li>Para crear Arrays utilizaremos --&gt; var myArray = [];
  </li>
  <li>Para crear Objetos utilizaremos --&gt; var myObject = {};
  </li>
  <li>Para crear Funciones utilizaremos --&gt; var myFunction =
  function () {};
  </li>
  <li>Para crear Strings haremos --&gt; var myString = "";
  </li>
  <li>Para crear Numbers haremos --&gt; var myNumber = 0;
  </li>
  <li>Para crear Booleans haremos --&gt; var myBoolean = false;
  </li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/debemos-crear-arrays-objetos-funciones-javascriptr-1203202/
published: true
post_date: 2011-05-15 11:45:00
---
En Javascript existen lo que se llaman las  <a href="https://developer.mozilla.org/en/Core_JavaScript_1.5_Guide/Working_with_Objects#Using_a_Constructor_Function">funciones constructoras</a>. Son funciones que nos permiten crear objetos cuando las llamamos con el operador  <a href="https://developer.mozilla.org/en/JavaScript/Reference/Operators/Special/new">new</a>.

Todos los "tipos de dato" (arrays, funciones, strings...) en Javascript tienen su funcion constructora correspondiente, aunque para crear estos elementos se recomienda utilizar la llamada <em>'notación literal'</em>

<!--more-->Pero... ¿por qué no conviene usar las funciones constructoras…
<ul>
 	<li><code>new Object()</code></li>
 	<li><code>new Array()</code></li>
 	<li><code>new Function()</code></li>
 	<li><code>new Boolean()</code></li>
 	<li><code>new String()</code></li>
 	<li><code>new Number()</code></li>
</ul>
…para crear objetos, arrays, funciones o datos de tipo booleano, string o number?

Las respuesta nos viene de la mano de Douglas Crockford aquí:
<a href="http://www.yuiblog.com/blog/2006/11/13/javascript-we-hardly-new-ya/">
http://www.yuiblog.com/blog/2006/11/13/javascript-we-hardly-new-ya/</a>
<blockquote>
<p style="text-align: left;"><em>JavaScript is a prototypal language, but it has a new operator that tries to make it look sort of like a classical language. That tends to confuse programmers, leading to some problematic programming patterns.</em></p>
<p style="text-align: left;"><em> </em><em>You never need to use <code>new Object()</code> in JavaScript. Use the object literal <code>{}</code> instead.</em></p>
<p style="text-align: left;"><em> </em><em>Similarly, don’t use <code>new Array()</code>, use the array literal <code>[]</code> instead. Arrays in JavaScript work nothing like the arrays in Java, and use of the Java-like syntax will confuse you.</em></p>
<p style="text-align: left;"><em> </em><em>Do not use <code>new Number</code>, <code>new String</code>, or <code>new Boolean</code>. These forms produce unnecessary object wrappers. Just use simple literals instead.</em></p>
<em>Do not use new Function to create function values. Use function expressions instead.</em></blockquote>
En general es mas limpio (más claro) crear estos elementos con la notación literal y además:
<ul>
 	<li>En el caso de <code>new Number</code>, <code>new String</code> y <code>new Boolean</code> lo que creamos son <strong>objetos</strong> contenedores de estos datos y no el tipo de dato primitivo (ocupa mas memoria innecesaria).</li>
</ul>
Como los métodos del objeto los podremos usar igual (al llamarlos, JS convertirá el dato en objeto, llamará al método, devolverá el resultado y destruirá el objeto creado) no es necesario crear el objeto de primeras para utilizar sus métodos
<ul>
 	<li>En el caso de <code>new Function</code> hace un eval del código que le pasamos, perdemos el lexical scope y mas cosas que hacen que no sea una buena manera de crear una función</li>
</ul>
Es interesante el comentario de <a href="http://www.nczonline.net/">Nicholas C. Zakas</a> en este post:
<blockquote><em>I think it’s also important to answer the question, “if I’m not supposed to do it, then why am I allowed to?”</em>

<em>In the case of <code>String</code>, <code>Number</code>, <code>Boolean</code>, and <code>Function</code>, these constructors are available so that their prototypes can be augmented, not so they can be instantiated.</em>

<em>Since these are used to create wrappers on the fly, it’s the only way to add new methods to this type of data.</em></blockquote>
Es por esto que la herramienta <a href="http://www.jslint.com/">JSLint</a> (una herramienta muy recomendable para validar el código) no admite el uso de estas funciones constructoras:
<blockquote><em><strong>Constructors and new</strong></em>

<em>Constructors are functions that are designed to be used with the new prefix. The new prefix creates a new object based on the function\'s prototype, and binds that object to the function\'s implied this parameter. If you neglect to use the new prefix, no new object will be made and this will be bound to the global object. This is a serious mistake.</em>

<em>JSLint enforces the convention that constructor functions be given names with initial uppercase. So…</em>
<ul>
 	<li><em>JSLint does not expect to see a function invocation with an initial uppercase name unless it has the new prefix.</em></li>
 	<li><em>JSLint does not expect to see the new prefix used with functions whose names do not start with initial uppercase.
This can be controlled with the newcap option.</em></li>
 	<li><em>JSLint does not expect to see the wrapper forms <code>new Number</code>, <code>new String</code>, <code>new Boolean</code>.</em></li>
 	<li><em>JSLint does not expect to see <code>new Object</code> (use <code>{}</code> instead).</em></li>
 	<li><em>JSLint does not expect to see <code>new Array</code> (use <code>[]</code> instead).</em></li>
</ul>
</blockquote>
<strong>Conclusion:</strong>

Para crear <em>Strings</em>, <em>Numbers</em> o <em>Booleans </em>asignamos directamente a nuestra variable el tipo de dato.

Para crear <em>Arrays</em>, <em>Objetos</em> o <em>Funciones </em>utilizaremos la notacion literal

Es decir:
<ul>
 	<li>Para crear Arrays utilizaremos --&gt; <code>var myArray = [];</code></li>
 	<li>Para crear Objetos utilizaremos --&gt; <code>var myObject = {};</code></li>
 	<li>Para crear Funciones podemos hacer --&gt; <code>var myFunction =
function () {};</code></li>
 	<li>Para crear Strings haremos --&gt; <code>var myString = "";</code></li>
 	<li>Para crear Numbers haremos --&gt; <code>var myNumber = 0;</code></li>
 	<li>Para crear Booleans haremos --&gt; <code>var myBoolean = false;</code></li>
</ul>