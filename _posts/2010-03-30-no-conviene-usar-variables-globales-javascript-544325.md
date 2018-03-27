---
ID: 2472
post_title: >
  Por qué no conviene usar variables
  globales en Javascript
author: JuanMa Garrido
post_excerpt: |
  <p>
  Global variables are evil.
  </p>
  <p>
  Las variables globales son una fuente de falta de fiabilidad y de
  inseguridad. Su uso hace que se incremente el riesgo de
  colisiones con otras variables de otros programas. El riesgo de
  colisiones es mayor, cuantos mas librerias, plugins y widgets
  utilizemos.
  </p>
  <p>
  De hecho, una medida objetiva de la calidad de un programa
  Javascript es: <em>¿Cuantas variables globales y funciones
  globales tiene?</em> Cuantas mas tenga, de peor calidad es
  </p>
  <p>
  Veamos ahora las diferentes formas de crear variables globales
  asi como la mejor alternativa a su uso.
  </p>
  <p>
  Hay 3 maneras de definir una variable global en Javascript:
  </p>
  <ul>
  <li>
  <p>
  La primera forma es declarar la variable fuera de cualquier
  funcion
  </p>
  <pre style="background-color: #fefbe4;">
  <code><br />                    var myGlobalVar = value;<br />          </code>
  </pre>
  </li>
  <li>
  <p>
  La segunda forma es asignar la variable como una propiedad
  del objeto global que en los navegadores web es el objeto
  window
  </p>
  <pre style="background-color: #fefbe4;">
  <code><br />                    window.myGlobalVar = value;<br />               </code>
  </pre>
  </li>
  <li>
  <p>
  La tercera forma es usar la variable directamente sin
  definirla antes. En este caso no importa si la variable está
  dentro o fuera de una funcion. Se considera implícitamente
  que es una variable global
  </p>
  <pre style="background-color: #fefbe4;">
  <code><br />                    myGlobalVar = 'Hello world';<br />              </code>
  </pre>
  </li>
  </ul>
  <p>
  Una buena manera de minimizar el uso de variables globales es
  almacenarlas en un único objeto global. Haciendo esto puedes
  mantener todas tus variables y funciones en un único lugar,
  reduciendo ampliamente el riesgo de colisiones de nombre.
  </p>
  <pre style="background-color: #ecfcea;">
  <code><br />                    // Define your global object  <br />                    var myObj = {};  <br /><br />                   // Add property (variable) to it  <br />                        myObj.myVar = 'Hello world';  <br /><br /><br />                        // Add method to it  <br />                     myObj.myFunctions = function() {  <br />                                // Do cool stuff  <br />                        };  <br />              </code>
  </pre>
  <p>
  Idealmente, un aplicación, librería, componente o widget define
  una unica variable global. Esta variable global deberia ser un
  objeto que es el namespace raiz de toda nuestra funcionalidad
  (funciones y variables)
  </p>
  <p>
  El lenguaje javascript se diseñó con variables globales para
  hacer más facil a los principiantes empezar a programar con este
  lenguaje. Pero el efecto colateral es que es facil olvidar
  definir una variable y de esta forma crear un bug difícil de
  descubrir. Asi que hazte un favor, y evita el uso de variables
  globales siempre que sea posible.
  </p>
  <p>
  ¿Y tu que opinas? ¿Alguna idea más para comentar respecto al uso
  de variables globales o alternativas?. Esperamos vuestros
  comentarios.
  </p>
  <h2>
  Enlaces y más
  </h2>
  <ul>
  <li>
  <a href=
  "http://yuiblog.com/blog/2006/06/01/global-domination/">Global
  Domination at Yahoo! User Interface Blog</a>
  </li>
  <li>
  <a href=
  "http://www.svennerberg.com/2009/02/global-variables-in-javascript/">
  Global variables in Javascript</a>
  </li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/no-conviene-usar-variables-globales-javascript-544325/
published: true
post_date: 2010-03-30 00:25:00
---
Desde hace tiempo vengo leyendo en muchos blogs de desarrollo con Javascript la recomendación de no utilizar variables globales en nuestro código. Pero ¿por qué se recomienda no utilizar variables globales en Javascript?

En pixelovers hemos querido ahondar un poco en esta cuestión y para ello comenzaremos respondiendo a algunas preguntas:<!--more-->
<h3><strong>¿Qué son las variables globales?</strong></h3>
En Javascript los programas son entregados como texto. Este texto Javascript es evaluado y compilado en un ejecutable que se ejecuta inmediatamente. Esta ejecución puede dejar algunos elementos en el objeto global de la ventana.

El objeto global es el espacio de memoria que contiene las funciones y variables que estan en la raiz. Las variables que no se definen específicamente tambien son consideradas como variables globales.

Los nombres de estas variables se mantienen en el objeto global y sus valores son accesibles desde cualquier parte del código.
<h3><strong>¿Si no es recomendable el uso de variables globales en Javascript por qué existen?</strong></h3>
Este uso de variables globales era conveniente para los pequeños scripts que Navigator 2 esperaba soportar. Con el tiempo, estos pequeños script han derivado en complejas aplicaciones Web 2.0 (POO, AJAX, uso de librerias, plugins, etc...)  por lo que el uso de variables globales ya no tiene justificación.
<h3>Global variables are evil.</h3>
Las variables globales son una fuente de falta de fiabilidad y de inseguridad. Su uso hace que se incremente el riesgo de colisiones con otras variables de otros programas. El riesgo de colisiones es mayor, cuantos mas librerias, plugins y widgets utilizemos.

De hecho, una medida objetiva de la calidad de un programa Javascript es: <em>¿Cuantas variables globales y funciones globales tiene?</em> Cuantas mas tenga, de peor calidad es

Veamos ahora las diferentes formas de crear variables globales asi como la mejor alternativa a su uso.

Hay 3 maneras de definir una variable global en Javascript:
<ul>
	<li>La primera forma es declarar la variable fuera de cualquier funcion
<pre style="background-color: #fefbe4;" class=""><code>var myGlobalVar = value;</code>
</pre>
</li>
	<li>La segunda forma es asignar la variable como una propiedad del objeto global que en los navegadores web es el objeto window
<pre style="background-color: #fefbe4;" class=""><code>window.myGlobalVar = value;</code>
</pre>
</li>
	<li>La tercera forma es usar la variable directamente sin definirla antes. En este caso no importa si la variable está dentro o fuera de una funcion. Se considera implícitamente que es una variable global
<pre style="background-color: #fefbe4;" class=""><code>myGlobalVar = 'Hello world';</code>
</pre>
</li>
</ul>
Una buena manera de minimizar el uso de variables globales es almacenarlas en un único objeto global. Haciendo esto puedes mantener todas tus variables y funciones en un único lugar, reduciendo ampliamente el riesgo de colisiones de nombre.
<pre style="background-color: #ecfcea;">                        <code>
// Define your global object  
var myObj = {};  

// Add property (variable) to it  
myObj.myVar = 'Hello world';  


// Add method to it  
myObj.myFunctions = function() {  
  // Do cool stuff  
};  
              </code>
</pre>
Idealmente, un aplicación, librería, componente o widget define una unica variable global. Esta variable global deberia ser un objeto que es el namespace raiz de toda nuestra funcionalidad (funciones y variables)

El lenguaje javascript se diseñó con variables globales para hacer más facil a los principiantes empezar a programar con este lenguaje. Pero el efecto colateral es que es facil olvidar definir una variable y de esta forma crear un bug difícil de descubrir. Asi que hazte un favor, y evita el uso de variables globales siempre que sea posible.

¿Y tu que opinas? ¿Alguna idea más para comentar respecto al uso de variables globales o alternativas?. Esperamos vuestros comentarios.
<h2>Enlaces y más</h2>
<ul>
	<li><a href="http://yuiblog.com/blog/2006/06/01/global-domination/">Global Domination at Yahoo! User Interface Blog</a></li>
	<li><a href="http://www.svennerberg.com/2009/02/global-variables-in-javascript/"> Global variables in Javascript</a></li>
</ul>