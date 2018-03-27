---
ID: 3891
post_title: 'SweetAlert2: El mejor sustituto de los alert'
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/sweetalert2-el-mejor-sustituto-de-los-alert/
published: true
post_date: 2017-05-06 19:13:02
---
<a href="https://limonte.github.io/sweetalert2/" target="_blank"><img class="alignnone size-large wp-image-3919" src="https://juanmaguitar.com/app/uploads/sites/7/2017/05/SweetAlert-2-dark-1024x512.png" alt="" width="700" height="350" /></a>

<a href="https://limonte.github.io/sweetalert2/" target="_blank">SweetAlert2</a> es una librería que nos ofrece un reemplazo bonito, responsive, accesible (<a href="https://www.w3.org/WAI/intro/aria">WAI-ARIA</a>) y configurable para los típicos <code>alert</code>

<!--more-->

Es decir, que en vez de mostrar nuestros mensajes <em>popup</em> asi...

<iframe width="100%" height="100" src="//jsfiddle.net/juanma/LdLa5cv5/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Los podemos mostrar así...
<iframe width="100%" height="400" src="//jsfiddle.net/juanma/kkjd1mea/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Mucho mejor (más claros, más bonitos,...) los mensajes con SweetAlert2, ¿no?
<h2>¿Qué necesitamos para poder utilizar SweetAlert2 en nuestro proyecto?</h2>
Para utilizar <a href="https://github.com/limonte/sweetalert2" target="_blank">SweetAlert2</a> en nuestro proyecto necesitamos cargar 3 cosas:
<ul>
 	<li>El <a href="https://cdn.jsdelivr.net/sweetalert2/6.5.6/sweetalert2.js">archivo .js de SweetAlert2</a></li>
 	<li>El <a href="https://cdn.jsdelivr.net/sweetalert2/6.5.6/sweetalert2.css">archivo .css de SweetAlert2</a></li>
</ul>
Los podemos descargar desde <a href="https://www.jsdelivr.com/projects/sweetalert2" target="_blank">jsdelivr.com/sweetalert2 </a> <span class="mobile-hidden">o </span><a href="https://cdnjs.com/libraries/limonte-sweetalert2" target="_blank">cdnjs.com/limonte-sweetalert2 </a> a nuestro proyecto y cargarlos en nuestro HTML desde su ubicación

También podemos instalar estos archivos con bower
<pre class="center">bower install sweetalert2</pre>
...y luego cargarlos desde <code>bower_components</code>

O los podemos cargar directamente desde un CDN
<pre class="lang:xhtml decode:true">&lt;!-- These belongs to the HTML file where you want C3 to work - put these lines into your &lt;head&gt; tag --&gt;
&lt;script type="text/javascript" src="https://cdn.jsdelivr.net/sweetalert2/6.5.6/sweetalert2.min.js"&gt;&lt;/script&gt;
&lt;link href="https://cdn.jsdelivr.net/sweetalert2/6.5.6/sweetalert2.min.css" rel="stylesheet" type="text/css"&gt;
</pre>
<h2>Tipos de Mensajes</h2>
Podemos mostrar estos 5 tipos de mensajes

<iframe width="100%" height="450" src="//jsfiddle.net/juanma/u23nafgz/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
<h2>¿Cómo lo utilizo en mi código?</h2>
Al cargar los archivos de esta libreria, tendrás disponible la función global <code>swal</code> a la que podrás llamar pasándole <a href="https://github.com/limonte/sweetalert2#configuration" target="_blank">un objeto de configuración.</a>

<iframe width="100%" height="450" src="//jsfiddle.net/juanma/utpgoL49/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

Esta función devolverá una promesa que podemos concatenar con diferentes <code>then</code> o <code>catch</code> para realizar acciones según la respuesta del usuario al mensaje

<iframe width="100%" height="450" src="//jsfiddle.net/juanma/46pu4njb/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
<h2>¿Y para utilizarlo en mi aplicación Angular 1.x?</h2>
Para angular 1.x hay un <code>wrapper</code> llamado <a href="https://github.com/oitozero/ngSweetAlert" target="_blank">ngSweetAlert</a> que al cargarlo en nuestro proyecto nos deja disponible el modulo <code>oitozero.ngSweetAlert</code> que podemos poner como dependencia de nuestro modulo principal.

Con esto tendremos disponible el factory <code>SweetAlert</code> que podremos <em>inyectar</em> en nuestros controladores para acceder a su método <code>swal</code> que funciona tal y como hemos explicado antes
<pre class="lang:js decode:true ">angular.module('mainApp',['oitozero.ngSweetAlert'])
  .controller('mainController', function($scope, SweetAlert) {
    $scope.clickMeToShowMessage = function() {
      SweetAlert.swal({
        type: 'info',
        title: 'Hey, this is important',
        text: 'You rocks!',
    	})
    }
  })</pre>
&nbsp;

<iframe width="100%" height="450" src="//jsfiddle.net/juanma/78fgo5dy/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>