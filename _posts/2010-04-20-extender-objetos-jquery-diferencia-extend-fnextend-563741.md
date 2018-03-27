---
ID: 2473
post_title: >
  Cómo extender objetos con jQuery.
  Diferencia entre $.extend y $.fn.extend
author: JuanMa Garrido
post_excerpt: |
  <p>
  Cuando .extend() recibe un unico objeto
  </p>
  <p>
  En este caso, como solo se le pasa un objeto, lo que hace es
  añadir los metodos definidos en este objeto al objeto
  <em>jQuery</em> o al objeto <em>jQuery.fn</em> (tambien llamado
  <em>jQuery.prototype</em> o <em>$.fn</em>)
  </p>
  <p>
  Como norma general, debemos extender el objeto <em>jQuery</em>
  para <strong>funciones</strong>, y el objeto <em>jQuery.fn</em>
  para <strong>metodos</strong>. Una funcion, a diferencia de un
  metodo, no puede ser accedida directamente desde el DOM.
  </p>
  <p>
  Por ejemplo, si extendemos el objeto <em>jQuery.fn</em> de esta
  forma:
  </p>
  <pre style="background-color: #eaf5fc;">
  <code><br />    $.fn.extend({<br />             myMethod: function(){...}<br /> });<br /></code>
  </pre>
  <p>
  Podremos aplicar este nuevo metodo a elementos del DOM de esta
  forma:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br />    $("div").myMethod();<br />      // aunque tambien podria llamar asi: $.fn.myMethod();<br /></code>
  </pre>
  <p>
  Y si extendemos el objeto <em>jQuery</em> de esta forma:
  </p>
  <pre style="background-color: #eaf5fc;">
  <code><br />    $.extend({<br />                myMethod2: function(){...}<br />        });<br /></code>
  </pre>
  <p>
  Podremos llamar a esta nueva funcion de esta forma
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br />    $.myMethod2();<br /></code>
  </pre>
  <p>
  Cuando .extend() recibe dos o más objetos
  </p>
  <p>
  Aquí lo que hace es añadirle al primer objeto, los metodos y
  variables definidos en el resto de objetos.
  </p>
  <p>
  Por ejemplo:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br />    defaults = { size: 3 };<br />   options = { height: 6 };<br />  var opts = $.extend(defaults, options)<br /><br />      // 'defaults' recibe los metodos y variable definidos en 'options'<br />        // opts == defaults == { size: 3, height: 6 }<br />     // options == { height: 6 };<br /></code>
  </pre>
  <p>
  El objeto <em>'defaults'</em> se amplia (se extiende) con los
  elementos del objeto <em>'options'</em>. El objeto
  <em>'options'</em> permanece igual.
  </p>
  <p>
  Si el primer objeto está vacio, se añadirán los metodos y
  variables del resto de objetos en un nuevo objeto. Esto es util
  cuando queremos agrupar los metodos y variables de diferentes
  objetos sin modificar ninguno de ellos.
  </p>
  <p>
  Por ejemplo:
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br />    var  opts = $.extend( {}, defaults, options)<br /><br />        // 'opts' recibe todos los metodos y variables definidos en 'defaults' y  'options', sin que estos queden modificados<br />     // opts == { size: 3, height: 6 }<br /> // defaults == { size: 3 };<br />       // options == { height: 6 };<br /></code>
  </pre>
  <p>
  El objeto <em>'opts'</em> se amplia (se extiende) con los
  elementos de <em>'defaults'</em> y <em>'options'</em>. Los
  objetos <em>'defaults'</em> y <em>'options'</em> permanecen
  igual.
  </p>
  <h2>
  Y por ultimo.... ¿hay más formas de extender los objetos jQuery,
  jQuery.fn o cualquier otro?
  </h2>
  <p>
  Pues si. Podemos extender cualquier objeto directamente con la
  nomenclatura de objetos, es decir haciendo ...
  </p>
  <pre style="background-color: #eaf5fc;">
  <code><br />    jQuery.myNewFunction_1 = function() {   <br />          // hago cosas chulas <br />     }  <br /><br /> jQuery.fn.myNewFunction_2 = function () {       <br />          // aquí tambien hago cosas chulas <br />        }<br /><br />   miObjeto.myNewFunction_3 = function () {        <br />          // y aquí no voy a ser menos <br />     }<br /></code>
  </pre>
  <p>
  ¿Y tú? ¿Has usado ya .extend() en tus aplicaciones? ¿Cómo lo has
  aplicado? Cuentanos tu experiencia.
  </p>
  <h2>
  Enlaces y más
  </h2>
  <ul>
  <li>
  <a href="http://api.jquery.com/jQuery.extend/">jQuery API:
  jquery.extend()</a>
  </li>
  <li>
  <a href=
  "http://asimilia.wordpress.com/2008/12/17/jquery-extend-confusion/">
  jQuery: $.extend() and $.fn.extend() confusion</a>
  </li>
  <li>
  <a href=
  "http://web.ontuts.com/tutoriales/como-crear-un-plugin-para-jquery/">
  Cómo crear un Plugin para jQuery</a>
  </li>
  <li>
  <a href=
  "http://stackoverflow.com/questions/1991126/difference-jquery-extend-and-jquery-fn-extend">
  Stack Overflow: difference jquery.extend and
  jquery.fn.extend</a>
  </li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/extender-objetos-jquery-diferencia-extend-fnextend-563741/
published: true
post_date: 2010-04-20 00:03:00
---
<p style="text-align: left;">En muchos de los plugins de jQuery que manejamos vemos las expresiones <code>$.extend</code> (o <code>jQuery.extend</code>) y <code>$.fn.extend</code> (o <code>jQuery.fn.extend</code>).</p>

Pues bien, lo que estamos viendo en estas expresiones es la aplicación del metodo <a href="http://api.jquery.com/jQuery.extend/"><code>.extend()</code></a>.

<!--more-->Este método es la base para la <strong>creación de plugins</strong> y para la <strong>parametrización de nuestros plugins</strong> (es decir poder tener unos valores por defecto que el usuario pueda modificar al llamar al plugin).

<h2>Pero... ¿que hace exactamente el metodo <code>.extend()</code>?</h2>

Basicamente lo que hace es extender objetos. Esto significa que, dado un objeto, le añade el contenido (funciones y variables) de otro objeto (o de otros).

La nomenclatura de este metodo es la siguiente:

<pre style="background-color: #eaf5fc;"><code>
    jQuery.extend( target, [ object1 ], [ objectN ] )
</code>
</pre>

Ahora bien, dependiendo del numero de objetos que reciba, el resultado final será diferente...

<h3>Cuando <code>.extend()</code> recibe un unico objeto</h3>

En este caso, como solo se le pasa un objeto, lo que hace es añadir los metodos definidos en este objeto al objeto <code>jQuery</code> o al objeto <code>jQuery.fn</code> (tambien llamado <code>jQuery.prototype</code> o <code>$.fn</code>)

Como norma general, debemos extender el objeto <code>jQuery </code>para <strong>funciones</strong>, y el objeto <code>jQuery.fn </code>para <strong>metodos</strong>. Una funcion, a diferencia de un metodo, no puede ser accedida directamente desde el DOM.

Por ejemplo, si extendemos el objeto <code>jQuery.fn</code> de esta forma:

<pre style="background-color: #eaf5fc;"><code>
    $.fn.extend({
             myMethod: function(){...}
 });
</code>
</pre>

Podremos aplicar este nuevo metodo a elementos del DOM de esta forma:

<pre style="background-color: #ecfcea;"><code>
    $("div").myMethod();
      // aunque tambien podria llamar asi: $.fn.myMethod();
</code>
</pre>

Y si extendemos el objeto <code>jQuery</code> de esta forma:

<pre style="background-color: #eaf5fc;"><code>
    $.extend({
                myMethod2: function(){...}
        });
</code>
</pre>

Podremos llamar a esta nueva funcion de esta forma

<pre style="background-color: #ecfcea;"><code>
    $.myMethod2();
</code>
</pre>

<h3>Cuando <code>.extend()</code> recibe dos o más objetos</h3>

Aquí lo que hace es añadirle al primer objeto, los metodos y variables definidos en el resto de objetos.

Por ejemplo:

<pre style="background-color: #ecfcea;"><code>
    defaults = { size: 3 };
   options = { height: 6 };
  var opts = $.extend(defaults, options)

      // \'defaults\' recibe los metodos y variable definidos en \'options\'
        // opts == defaults == { size: 3, height: 6 }
     // options == { height: 6 };
</code>
</pre>

El objeto <code>defaults</code> se amplia (se extiende) con los elementos del objeto <code>options</code>. El objeto <code>options</code> permanece igual.

Si el primer objeto está vacio, se añadirán los metodos y variables del resto de objetos en un nuevo objeto. Esto es util cuando queremos agrupar los metodos y variables de diferentes objetos sin modificar ninguno de ellos.

Por ejemplo:

<pre style="background-color: #ecfcea;"><code>
    var  opts = $.extend( {}, defaults, options)

        // \'opts\' recibe todos los metodos y variables definidos en \'defaults\' y  \'options\', sin que estos queden modificados
     // opts == { size: 3, height: 6 }
 // defaults == { size: 3 };
       // options == { height: 6 };
</code>
</pre>

El objeto <code>opts</code> se amplia (se extiende) con los elementos de <code>defaults</code> y <code>options</code>. Los objetos <code>defaults</code> y <code>options</code> permanecen
igual.

<h2>Y por ultimo.... ¿hay más formas de extender los objetos jQuery, jQuery.fn o cualquier otro?</h2>

Pues si. Podemos extender cualquier objeto directamente con la nomenclatura de objetos, es decir haciendo ...

<pre style="background-color: #eaf5fc;"><code>
    jQuery.myNewFunction_1 = function() {   
          // hago cosas chulas 
     }  

 jQuery.fn.myNewFunction_2 = function () {       
          // aquí tambien hago cosas chulas 
        }

   miObjeto.myNewFunction_3 = function () {        
          // y aquí no voy a ser menos 
     }
</code>
</pre>

¿Y tú? ¿Has usado ya <code>.extend()</code> en tus aplicaciones? ¿Cómo lo has
aplicado? Cuentanos tu experiencia.

<h2>Enlaces y más</h2>

<ul>
    <li><a href="http://api.jquery.com/jQuery.extend/">jQuery API: jquery.extend()</a></li>
    <li><a href="http://asimilia.wordpress.com/2008/12/17/jquery-extend-confusion/">jQuery: $.extend() and $.fn.extend() confusion</a></li>
    <li><a href="http://web.ontuts.com/tutoriales/como-crear-un-plugin-para-jquery/">Cómo crear un Plugin para jQuery</a></li>
    <li><a href="http://stackoverflow.com/questions/1991126/difference-jquery-extend-and-jquery-fn-extend">Stack Overflow: difference jquery.extend and jquery.fn.extend</a></li>
</ul>