---
ID: 2499
post_title: 'Patrones de Diseño en Javascript: El patrón Singleton'
author: JuanMa Garrido
post_excerpt: |
  <p>
  En Javascript, sin embargo, podemos crear un objeto directamente.
  Por lo que un singleton en su forma mas simple podria ser esto:
  </p>
  <pre style=
  "font-family: Courier New; background-color: #ecfcea; border: 1px solid #CCC; font-weight: bold;">
  
  
  var mySingleton = {
  property1: "something",
  
  property2: "something else",
  
  method1:function(){
  console.log('hello world');
  }
  
  };
  
  </pre>
  <p>
  Asi que los singletons los podemos utilizar en Javascript
  sencillamente como namespaces que aislan el código del namespace
  global y ofrecen un único punto de acceso para las funciones.
  </p>
  <p>
  Podriamos llevar este código más allá y añadir miembros y metodos
  privados. Una vez hecho esto, podemos exponer sólo aquello que
  queramos hacer publico:
  </p>
  <pre style=
  "font-family: Courier New; background-color: #ecfcea; border: 1px solid #CCC; font-weight: bold;">
  
  
  var mySingleton = function(){
  
  // here are our private methods and variables
  var privateVariable = 'something private';
  function showPrivate(){
  console.log( privateVariable );
  }
  
  // public variables and methods (which can access
  // private variables and methods )
  return {
  
  publicMethod:function(){
  showPrivate();
  },
  
  publicVar:'the public can see this!'
  
  };
  };
  
  var single = mySingleton();
  single.publicMethod();  // logs 'something private'
  console.log( single.publicVar ); // logs 'the public can see this!'
  
  </pre>
  <p>
  Si queremos acercarnos más al concepto clásico de singleton con
  Javascript, podemos montar una <em>clase</em> para que instancie
  el objeto sólo una vez. Para ello necesitamos <em>hacer el
  constructor privado y proveer de un metodo publico que devuelva
  la instancia</em> (y que controle que sólo se crea una):
  </p>
  <pre style=
  "font-family: Courier New; background-color: #ecfcea; border: 1px solid #CCC; font-weight: bold;">
  
  
  var Singleton = (function() {
  var instance = null;
  
  function PrivateConstructor() {
  var rand = Math.round(Math.random() * 100);
  this.getRand = function() {
  return rand;
  }
  }
  
  return new function() {
  this.getInstance = function() {
  if (instance == null) {
  instance = new PrivateConstructor();
  instance.constructor = null;
  }
  return instance;
  }
  }
  })();
  
  var singletonInstance = Singleton.getInstance();
  
  </pre>
  <p>
  &nbsp;¿Qué opinas de los patrones de diseño? ¿Los aplicas en tu
  trabajo diario? ¿Qué patron de diseño es el que más
  utilizas?&nbsp;¿Qué opinas del patrón Singleton?
  </p>
  <p>
  Esperamos vuestros comentarios.
  </p>
  <h2>
  &nbsp;Enlaces y más
  </h2>
  <ul>
  <li>
  <a href=
  http://www.etnassoft.com/2011/05/20/el-patron-singleton-en-javascript/
  target="_blank">El patrón singleton en JavaScript</a>
  </li>
  <li>
  <a href=
  http://www.2ality.com/2011/04/singleton-pattern-in-javascript-not.html
  target="_blank">The Singleton pattern in JavaScript not
  needed</a>
  </li>
  </ul>
  <div>
  &nbsp;
  </div>
layout: post
permalink: >
  https://pixelovers.com/patrones-diseno-javascript-patron-singleton-1698384/
published: true
post_date: 2012-03-25 13:46:00
---
<a class="thickbox" href="/app/uploads/sites/7/2012/03/4f6f0de3f15dds134326.jpg"><img class="fotobonita" style="display: block; margin-left: auto; margin-right: auto;" title="El patron Singleton" src="/app/uploads/sites/7/2012/03/4f6f0de3f15dds134326.jpg" alt=" - " align="center" /></a>

El <strong>patrón singleton</strong> es uno de los <a href="http://es.wikipedia.org/wiki/Patr%C3%B3n_de_dise%C3%B1o" target="_blank">patrones de diseño</a> más populares.

La idea general de este patrón es la de <em>asegurar que una clase genera una única instancia</em>, es decir, limitar la instanciación de una clase a un único objeto.

<!--more-->

En lenguajes basados en clases como <a href="http://es.wikipedia.org/wiki/Java_(lenguaje_de_programaci%C3%B3n)" target="_blank">Java</a>, cualquier objeto que creemos tiene que ser instanciado por una clase. Asi que  este patrón tiene más sentido en este tipo de lenguajes si queremos asegurar que una clase instancia un sólo objeto, y generar una asociación uno-a-uno entre la clase y su intancia.
<pre class="lang:js decode:true ">        class Singleton {
                private static Singleton instance = null;
                private Singleton() { }
                public static Singleton getInstance() {
                        if (instance == null) {
                                instance = new Singleton();
                        }
                        return instance;
                }
        }

</pre>
En Javascript, sin embargo, podemos crear un objeto directamente. Por lo que un singleton en su forma mas simple podria ser esto:
<pre style="font-family: Courier New; background-color: #ecfcea; border: 1px solid #CCC; font-weight: bold;">        
        var mySingleton = {
          property1: "something",

          property2: "something else",

          method1:function(){
            console.log('hello world');
          }

        };

</pre>
Asi que los singletons los podemos utilizar en Javascript sencillamente como namespaces que aislan el código del namespace global y ofrecen un único punto de acceso para las funciones.

Podriamos llevar este código más allá y añadir miembros y metodos privados. Una vez hecho esto, podemos exponer sólo aquello que queramos hacer publico:
<pre style="font-family: Courier New; background-color: #ecfcea; border: 1px solid #CCC; font-weight: bold;">        
       var mySingleton = function(){

          // here are our private methods and variables
          var privateVariable = 'something private';
          function showPrivate(){
            console.log( privateVariable );
          }

          // public variables and methods (which can access
          // private variables and methods )
          return {

            publicMethod:function(){
              showPrivate();
            },

            publicVar:'the public can see this!'

          };
        };

        var single = mySingleton();
        single.publicMethod();  // logs 'something private'
        console.log( single.publicVar ); // logs 'the public can see this!'

</pre>
Si queremos acercarnos más al concepto clásico de singleton con Javascript, podemos montar una <em>clase</em> para que instancie el objeto sólo una vez. Para ello necesitamos <em>hacer el constructor privado y proveer de un metodo publico que devuelva la instancia</em> (y que controle que sólo se crea una):
<pre style="font-family: Courier New; background-color: #ecfcea; border: 1px solid #CCC; font-weight: bold;">        
         var Singleton = (function() {
                var instance = null;

                function PrivateConstructor() {
                    var rand = Math.round(Math.random() * 100);
                    this.getRand = function() {
                        return rand;
                    } 
                }

                return new function() {
                    this.getInstance = function() {
                        if (instance == null) {
                            instance = new PrivateConstructor();
                            instance.constructor = null;
                        }
                        return instance;
                    }
                }
        })();

        var singletonInstance = Singleton.getInstance();

</pre>
¿Qué opinas de los patrones de diseño? ¿Los aplicas en tu trabajo diario? ¿Qué patron de diseño es el que más utilizas? ¿Qué opinas del patrón Singleton?

Esperamos vuestros comentarios.
<h2> Enlaces y más</h2>
<ul>
	<li><a href="http://www.etnassoft.com/2011/05/20/el-patron-singleton-en-javascript/" target="_blank">El patrón singleton en JavaScript</a></li>
	<li><a href="http://www.2ality.com/2011/04/singleton-pattern-in-javascript-not.html" target="_blank">The Singleton pattern in JavaScript not needed</a></li>
</ul>