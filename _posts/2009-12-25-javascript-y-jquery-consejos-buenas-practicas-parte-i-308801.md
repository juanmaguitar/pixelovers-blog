---
ID: 2451
post_title: 'Javascript y jQuery: Consejos y Buenas Practicas (Parte I)'
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/javascript-y-jquery-consejos-buenas-practicas-parte-i-308801/
published: true
post_date: 2009-12-25 20:50:00
---
<p style="text-align: left;"><img class=" alignright" title="/app/uploads/sites/7/2009/12/308801-209198.jpg" src="/app/uploads/sites/7/2009/12/308801-209198.jpg" alt="/app/uploads/sites/7/2009/12/308801-209198.jpg" width="229" height="233" />jQuery es una de las librerias mas utilizadas por los desarrolladores FrontEnd por su versatilidad y facilidad de uso. En Pixelovers somos autenticos fans de esta libreria.</p>

Es por esto que queremos compartir con vosotros lo que consideramos que son unas buenas practicas a la hora de programar codigo Javascript ayudandonos de la libreria jQuery.

<!--more-->El objetivo de este compendio de buenas practicas es conseguir un codigo Javascript y jQuery lo mas limpio, claro y eficiente posible.

Los tips que aqui incluimos estan sacados de nuestra propia experiencia y de conclusiones interesantes que hemos ido encontrando por la red y que hemos acoplado a nuestro repertorio.

Como son muchos los puntos tratados y para no cargar el post con demasiada informacion vamos a dividir este compendio en 2 partes.

En esta primera parte hablaremos de normas generales a seguir que te ayudaran a crear un codigo mas claro y eficiente. En un segundo post hablaremos de como solucionar de forma eficiente problemas concretos que nos solemos encontrar en nuestros
desarrollos.

Y una vez dicho esto, vamos al lio...

<h3><strong>Aprenderse bien la librería.</strong></h3>

Para utilizar siempre la solución mas optimizada posible. No está de mas tener a mano una chuleta de jQuery o ir directamente a la <a href="http://docs.jquery.com/" target="_blank">documentacion oficial de jQuery</a>

<h3><strong>Utilizar librerias consolidadas, versatiles, con soporte y con proyecto de futuro.</strong></h3>

Por ejemplo jQuery como librería principal y <a href="http://flowplayer.org/tools/index.html" target="_blank">jQuery Tools</a> y <a href="http://jqueryui.com/" target="_blank">jQuery UI</a> como liberias adicionales de efectos

<h3><strong>Trabajar en archivos separados.</strong></h3>

Mejor crear JS's diferentes para cada funcionalidad separable de nuestro site y luego utilizar algun sistema que junte todos estos JS's en uno final (comprimido y ofuscado)

<h3><strong>Javascript no intrusivo.</strong></h3>

Nunca depender de JS en la medida de lo posible. Si está desactivado el javascript o
falla, que la pagina muestre un aspecto normal. Javascript es una mejora, no un sistema de seguridad.

<h3><strong>Optimiza el codigo haciendo pruebas de rendimiento.</strong></h3>

Con Firebug podemos medir el tiempo que tarda una funcion (o trozo de codigo) en ejecutarse:

<pre class="lang:js decode:true">  console.time('native');
  var l = array.length;
  for (var i=0;i&lt;l; i++) {
    array[i] = i;
  }
  console.timeEnd('native');
</pre>

<h3><strong>Comprimir el codigo al final.</strong></h3>

Al comprimir el codigo el archivo JS que tendrá que bajarse el usuario será de
menor tamaño, aunque hay que valorar el rendimiento final ya que por el contrario el navegador tendrá que realizar el proceso adicional de descomprimir el codigo antes de
ejecutarlo.Para comprimir el codigo disponemos de herramientas, tipo <a href="http://yuilibrary.com/projects/yuicompressor/wiki" target="_blank">YUI Compressor</a> aunque hay <a href="http://www.cristalab.com/tips/comprimir-y-ofuscar-archivos-.js-de-javascript-c52395l/" target="_blank">muchas mas</a>

<h3><strong>El marcado semantico y accesible viene primero.</strong></h3>

No adaptar el marcado para facilitar el JS sino que sea el JS el que se adapte al marcado. Con ID’s, herencia, y clases podemos acceder a cualquier elemento y asignarle funcionalidades

<em>Marcado malo:</em>

<pre class="lang:xhtml decode:true">&lt;table&gt;
    &lt;tbody&gt;
        &lt;tr&gt;
            &lt;td&gt;First Option&lt;/td&gt;
            &lt;td&gt;First option description&lt;/td&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
            &lt;td&gt;Second Option&lt;/td&gt;
            &lt;td&gt;Second option description&lt;/td&gt;
        &lt;/tr&gt;
    &lt;/tbody&gt;
&lt;/table&gt;</pre>

<em>Marcado bueno:</em>

<pre class="lang:xhtml decode:true ">&lt;dl&gt;
    &lt;dt&gt;First Option&lt;/dt&gt;
    &lt;dd&gt;First option description&lt;/dd&gt;
    &lt;dt&gt;Second Option&lt;/dt&gt;
    &lt;dd&gt;Second option description&lt;/dd&gt;
&lt;/dl&gt;</pre>

<em>Marcado bueno y listo para JS:</em>

<pre class="lang:xhtml decode:true ">&lt;dl id="OptionList"&gt;
    &lt;dt&gt;First Option&lt;/dt&gt;
    &lt;dd&gt;First option description&lt;/dd&gt;
    &lt;dt&gt;Second Option&lt;/dt&gt;
    &lt;dd&gt;Second option description&lt;/dd&gt;
&lt;/dl&gt;</pre>

<h3><strong>Encapsular lo maximo posible el codigo.</strong></h3>

Esto significa agrupar todas las funciones comunes dentro de una funcion padre, asi acotamos el contexto de cada funcionalidad (objeto si hace falta)

Ejemplo:

<pre class="lang:js decode:true">  var mySite = new Object();

        mySite = {

                var1 : 1,
                var2 : 2,
                valorCalculado,

                init : function() {
                        // aqui hago varias cosas
                        this.valorCalculado = "hola";
                        this.funcionalidad1();
                },

                funcionalidad1 : function() {
                        // aqui desarrollo una funcionalidad concreta

                }
        }

        // desde fuera (o desde otro objeto) puedo llamar a las funciones de este objecto
        mySite.funcionalidad1();
</pre>

<h3><strong>Elimina consultas innecesarias</strong>.</h3>

Podemos ahorrarnos la llamada al <code>$(document).ready()</code> poniendo los tags <code>script</code> justo antes de que se cierre el tag <code>body</code>

<h3>`eval` is evil</h3>

Evitar el uso de eval. Problemas de seguridad. Mas info de por qué puede ser un problema <a href="http://blogs.msdn.com/ericlippert/archive/2003/11/01/53329.aspx" target="_blank">aqui</a>. Una posible alternativa al uso de EVAL puede ser <a href="http://wiki.ecmascript.org/doku.php?id=es3.1:json_support" target="_blank">JSON.parse</a> o <a href="http://beebole.com/en/blog/general/sandbox-your-cross-domain-jsonp-to-improve-mashup-security/" target="_blank">JSONP</a>   Y hasta aqui la primera parte del asunto... ¿Que te han parecido los puntos aqui comentados? ¿Estas de acuerdo? ¿Algun punto que creas que falta en esta lista?

<h2>Enlaces y más</h2>

<ul>
    <li><a href="http://jquery.com/" target="_blank">jQuery</a></li>
    <li><a href="http://getfirebug.com/" target="_blank">Firebug</a></li>
    <li><a href="http://flowplayer.org/tools/index.html" target="_blank">jQuery Tools</a></li>
    <li><a href="http://jqueryui.com/" target="_blank">jQuery UI</a></li>
    <li><a href="http://yuilibrary.com/projects/yuicompressor/wiki" target="_blank">YUI Compressor</a></li>
</ul>