---
ID: 3209
post_title: 'ECMAScript 3, 5 y 6: Pasado, Presente y Futuro de Javascript'
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/ecmascript-3-5-6-javascript/
published: true
post_date: 2015-05-05 08:05:32
---
Desde que en <a href="https://www.w3.org/community/webed/wiki/A_Short_History_of_JavaScript">1995 apareciera el lenguaje Javascript</a> cada navegador ha implementado su propia "versión" del lenguaje

Para poner un poco de orden en todas estas implementaciones se definió un standard y la European Computer Manufacturers Association (ECMA) lo publica (su primera versión) en 1997 bajo el nombre <a href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%201st%20edition,%20June%201997.pdf">ECMA-262</a>.

<a href="http://es.wikipedia.org/wiki/ECMAScript">ECMAscript</a> para los amigos ;)

<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/FEATURE-IMAGE2.png"><img class="alignnone wp-image-3212 size-full" title="ECMAScript (ES3, ES5 y ES6)" src="http://pixelovers.com/app/uploads/sites/7/2015/05/FEATURE-IMAGE2.png" alt="ECMAScript (ES3, ES5 y ES6)" width="680" height="225" /></a>

&nbsp;

<!--more-->Siendo estrictos, ECMAScript es sólo la especificación en la que se basa (como también se basan <a href="http://en.wikipedia.org/wiki/ActionScript">ActionScript</a> y otros lenguajes) pero a efectos prácticos la podemos considerar cómo la guía oficial de Javascript ya que ahí puedes encontrar la explicación detallada y rigurosa de cómo funcionan internamente muchos elementos Javascript que ya utilizas.

En esta especificación están definidas las bases del lenguaje (operadores, funciones, etc..) y las diferentes implementaciones se basan en esta serie de "definiciones" (aunque luego las amplíen)

ECMAScript ha ido evolucionando con el tiempo y ha dado lugar a la publicación de diferentes versiones de este standard. Las más populares son:

<ul>
    <li>ECMAScript 3 (publicado en 1999)</li>
    <li>ECMAScript 5 (publicado en 2009)</li>
    <li>ECMAScript 6 (se espera su publicación oficial para este año 2015)</li>
</ul>

Las <a href="http://www.ecma-international.org/publications/standards/Ecma-262-arch.htm">diferentes revisiones del Ecma-262</a> y su <a href="http://kangax.github.io/compat-table/es5/">implementacion en los navegadores</a> han ido marcando los desarrollos en Javascript

Esto significa que cada versión de navegador ha dado soporte en mayor o menor grado a estas versiones de ECMAScript. Este soporte es importante ya que nos da una medida de en cuantos navegadores funcionará nuestro código si utilizamos tal o cual objeto, método o propiedad.

Existen <a href="http://kangax.github.io/compat-table/es5/">tablas</a> que podemos utilizar de referencia para tener una visión clara de este soporte de navegadores a las diferentes versiones de ECMAScript

Aunque tambien podemos utilizar <a href="https://github.com/es-shims">shims</a> para dar soporte a navegadores que no soporten la funcionalidad que estemos utilizando

<h2 style="font-size: 4.2rem;">EcmaScript 3 (pasado)</h2>

<a href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%203rd%20edition,%20December%201999.pdf">ECMAScript 3</a> fue lanzado en 1999 y todos los navegadores (<a href="http://www.webdevout.net/browser-support-ecmascript">antiguos</a> y modernos) siguen este standard.

Añade (respecto de los standards anteriores): <code>do-while</code>, expresiones regulares, nuevos métodos de <code>string</code> (<code>concat</code>, <code>match</code>, <code>replace</code>, <code>slice</code> , <code>split</code> con expresiones regulares, etc.), manejo de excepciones y más.

<h2 style="font-size: 4.2rem;">EcmaScript 5 (presente)</h2>

<strong><a href="http://www.ecma-international.org/ecma-262/5.1/">ECMAScript5.1</a></strong> fue lanzado en 2011 y podemos decir que <strong><a href="http://blog.oio.de/2013/04/16/ecmascript-5-the-current-javascript-standard/">es el actual standard de Javascript</a></strong> (2014).

Si miramos las <a href="http://clicky.com/marketshare/global/web-browsers/versions/">estadísticas de uso de navegadores</a> junto con la <a href="http://kangax.github.io/compat-table/es5/">compatibilidad de estos con ES5</a> podemos concluir que: <em>basándonos en ES5 nuestro código funcionará bien en la mayoría de los navegadores utilizados actualmente (2014)</em>.

Si queremos, podemos dar soporte de algunas features de ES5 en navegadores antiguos que no la soporten, utilizando el correspondiente <a href="https://github.com/es-shims/es5-shim">shim</a>

Esta versión <strong>amplia</strong> los anteriores standards <a href="http://www.jayway.com/2011/04/05/what-is-new-in-ecmascript-5/">con algunas mejoras</a>:

<h3><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode"><code>strict mode</code></a></h3>

Muy <a href="http://cjihrig.com/blog/javascripts-strict-mode-and-why-you-should-use-it/">recomendado</a> utilizarlo desde <a href="http://www.nczonline.net/blog/2012/03/13/its-time-to-start-using-javascript-strict-mode/">ya</a>

<pre><code class="javascript">function() {
  "use strict";
}
</code></pre>

<h3>Nuevos métodos <a href="http://ejohn.org/blog/ecmascript-5-objects-and-properties/"><code>Object</code></a></h3>

<pre><code class="javascript">// Creates an object with parent as prototype and properties from donor
Object.create(parent, donor);

// Meta properties of an object
var descriptor = {
  value: "test",
  writable: true, // Can the value be changed?
  enumerable: true, // Will it appear in for-in and Object.keys(object)?
  configurable: true, // Can the property be removed?
  set: function(value) { test = value}, // Getter
  get: function() { return test } // Setter
}

// Methods for manipulation the descriptors
Object.defineProperty(object, property, descriptor)
Object.defineProperties(object, descriptors)
Object.getOwnPropertyDescriptor(object, property)
Object.getPrototypeOf(object)

// Returns an array of enumerable properties
Object.keys(object)
// Returns an array of all properties
Object.getOwnPropertyNames(object)

// Prevents anyone from adding properties to the object, cannot be undone.
Object.preventExtensions(object)
Object.isExtensible(object)

// Prevents anyone from changing, properties or descriptors of the object.
// The values can still be changed
Object.seal(object)
Objcect.isSealed(object)

// Prevents any changes to the object.
Object.freeze(object)
Object.isFrozen(object)
</code></pre>

<h3><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind"><code>Function.prototype.bind()</code></a></h3>

<pre><code class="javascript">var tapir = {
  method: function(name) {
    this.name = name;
  }
};
setTimeout( tapir.method.bind(tapir, "Malayan"), 100 );
</code></pre>

<a href="http://www.smashingmagazine.com/2014/01/23/understanding-javascript-function-prototype-bind/">Aqui </a>tienes más info sobre <code>prototype.bind</code>

<h3><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/Trim"><code>String.prototype.trim()</code></a></h3>

<pre class="lang:js decode:true">&gt;&gt;&gt; var orig = ' foo ';
>&gt;&gt; console.log(orig.trim());
'foo'</pre>

<h3>Nuevos métodos <a href="http://www.jimmycuadra.com/posts/ecmascript-5-array-methods"><code>Array</code></a></h3>

<pre class="lang:js decode:true">// Do all elements satisfy predicate?
Array.prototype.every(predicate)

// Return a new array with the elements that satisfy predicate?
Array.prototype.filter(predicate)

// Call action(element) for each element.
Array.prototype.forEach(action)

// What is the index of the first element that equals value?
Array.prototype.indexOf(value, fromIndex)

// What is the index of the last element that equal value?
Array.prototype.lastIndexOf(value, fromIndex)

// Create a new array by applying unaryFunc to each element
Array.prototype.map(unaryFunc)

// Reduces the elements of the array, by applying binaryFunc
// between the elements
// [a0, a1].reduce(+ , seed) == seed + a0 + a1
Array.prototype.reduce(binaryFunc, seed)

// Is at least one element satisfied by the predicate?
Array.prototype.some(predicate)</pre>

<h3>Soporte nativo de <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_native_JSON">JSON</a></h3>

Con los métodos <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse"><code>JSON.parse()</code></a> y <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify"><code>JSON.stringify()</code></a>

<h2 style="font-size: 4.2rem;">EcmaScript 6 (futuro)</h2>

<a href="https://people.mozilla.org/~jorendorff/es6-draft.html">ECMAScript 6</a> será el próximo standard de Javascript pero <a href="http://kangax.github.io/compat-table/es6/">aun no está lo suficientemente implantado</a> en los navegadores mas utilizados.

Aunque podemos dar soporte de estas features de ES6 en navegadores que no las soporten utilizando el correspondiente <a href="https://github.com/paulmillr/es6-shim/">shim</a>

Si quieres empezar a utilizar las novedades que incorpora IE6 aquí tienes algunos recursos útiles para aprender:

<ul>
    <li><a href="https://6to5.org/docs/tour/">Learn ES6 | A detailed overview of ECMAScript 6 features</a></li>
    <li><a href="https://github.com/ericdouglas/ES6-Learning">ECMAScript 6 Learning! (Eric Douglas Github)</a></li>
    <li><a href="http://es6rocks.com/">ES6 Rocks | A collaborative website about the ECMAScript sixth edition, a.k.a. ES6.</a></li>
    <li><a href="http://code.tutsplus.com/articles/use-ecmascript-6-today--net-31582">Use ECMAScript 6 Today (tutsplus.com)</a></li>
</ul>

En <a href="https://twitter.com/pixelovers">pixelovers </a>hablaremos en detalle sobre ES6 y las novedades que incorpora que nos permitirán hacer con JS de forma nativa directamente cosas para las que ahora necesitamos cargar librerías externas.