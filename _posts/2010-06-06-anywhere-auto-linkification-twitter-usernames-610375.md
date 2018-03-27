---
ID: 2478
post_title: 'Anywhere: Auto-linkification of Twitter usernames'
author: Jorge del Casar
post_excerpt: |
  <p>Como sab&eacute;is la funci&oacute;n T puede recibir como par&aacute;metro un selector el cual usar&aacute; la librer&iacute;a&nbsp;<a title="A pure-JavaScript CSS selector engine" href="http://sizzlejs.com/" target="_blank">Sizzle</a>&nbsp;para encontrar los elementos del DOM, es la misma librer&iacute;a que usa jQuery, as&iacute; que seguro que est&aacute;is familiarizados con este forma de encontrar elementos en el DOM. Si no le pasamos ning&uacute;n argumento a T tomar&aacute; todo el contenido del&nbsp;<var>body</var>&nbsp;de la p&aacute;gina para buscar.</p>
  <p>Con Linkify users podremos enlazar con el perfil de Twitter a todos usuarios que mencionemos en la p&aacute;gina de la forma: @nombreUsuaurio teniendo en cuenta la siguiente expresi&oacute;n regular:&nbsp;<var>/B[@&#65312;]([a-zA-Z0-9_]{1,20})b/g</var>, es decir,el s&iacute;mbolo '@' seguido de 1 a 20 caracteres alfanum&eacute;ricos incluyendo el '_'. Por lo tanto nombres como @pixelovers, @jorgecasar y @juanmaguitar son nombre de twitter v&aacute;lidos.</p>
  <p>Sabiendo esto simplemente podremos enlazar estos nombres utilizando el siguiente c&oacute;digo en Javascript:</p>
  <pre style="color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; margin: 8px;"><code>T.linkifyUsers();</code></pre>
  <p>Si queremos ser m&aacute;s espec&iacute;ficos y que solo busque en cierta parte de nuestra p&aacute;gina podemos llamar a la funci&oacute;n especificando un selector:</p>
  <pre style="color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; margin: 8px;"><code>T('#content').linkifyUsers();</code></pre>
  <p>Tambi&eacute;n es importante saber que la funci&oacute;n&nbsp;&nbsp;<var>linkifyUsers</var>&nbsp;puede recibir un objeto como argumento con las sugientes propiedades:</p>
  <ul>
  <li>className: Puedes especificar un nombre de clase alternativo. (En la documentaci&oacute;n)</li>
  <li>complete: Puedes a&ntilde;adir una llamada de callback a la finalizaci&oacute;n del autoenlazado (No se especifica en la documentaci&oacute;n)</li>
  </ul>
  <p>Un ejemplo especificando todas las formas de llamar a esta funci&oacute;n podr&iacute;a ser:</p>
  <pre style="color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; margin: 8px;"><code>T('#content').linkifyUsers({<br />   className:"twitterName",<br />   complete: function(){<br />      alert('LinkifyUsers done!');<br />   }<br />});</code></pre>
  <p>Creo que con esto podr&eacute;is hacer una primera toma de contacto con @Anywhere. Ya lo tienes implementado en tu sitio y quieres mostrarnos como lo has hecho. Deja un comentario explicandolo. Si has tenido problemas, preguntanos, entre todos podemos intentar encontrar la soluci&oacute;n.</p>
layout: post
permalink: >
  https://pixelovers.com/anywhere-auto-linkification-twitter-usernames-610375/
published: true
post_date: 2010-06-06 22:11:00
---
Ya os hablamos hace un par de semanas de @<a title="Anywhere: API Javascript de Twitter" href="http://pixelovers.com/anywhere-api-javascript-twitter-569267">Anywhere</a> (API Javascript de Twitter) y hoy queremos entrar en más detalles sobre la librería, para que la puedas implementar en tu web de forma sencilla y potente.

Por no hacer el artículo muy largo hablaremos de cada una de las funciones en artículos separados. Así, hoy trataremos uno de los métodos más sencillitos de la API @Anywhere. También quiero destacar que todos los ejemplos de código estarán dentro de la llamada de callback (T) como dijimos en el anterior artículo:
<pre><code>twttr.anywhere(function (T) {
  // Tu código aquí...
});</code></pre>
<!--more-->

Como sabéis la función T puede recibir como parámetro un selector el cual usará la librería <a title="A pure-JavaScript CSS selector engine" href="http://sizzlejs.com/" target="_blank">Sizzle</a> para encontrar los elementos del DOM, es la misma librería que usa jQuery, así que seguro que estáis familiarizados con este forma de encontrar elementos en el DOM. Si no le pasamos ningún argumento a T tomará todo el contenido del <var>body</var> de la página para buscar.

Con Linkify users podremos enlazar con el perfil de Twitter a todos usuarios que mencionemos en la página de la forma: @nombreUsuaurio teniendo en cuenta la siguiente expresión regular: <var>/\\B[@＠]([a-zA-Z0-9_]{1,20})\\b/g</var>, es decir,el símbolo <code>'@'</code> seguido de 1 a 20 caracteres alfanuméricos incluyendo el <code>'_'</code>. Por lo tanto nombres como @pixelovers, @jorgecasar y @juanmaguitar son nombre de twitter válidos.

Sabiendo esto simplemente podremos enlazar estos nombres utilizando el siguiente código en Javascript:
<pre style="color: #000000; font: normal normal normal 12px/1.5em \'Lucida Grande\', Helvetica, Arial, sans-serif; margin: 8px;"><code>T.linkifyUsers();</code></pre>
Si queremos ser más específicos y que solo busque en cierta parte de nuestra página podemos llamar a la función especificando un selector:
<pre style="color: #000000; font: normal normal normal 12px/1.5em \'Lucida Grande\', Helvetica, Arial, sans-serif; margin: 8px;"><code>T('#content').linkifyUsers();</code></pre>
También es importante saber que la función  <var>linkifyUsers</var> puede recibir un objeto como argumento con las sugientes propiedades:
<ul>
	<li>className: Puedes especificar un nombre de clase alternativo. (En la documentación)</li>
	<li>complete: Puedes añadir una llamada de callback a la finalización del autoenlazado (No se especifica en la documentación)</li>
</ul>
Un ejemplo especificando todas las formas de llamar a esta función podría ser:
<pre style="color: #000000; font: normal normal normal 12px/1.5em \'Lucida Grande\', Helvetica, Arial, sans-serif; margin: 8px;"><code>T('#content').linkifyUsers({
   className:"twitterName",
   complete: function(){
      alert('LinkifyUsers done!');
   }
});</code></pre>
Creo que con esto podréis hacer una primera toma de contacto con @Anywhere. Ya lo tienes implementado en tu sitio y quieres mostrarnos como lo has hecho. Deja un comentario explicandolo. Si has tenido problemas, preguntanos, entre todos podemos intentar encontrar la solución.