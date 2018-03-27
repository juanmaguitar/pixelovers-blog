---
ID: 2470
post_title: 'Javascript y jQuery: Consejos y Buenas Practicas (Parte II)'
author: JuanMa Garrido
post_excerpt: |
  <p>
  Practicas eficientes
  </p>
  <ul>
  <li style="margin-bottom: 10px;">
  <strong>Checkear la disponibilidad de un objeto antes de
  acceder a él.</strong> Muchos de los errores en Javascript se
  deben a que se intenta acceder a elementos o métodos que no
  existen en un determinado momento del periodo de ejecución.
  Para solucionar esto basta con realizar un pequeña comprobación
  antes de utilizar dicho elemento o método.
  <p>
  Ejemplo:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      if ( $('#signup').length ) {<br />              $('#signup input').change ( function () {<br />                 alert ("Acabas de poner " + $(this).val() );<br />              });<br />       }<br />                                 <br /></code>
  </pre>
  </li>
  <li style="margin-bottom: 10px;">
  <strong>Evita el uso de variables globales.</strong> A fin de
  evitar el uso de variables globales, podemos utilizar data, un
  método de jQuery que nos permite mantener relaciones entre
  valores y elementos DOM.
  <p>
  Por ejemplo podemos guardar un dato en el objeto document de
  esta forma
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      $(document).data('id_country',3) ,<br />                                        <br /></code>
  </pre>
  <p>
  Y acceder al dato de esta leer el dato de esta otra
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      $(document).data('id_country')<br />                                    <br /></code>
  </pre>
  <p>
  Aunque lo suyo realmente es aprovechar la terminologia de
  objetos y ubicar las variables en su contexto
  </p>
  <p>
  Ejemplo:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      var mySite = {<br />            general_1 : 100 ,<br />         general_2 : 200,<br />                                                  <br />          myObject1 : {<br />                                                     <br />                  local_1 : 500,<br />                    funcionLocal : function() {<br />                               var local_2 = 600;<br />                                console.log ("estoy en funcionLocal");<br />                            console.log ("local_1=" + mySite.myObject1.local_1);<br />                              console.log ("local_2=" + local_2);<br />                       }<br />                                         <br />          },<br /><br />          init : function() {<br />                       console.log ("estoy en init");<br />                    this.funcionalidad1();<br />                    this.myObject1.funcionLocal();<br />            },<br />                                                <br />          funcionalidad1 : function() {<br />                     console.log ("estoy en funcionalidad1");<br />                  console.log ("general_1=" + this.general_1);<br />                      console.log ("general_2=" + this.general_2);<br />              }<br /> }<br /><br /></code>
  </pre>
  </li>
  <li style="margin-bottom: 10px;">
  <strong>Definir siempre las variables con VAR</strong> ,
  incluso dentro de los FOR, de esta forma nos aseguramos que la
  variable tendrá el ambito que le corresponda. Si no se pone var
  se toma la variable como global.
  <p>
  Mala declaracion de variables para el FOR
  </p>
  <pre style="background-color: #fceaea;">
  <code><br /><br />      var i=0; // Creates a global variable<br /><br />       function test() {<br />    for (i=0; i&lt;10; i++) {<br />                // do something<br />    }<br />      }<br /><br />   test();<br /><br />     alert(i); // The global variable i is now 10!<br /><br /></code>
  </pre>
  <p>
  Buenas declaraciones de variables para el FOR
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      var i=0; // Creates a global variable<br /><br />       function test() {<br />    var i=0;<br />          for (i=0; i&lt;10; i++) {<br />                      // do something<br />      }<br />      }<br /><br />   function test2() {<br />           for (var i=0; i&lt;10; i++) {<br />                  // do something else<br />         }<br />      }<br /><br />   test();<br />   test2();<br /><br />    alert(i); // The global variable i is still 0!<br /><br /></code>
  </pre>
  </li>
  <li style="margin-bottom: 10px;">
  <strong>Usa FOR en vez de EACH</strong>. Por lo general las
  funciones nativas de Javascript son mas rapidas que las
  derivadas de librerias
  <p>
  Ejemplos:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      var array = new Array ();  <br />       for (var i=0; i&lt;10000; i++) {  <br />                array[i] = 0;  <br />   }  <br />       <br />  // Mas lento<br />      $.each (array, function (i) {  <br />           array[i] = i;  <br />   });  <br /><br />       // Mas rapido<br />     var l = array.length;  <br />   for (var i=0; i&lt;l; i++) {  <br />            array[i] = i;  <br />   }<br /><br /></code>
  </pre>
  </li>
  <li style="margin-bottom: 10px;">
  <strong>Para concatenaciones largas de cadenas, mejor <a href=
  "http://www.w3schools.com/jsref/jsref_join.asp">JOIN()</a> que
  <a href=
  "http://www.w3schools.com/jsref/jsref_concat_array.asp">CONCAT()</a></strong>.
  JOIN devuelve texto y CONCAT devuelve un array.
  <p>
  Ejemplos:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      var array = [];  <br /> for (var i=0; i&lt;=1000; i++) {  <br />                array[i] = '</code>
  </pre>
  </li>
  <li>'+i+'
  </li>
  <li style="margin-bottom: 10px;">
  <pre style="background-color: #ecfcea;">
  <code>';  <br />        }  <br /><br /> // JOIN devuelve texto<br />    $('#list').html ( array.join (''));  <br /><br />       // CONCAT devuelve array<br />  var array_concat = array.concat('');  <br /><br /> </code>
  </pre>
  </li>
  <li style="margin-bottom: 10px;">
  <strong>Return FALSE</strong> Si no devuelves FALSE en la
  funcion la pagina salta al top, por eso a la hora de capturar
  eventos conviene devolver FALSE al final para que haga lo que
  nosotros definimos y nada mas
  <p>
  En vez de esto:
  </p>
  <pre style="background-color: #fceaea;">
  <code><br />    <br />  $('#item').click (function () {<br />           // stuff here<br />     });<br /><br /></code>
  </pre>
  <p>
  Mejor esto:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br /><br />      $('#item').click (function () {<br />           // stuff here<br />             return false;<br />     });<br /><br /></code>
  </pre>
  </li>
  <li style="margin-bottom: 10px;">
  <strong>Usar correctamente el tag SCRIPT</strong>. El atributo
  LANGUAGE está deprecado en el tag <script type=
  "text/javascript">
  . La forma correcta de crear un bloque de código javascript es:
  <pre style="background-color:#ecfcea;"><code><br /><br />       <script type="text/javascript ><br />           // code JS here<br />   </script><script><br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>La selección mas rápida es por ID< /strong>. Siempre el selector más rápido y que menos iteraciones produce es la búsqueda por un #id, ya que simplemente lanza un document.getElementById(), lo que al ser nativo nos asegura un tiempo de respuesta mínimo y un mínimo consumo de proceso.
  <p>Por ejemplo, con este codigo:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       <div id="content"><br />                <form method="post" action="/"><br />                   <h2>Traffic Light< /h2><br />                            <ul id="traffic_light"><br />                                   <li><input type="radio" name="light" value="red" /> Red< /li><br />                                      </li><li><input type="radio" name="light" value="yellow" /> Yellow< /li><br />                                        </li><li><input type="radio" name="light" value="green" /> Green< /li><br />                          < /ul><br />                             <input id="traffic_button" type="submit" value="Go" /><br />            < /form><br />   < /div><br /><br />< /code>< /pre>
  <p>En vez de esto:< /p>
  <pre style="background-color:#fceaea;">                 <code><br /><br />      // Más lento<br />      var traffic_button = $('#content .button');<br /><br />< /code>< /pre>
  <p>Mejor esto:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       // Más rápido<br />     var traffic_button = $('#traffic_button');<br /><br />< /code>< /pre>
  <p>Para acceder a varios elementos, siempre que podamos debemos hacerlo partiendo de un #id, de esta forma nos aseguramos una iteración más ajustada.:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       var traffic_lights = $('#traffic_light input');<br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>Usar tags delante de las clases< /strong>. Al hacer selección de clases con jQuery, es recomendable indicar el tag del elemento solicitado ya que al hacer iternamente uso de document.getElementsByTagName() para localizarlos acotamos previamente los elementos en los que buscar las clases solicitadas.
  <p>Por ejemplo, para el HTML del punto anterior, si queremos seleccionar el elemento radio con, la opción más rápida sería la siguiente:< /p>
  <pre style="background-color:#ecfcea;"><code><br />     <br />  var active_light = $('#traffic_light input.on');<br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>Usar la caché de objetos< /strong>. Coger el hábito de guardar una variable con el valor de un objeto jQuery nos evita realizar una serie de comprobaciones innecesarias y que en scripts pesados pueden suponer un aumento de rendimiento importante.
  <p>Seleccion poco eficiente de elementos:< /p>
  <pre style="background-color:#fceaea;">                 <code><br /><br />      $('#traffic_light input.on).bind('click', function(){...});<br />       $('#traffic_light input.on).css('border', '3px dashed yellow');<br />   $('#traffic_light input.on).css('background-color', 'orange');<br />    $('#traffic_light input.on).fadeIn('slow');<br /><br />< /code>< /pre>
  <p>Seleccion Eficiente de elementos:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       var $active_light = $('#traffic_light input.on');<br /> $active_light.bind('click', function(){...});<br />     $active_light.css('border', '3px dashed yellow');<br /> $active_light.css('background-color', 'orange');<br />  $active_light.fadeIn('slow');<br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>Crear Objeto Global con resultados jQuery.< /strong>. Si necesitamos utilizar una selección jQuery en diferentes funciones, se puede cachear en un objeto con ámbito global.
  <p>Ejemplo:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       // Define an object in the global scope (i.e. the window object)<br /><br />    window.$my = {<br /><br />              // Initialize all the queries you want to use more than once<br />              head : $('head'),<br />              traffic_light : $('#traffic_light'),<br />              traffic_button : $('#traffic_button')<br />        };<br /><br />  function do_something() {<br /><br />              // Now you can reference the stored results and manipulate them<br />              var script = document.createElement('script');<br /><br />              $my.head.append(script);<br />              // When working inside functions, continue to save jQuery results<br /><br />              // to your global container.<br />              $my.cool_results = $('#some_ul li');<br />              $my.other_results = $('#some_table td');<br /><br />              // Use the global functions as you would a normal jQuery result<br />              $my.other_results.css('border-color', 'red');<br />              $my.traffic_light.css('border-color', 'green');<br />        }<br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>Aprovechar el encadenamiento< /strong>. El encadenamiento pese a producir un amasijo de código que no contribuye a mejorar la lectura del código hace que nuestro Javascript sea más ligero y puede ayudar a mejorar el rendimiento de nuestros scripts.
  <p>Ejemplo:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       var $active_light = $('#traffic_light input.on');<br /> <br />  $active_light.bind('click', function(){...})<br />              .css('border', '3px dashed yellow')<br />               .css('background-color', 'orange')<br />                .fadeIn('slow');<br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>Usar subqueries siempre que se pueda< /strong>. Si debemos realizar varias búsquedas sobre un elemento es altamente recomendable realizar un uso intensivo del método find() de jQuery para realizar las búsquedas. Mejoraremos el tiempo de respuesta al evitarnos búsquedas previas ya realizadas.
  <p>Ejemplo:< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       var $traffic_light = $('#traffic_light'),<br /> $active_light = traffic_light.find('input.on'),<br />   $inactive_lights = $traffic_light.find('input.off');<br /><br />< /code>< /pre>
  < /li>
  <li style="margin-bottom:10px;"><strong>Limitar la manipulación directa del DOM< /strong>. La idea general es crear exactamente lo que necesitas en memoria y luego actualizar el DOM
  <p>Si necesitas crear una lista de elementos, en vez de :< /p>
  <pre style="background-color:#fceaea;">                 <code><br /> <br />     var top_100_list = [...], // assume this has 100 unique strings<br />   $mylist = $('#mylist'); // jQuery selects our <ul> element<br /><br />  for (var i=0, l=top_100_list.length; i<l ; i++) {<br></l>          $mylist.append('<li>' + top_100_list[i] + '< /li>');<br />       }<br /><br /> < /code>< /pre>
  <p>Creamos la lista de elementos en un string antes de insertarlo en el DOM< /p>
  <pre style="background-color:#ecfcea;"><code><br /><br />       var top_100_list = [...], // assume this has 100 unique strings<br />   $mylist = $('#mylist'), // jQuery selects our <ul> element<br />        top_100_li = ""; // This will store our list items<br />        <br />  for (var i=0, l=top_100_list.length; i<l ; i++) {<br></l>          top_100_li += '<li>' + top_100_list[i] + '< /li>';<br /> }<br /><br />   $mylist.html(top_100_li);<br /><br /> < /code>< /pre>
  < /li>
  </li><li style="margin-bottom:10px;"><strong>Usar JSON< /strong>. Para guardar estructuras de datos o enviar/recibir estructuras de datos via AJAX mejor <a href="http://www.json.org/">JSON< /a> que </a><a href="http://www.w3.org/XML/">XML< /a>< /li>
  < /ul>
  <p>Y hasta aqui la segunda parte y el final de la serie de consejos y buenas practicas para desarrollo con Javascript y jQuery.< /p>
  </p><p>¿Que te han parecido los puntos aqui comentados? ¿Algun punto que creas que falta en esta lista?.< /p>
  <h2>Enlaces y más< /h2>
  <ul>
  <li><a href="http://www.bobbyvandersluis.com/articles/javascript_good_practices/index.html">Ten good practices for writing JavaScript in 2005< /a>< /li>
  <li><a href="http://www.smashingmagazine.com/2008/09/16/jquery-examples-and-best-practices/">jQuery and JavaScript Coding: Examples and Best Practices< /a>< /li>
  <li><a href="http://www.anieto2k.com/2009/05/13/optimizando-el-rendimiento-de-nuestros-scritps-jquery/">Optimizando el rendimiento de nuestros scritps jQuery< /a>< /li>
  <li><a href="http://www.javascripttoolbox.com/bestpractices/">Javascript Best Practices< /a>< /li>
  <li><a href="http://developer.yahoo.com/performance/rules.html">Best Practices for Speeding Up Your Web Site< /a>< /li>
  <li><a href="http://www.artzstudio.com/2009/04/jquery-performance-rules/">jQuery Performance Rules< /a>< /li>
  <li><a href="http://net.tutsplus.com/tutorials/javascript-ajax/10-ways-to-instantly-increase-your-jquery-performance/">10 Ways to Instantly Increase Your jQuery Performance< /a>< /li>
  <li><a href="http://www.anieto2k.com/2007/09/20/analizando-las-formas-de-optimizar-el-trabajo-con-dom-en-javascript/">Analizando las formas de optimizar el trabajo con DOM en Javascript< /a>< /li>
  <li><a href="http://www.tvidesign.co.uk/blog/improve-your-jquery-25-excellent-tips.aspx">Improve your jQuery - 25 excellent tips< /a>< /li>
  < /ul>
  < /script>
  < /li>
  < /ul>
  </a></li></a></li></a></li></a></li></a></li></a></li></a></li></a></li></a></li></ul></h2></p></a></strong></li></ul></code></pre></p></li></ul></code></pre></p></strong></li></code></pre></p></strong></li></code></pre></p></strong></li></code></pre></p></strong></li></code></pre></p></code></pre></p></strong></li></code></pre></p></strong></li></code></pre></p></code></pre></p></code></pre></p></li></ul></h2></form></div></code></pre></p></strong></li></script>
  </code></pre></script></li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/javascript-jquery-consejos-buenas-practicas-parte-ii-521211/
published: true
post_date: 2010-02-20 20:30:00
---
<img class=" ma-l alignleft wp-image-2924" src="http://pixelovers.com/app/uploads/sites/7/2010/02/308801-209198_t.jpg" alt="308801-209198_t" width="229" height="229" />Hace unas semanas iniciamos una serie de 2 posts para hablar de lo que consideramos que son unas buenas practicas para desarrollar codigo Javascript con la libreria jQuery.

Con este post cerramos la serie y profundizamos un poco más en eltema

En el  <a href="http://pixelovers.com/javascript-jquery-consejos-buenas-practicas-parte-i-308801">primer post de esta serie</a> comentamos algunas generalidades que nos pueden servir de base a la hora de desarrollar un código JS eficiente. En este segundo post hablaremos de como solucionar de forma eficiente problemas concretos que nos solemos encontrar en nuestros desarrollos.

<!--more-->

Asi que, ahi vamos...

<h3>1.- Checkear la disponibilidad de un objeto antes de acceder a él.</h3>

Muchos de los errores en Javascript se deben a que se intenta acceder a elementos o métodos que no existen en un determinado momento del periodo de ejecución.

Para solucionar esto basta con realizar un pequeña comprobación antes de utilizar dicho elemento o método.

Ejemplo:

<pre class="lang:js decode:true" style="padding-left: 30px;">if ( $('#signup').length ) {
  $('#signup input').change ( function () {
    alert ("Acabas de poner " + $(this).val() );
  });
}

</pre>

<h3>2.- Evita el uso de variables globales.</h3>

A fin de evitar el uso de variables globales, podemos utilizar data, un método de jQuery que nos permite mantener relaciones entre valores y elementos DOM.Por ejemplo podemos guardar un dato en el objeto document de esta forma

<pre class="lang:js decode:true">  $(document).data('id_country',3)

</pre>

Y acceder al dato de esta leer el dato de esta otra

<pre class="lang:js decode:true">  $(document).data('id_country')

</pre>

Aunque lo suyo realmente es aprovechar la terminologia de objetos y ubicar las variables en su contexto

Ejemplo:

<pre class="lang:js decode:true">    

var mySite = {
  general_1 : 100 ,
  general_2 : 200,

  myObject1 : {
    local_1 : 500,
    funcionLocal : function() {
      var local_2 = 600;
      console.log ("estoy en funcionLocal");
      console.log ("local_1=" + mySite.myObject1.local_1);
      console.log ("local_2=" + local_2);
    }
  },

  init : function() {
    console.log ("estoy en init");
    this.funcionalidad1();
    this.myObject1.funcionLocal();
  },

  funcionalidad1 : function() {
    console.log ("estoy en funcionalidad1");
    console.log ("general_1=" + this.general_1);
    console.log ("general_2=" + this.general_2);
  }
}

</pre>

<h3>3.- Definir siempre las variables con `var`.</h3>

Incluso dentro de los <code>for</code>, de esta forma nos aseguramos que la variable tendrá el ambito que le corresponda. Si no se pone var se toma la variable como global.

<em>Mala declaracion de variables para el <code>for</code></em>

<pre class="lang:js decode:true ">  

  var i=0; // Creates a global variable

  function test() {
    for (i=0; i&lt;10; i++) {
      // do something
    }
  }

  test();
  alert(i); // The global variable i is now 10!

</pre>

<em>Buenas declaraciones de variables para el <code>for</code></em>

<pre class="lang:js decode:true">  var i=0; // Creates a global variable

  function test() {
    var i=0;
    for (i=0; i&lt;10; i++) {
      // do something
    }
  }

  function test2() {
    for (var i=0; i&lt;10; i++) {
      // do something else
    }
  }

  test();
  test2();

  alert(i); // The global variable i is still 0!

</pre>

<h3>4.- Usa `for` en vez de `$.each`</h3>

Por lo general las funciones nativas de Javascript son mas rapidas que las derivadas de librerias

Ejemplos:

<pre class="lang:js decode:true">  var array = new Array ();  
  for (var i=0; i&lt;10000; i++) {  
    array[i] = 0;  
  }  

  // Mas lento
  $.each (array, function (i) {  
    array[i] = i;  
  });  

  // Mas rapido
  var l = array.length;  
  for (var i=0; i&lt;l; i++) {  
    array[i] = i;  
  }

</pre>

<h3>5.- Para concatenaciones largas de cadenas, mejor <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join">`join`</a> que <a href="http://www.w3schools.com/jsref/jsref_concat_array.asp">`concat`</a></h3>

<code>join</code> devuelve texto y <code>concat</code> devuelve un array.

Ejemplos:

<pre class="lang:js decode:true">var array = [];  
for (var i=1; i&lt; =1000; i++) {  
  array[i] = i;  
}  

 // JOIN devuelve texto
var array_join = array.join('');  
typeof array_join === "string" // true

// CONCAT devuelve array
var array_concat = array.concat('');  
array_concat instanceof Array // true

</pre>

<h3>6.- return `false` para evitar "saltos".</h3>

Si no devuelves <code>false</code> en la funcion la pagina salta al top, por eso a la hora de capturar eventos conviene devolver <code>false</code> al final para que haga lo que nosotros definimos y nada mas

En vez de esto:

<pre class="lang:js decode:true">$('#item').click (function () {
  // stuff here
});

</pre>

Mejor esto:

<pre class="lang:js decode:true">  $('#item').click (function () {
    // stuff here
    return false;
  });

</pre>

<h3>7.- Usar correctamente el tag `script`.</h3>

El atributo <code>language</code> está deprecado en el tag <code>script</code>

La forma correcta de crear un bloque de código javascript es:

<pre class="lang:js decode:true">&lt;script type="text/javascript"&gt;
   // code JS here
&lt;/script&gt;</pre>

<h3>8.- La selección mas rápida es por ID.</h3>

Siempre el selector más rápido y que menos iteraciones produce es la búsqueda por un #id, ya que simplemente lanza un <code>document.getElementById()</code>, lo que al ser nativo nos asegura un tiempo de respuesta mínimo y un mínimo consumo de proceso.

Por ejemplo, con este codigo:

<div id="content"><form action="#" method="post">
<h3>Traffic Light</h3>
<ul id="traffic_light">
    <li><input name="light" type="radio" value="red" /> Red</li>
    <li><input name="light" type="radio" value="yellow" /> Yellow</li>
    <li><input name="light" type="radio" value="green" /> Green</li>
</ul>
<input id="traffic_button" type="submit" value="Go" /></form></div>

En vez de esto:

<pre class="lang:js decode:true">// Más lento
var traffic_button = $('#content .button');

</pre>

Mejor esto:

<pre class="lang:js decode:true">  // Más rápido
  var traffic_button = $('#traffic_button');

</pre>

Para acceder a varios elementos, siempre que podamos debemos hacerlo partiendo de un #id, de esta forma nos aseguramos una iteración más ajustada.:

<pre class="lang:js decode:true">  var traffic_lights = $('#traffic_light input');

</pre>

<h3>9.- Usar tags delante de las clases.</h3>

Al hacer selección de clases con jQuery, es recomendable indicar el tag del elemento solicitado ya que al hacer iternamente uso de <code>document.getElementsByTagName()</code> para localizarlos acotamos previamente los elementos en los que buscar las clases solicitadas.

Por ejemplo, para el HTML del punto anterior, si queremos seleccionar el elemento radio con, la opción más rápida sería la siguiente:

<pre class="lang:js decode:true">  var active_light = $('#traffic_light input.on');

</pre>

<h3>10.- Usar la caché de objetos.</h3>

Coger el hábito de guardar una variable con el valor de un objeto jQuery nos evita realizar una serie de comprobaciones innecesarias y que en scripts pesados pueden suponer un aumento de rendimiento importante.

<em>Seleccion poco eficiente de elementos:</em>

<pre class="lang:js decode:true">$('#traffic_light input.on').bind('click', function(){...});
$('#traffic_light input.on').css('border', '3px dashed yellow');
$('#traffic_light input.on').css('background-color', 'orange');
$('#traffic_light input.on').fadeIn('slow');

</pre>

<em>Seleccion Eficiente de elementos:</em>

<pre class="lang:js decode:true">var $active_light = $('#traffic_light input.on');
$active_light.bind('click', function(){...});
$active_light.css('border', '3px dashed yellow');
$active_light.css('background-color', 'orange');
$active_light.fadeIn('slow');

</pre>

<h3>11.- Crear Objeto Global con resultados jQuery.</h3>

Si necesitamos utilizar una selección jQuery en diferentes funciones, se puede cachear en un objeto con ámbito global.

Ejemplo:

<pre class="lang:js decode:true">// Define an object in the global scope (i.e. the window object)

window.$my = {
  // Initialize all the queries you want to use more than once
  head : $('head'),
  traffic_light : $('#traffic_light'),
  traffic_button : $('#traffic_button')
};

function do_something() {

  // Now you can reference the stored results and manipulate them
  var script = document.createElement('script');

  $my.head.append(script);
  // When working inside functions, continue to save jQuery results

  // to your global container.
  $my.cool_results = $('#some_ul li');
  $my.other_results = $('#some_table td');

  // Use the global functions as you would a normal jQuery result
  $my.other_results.css('border-color', 'red');
  $my.traffic_light.css('border-color', 'green');

}

</pre>

<h3>12.- Aprovechar el encadenamiento.</h3>

El encadenamiento pese a producir un amasijo de código que no contribuye a mejorar la lectura del código hace que nuestro Javascript sea más ligero y puede ayudar a mejorar el rendimiento de nuestros scripts.

Ejemplo:

<pre class="lang:js decode:true">var $active_light = $('#traffic_light input.on');

$active_light.bind('click', function(){...})
  .css('border', '3px dashed yellow')
  .css('background-color', 'orange')
  .fadeIn('slow');

</pre>

<h3>13.- Usar subqueries siempre que se pueda.</h3>

Si debemos realizar varias búsquedas sobre un elemento es altamente recomendable realizar un uso intensivo del método find() de jQuery para realizar las búsquedas. Mejoraremos el tiempo de respuesta al evitarnos búsquedas previas ya realizadas.

Ejemplo:

<pre class="lang:js decode:true">var $traffic_light = $('#traffic_light'),
$active_light = traffic_light.find('input.on'),
$inactive_lights = $traffic_light.find('input.off');

</pre>

<h3>14.- Limitar la manipulación directa del DOM.</h3>

La idea general es crear exactamente lo que necesitas en memoria y luego actualizar el DOM

Si necesitas crear una lista de elementos, en vez de :

<pre class="lang:js decode:true">var top_100_list = [...], // assume this has 100 unique strings
    $mylist = $('#mylist'); // jQuery selects our 'ul' element 

for (var i=0, l=top_100_list.length; i</pre>

Creamos la lista de elementos en un string antes de insertarlo en el DOM

<pre class="lang:js decode:true">var top_100_list = [...], // assume this has 100 unique strings
  $mylist = $('#mylist'), // jQuery selects our 'ul' element
  top_100_li = ""; // This will store our list items 

  for (var i=0, l=top_100_list.length; i</pre>

<h3>15.- Usar JSON.</h3>

Para guardar estructuras de datos o enviar/recibir estructuras de datos via AJAX mejor <a href="http://www.json.org/">JSON</a> que <a href="http://www.w3.org/XML/">XML</a>

Y hasta aqui la segunda parte y el final de la serie de consejos y buenas practicas para desarrollo con Javascript y jQuery.

¿Que te han parecido los puntos aqui comentados? ¿Algun punto que creas que falta en esta lista?.

<h2>Enlaces y más</h2>

<ul>
    <li><a href="http://www.bobbyvandersluis.com/articles/javascript_good_practices/index.html">Ten good practices for writing JavaScript in 2005</a></li>
    <li><a href="http://www.smashingmagazine.com/2008/09/16/jquery-examples-and-best-practices/">jQuery and JavaScript Coding: Examples and Best Practices</a></li>
    <li><a href="http://www.anieto2k.com/2009/05/13/optimizando-el-rendimiento-de-nuestros-scritps-jquery/">Optimizando el rendimiento de nuestros scritps jQuery</a></li>
    <li><a href="http://www.javascripttoolbox.com/bestpractices/">Javascript Best Practices</a></li>
    <li><a href="http://developer.yahoo.com/performance/rules.html">Best Practices for Speeding Up Your Web Site</a></li>
    <li><a href="http://www.artzstudio.com/2009/04/jquery-performance-rules/">jQuery Performance Rules</a></li>
    <li><a href="http://net.tutsplus.com/tutorials/javascript-ajax/10-ways-to-instantly-increase-your-jquery-performance/">10 Ways to Instantly Increase Your jQuery Performance</a></li>
    <li><a href="http://www.anieto2k.com/2007/09/20/analizando-las-formas-de-optimizar-el-trabajo-con-dom-en-javascript/">Analizando las formas de optimizar el trabajo con DOM en Javascript</a></li>
    <li><a href="http://www.tvidesign.co.uk/blog/improve-your-jquery-25-excellent-tips.aspx">Improve your jQuery - 25 excellent tips</a></li>
</ul>