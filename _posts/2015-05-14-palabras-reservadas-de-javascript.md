---
ID: 3359
post_title: >
  Palabras reservadas a evitar como
  nombres de variables en Javascript
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/palabras-reservadas-de-javascript/
published: true
post_date: 2015-05-14 09:22:43
---
La primera buena práctica de Javascript que yo recomendaria es: evitar como nombres de variables las palabras reservadas de Javascript.

Las palabras reservadas son aquellas palabras que no debemos utilizar como nombres de variables (identificadores) ya que Javascript tiene asociado algún otro uso para ellas y seguramente nos lanzará un error al querer utilizarlas como nombres de variables.

Buscando una buena referencia de palabras clave a evitar me encontré con <a href="https://mathiasbynens.be/notes/reserved-keywords">este post</a> de <a href="https://twitter.com/mathias">Mathias Bynens</a> que es inmejorable. En su articulo, Mathias lista y comenta las palabras clave reservadas de cada una de las versiones ECMAScript. Asi que, con permiso de su autor, este post es una traducción libre de su articulo...

<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/featured-palabras-clave.png"><img class="alignnone wp-image-3390 size-full" title="palabras clave reservadas en javascript" src="http://pixelovers.com/app/uploads/sites/7/2015/05/featured-palabras-clave.png" alt="palabras clave reservadas  javascript" width="598" height="228" /></a>

<!--more-->

¿Andas buscando una lista de palabras reservadas en Javascript? ¡¡Has llegado al lugar correcto!! :)

Hace poco me surgió la necesidad de consultar esta lista, y como no encontré una fuente clara terminé haciendo yo una comparativa de las palabras clave reservadas para las diferentes versiones ECMAScript.
Asi que para futuras referencias, aquí tenéis el resultado de esta "investigación"

<h2>ECMAScript 1</h2>

La primera versión de Javascript se basó en <a href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%201st%20edition,%20June%201997.pdf">ECMAScript 1</a> que incluía la siguiente lista de palabras reservadas.

<pre class="lang:js decode:true striped:false nums:false nums-toggle:false" title="Palabras Reservadas en ECMAScript 1">// Reserved Words in ECMAScript1
break       for         new         var
continue    function    return      void
delete      if          this        while
else        in          typeof      with

// Future Reserved Words in ECMAScript1
case        debugger    export      super
catch       default     extends     switch
class       do          finally     throw
const       enum        import      try</pre>

<h2>ECMAScript 2</h2>

Años más tarde, <a title="1998: ECMA-262 2nd edition" href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%202nd%20edition,%20August%201998.pdf">ECMAScript 2</a> añadió <code>int</code>, <code>byte</code>, <code>char</code>, <code>goto</code>, <code>long</code>, <code>final</code>, <code>float</code>, <code>short</code>, <code>double</code>, <code>native</code>,<code>public</code>, <code>static</code>, <code>throws</code>, <code>boolean</code>, <code>package</code>, <code>private</code>, <code>abstract</code>, <code>volatile</code>, <code>interface</code>, <code>protected</code>,<code>transient</code>, <code>implements</code>, <code>instanceof</code> y <code>synchronized</code>.

<pre class="striped:false nums:false nums-toggle:false lang:js decode:true" title="Palabras Reservadas en ECMAScript 2">// Reserved Words in ECMAScript2
break       for         new         var
continue    function    return      void
delete      if          this        while
else        in          typeof      with


// Future Reserved Words in ECMAScript2
abstract    do          import      short
boolean     double      instanceof  static
byte        enum        int         super
case        export      interface   switch
catch       extends     long        synchronized
char        final       native      throw
class       finally     package     throws
const       float       private     transient
debugger    goto        protected   try
default     implements  public      volatile</pre>

<h2>ECMAScript 3</h2>

<a title="1999: ECMA-262 3rd edition" href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%203rd%20edition,%20December%201999.pdf">ECMAScript 3</a> no introdujo ningún cambio en la lista de las palabras clave reservadas. Es idéntica a la lista de ECMAScript 2

<h2 id="ecmascript-4">ECMAScript 4</h2>

Lo mismo pasó con <a href="https://www.youtube.com/watch?v=ilzr1fmYtsU">ECMAScript 4</a>.

<h2 id="ecmascript-5">ECMAScript 5</h2>

<a title="2009: ECMA-262 5th edition" href="http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262%205th%20edition%20December%202009.pdf">ECMAScript 5/5.1</a> eliminó de la lista <code>int</code>, <code>byte</code>, <code>char</code>, <code>goto</code>, <code>long</code>, <code>final</code>, <code>float</code>, <code>short</code>, <code>double</code>, <code>native</code>,<code>throws</code>, <code>boolean</code>, <code>abstract</code>, <code>volatile</code>, <code>transient</code> y <code>synchronized</code>

Y añadió <code>let</code> y <code>yield</code>.

<pre class="striped:false nums:false nums-toggle:false lang:js decode:true" title="Palabras Reservadas en ECMAScript 5">// Reserved Words in ECMAScript5
break       do          instanceof  typeof
case        else        new         var
catch       finally     return      void
continue    for         switch      while
debugger    function    this        with
default     if          throw
delete      in          try


// Future Reserved Words in ECMAScript5
class       enum        extends     super
const       export      import

// Future Reserved Words in ECMAScript5 within strict mode
implements  let         private     public      yield
interface   package     protected   static

// Words that aren't strictly Reserved Words but act like them 
// and should also be avoided
eval        arguments

// Words that aren't strictly Reserved Words 
// but should also be avoided as identifiers in ES5
NaN         Infinity    undefined</pre>

Fíjate que <code>implements</code>, <code>let</code>, <code>private</code>, <code>public</code>, <code>interface</code>, <code>package</code>, <code>protected</code>, <code>static</code>, y <code>yield</code> estan prohibidas sólo en <code>strict mode</code>

También he incluido en la lista  <code>eval</code> y <code>arguments</code>. No son estrictamente palabras reservadas pero <a href="http://ecma-international.org/ecma-262/5.1/#sec-12.2.1">se comportan como tal</a>  y también están prohibidas en <code>strict mode</code>

Ademas, las propiedades <code>NaN</code>, <code>Infinity</code>, y <code>undefined</code> del objeto global son propiedades inmutables y de sólo lectura en ECMAScript 5. Asi que aunque hagamos <code>var NaN = 42;</code> en el contexto global no nos va a dar error pero tampoco va a hacer nada (no se va guardar ese valor en esa variable/propiedad). Por tanto, para evitar confusiones, es mejor evitar también el uso de estas palabras como identificadores de variables aunque no sean estrictamente palabras reservadas.

<h2 id="ecmascript-4">ECMAScript 6</h2>

El <a href="https://people.mozilla.org/~jorendorff/es6-draft.html">último borrador de ECMAScript 6</a> añade <code>await</code> como una futura palabra clave dentro de los modulos. <code>let</code> y <code>yield</code> estan prohibidas ahora incluso fuera del modo <code>strict mode</code>

<pre class="striped:false nums:false nums-toggle:false lang:js decode:true " title="Palabras Reservadas en ECMAScript 6">// Reserved Words in ECMAScript6
break       do          in          typeof
case        else        instanceof  var
catch       export      new         void
class       extends     return      while
const       finally     super       with
continue    for         switch      yield
debugger    function    this    
default     if          throw   
delete      import      try

// Future Reserved Words in ECMAScript5
enum        await

// Future Reserved Words in ECMAScript6 within strict mode
implements  package     protected   
interface   private     public</pre>

<h2>¿Y cual es la utilidad práctica de todo esto?</h2>

Las palabras reservadas no deben ser utilizadas como <a href="https://mathiasbynens.be/notes/javascript-identifiers">nombres de variable en Javascript</a>. Para un soporte optimo de versiones antiguas de Javascript (y evitar errores inesperados), lo mejor es acostumbrarse a <strong>evitar el uso de todas las palabras clave que aparecen en este articulo como nombres de variables o nombres de propiedades</strong>, incluso los más antiguos de ECMAScript 2 como <code>char</code> y <code>default</code>.

<hr />

Cómo habreis observado en cada versión ECMAScript hay una lista de palabras claves reservadas y otra de "futuras" palabras claves reservadas.

Las "futuras" son palabras clave que si bien no están desarrolladas ni especificadas en la versión de ECMAScript que se trate, si que están propuestas oficialmente para ser desarrolladas por lo que se desaconseja su uso también para evitar problemas cuando ya esten implementadas