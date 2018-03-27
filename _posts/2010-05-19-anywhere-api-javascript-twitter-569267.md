---
ID: 2475
post_title: 'Anywhere: API Javascript de Twitter'
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/anywhere-api-javascript-twitter-569267/
published: true
post_date: 2010-05-19 10:35:00
---
Hace 1 mes se realizó el <a href="http://hipertextual.com/archivo/2010/01/chirp-la-conferencia-para-desarrolladores-de-twitter/" target="_blank">Chirp</a>, la conferencia oficial para desarrolladores de Twitter. Y en ella se presentaron varias novedades en torno al mundo Twitter. Entre ellas, una nueva página para desarolladores de Twitter: <a title="Documentación API de Twitter " href="http://dev.twitter.com/" target="_blank">dev.twitter.com</a>, donde podemos ver nuevas herramientas.

En la que nos vamos a centrar, por ser la más cercana a la temática del blog es <a title="Integrate Twitter seamlessly into your   site with just a few lines of Javascript" href="http://dev.twitter.com/anywhere/" target="_blank">@Anywhere</a>.

<!--more-->@Anywhere es una API de Javascript que te permite integrar Twitter con tu sitio en unas pocas lineas de Javascript. Antes de empezar a utilizarla has de registrarte como desarrollador para que te faciliten una API key, para ello tienes el formulario de <a title="Registro de una   aplicación Anywhere" href="http://dev.twitter.com/anywhere/apps/new" target="_blank">registro de un aplicación Anywhere</a>. Tras ese paso, solo debemos añadir en las cabeceras de nuestra web la llamada a este script:
<pre class="lang:xhtml decode:true">&lt;script src="http://platform.twitter.com/anywhere.js?id=YOUR_API_KEY&amp;v=1" type="text/javascript"&gt;&lt;/script&gt;</pre>
Una vez añadido este script la foma de inicializar @Anywhere es la siguiente:
<pre class="lang:js decode:true ">twttr.anywhere(function (T) {
  // Tu código aquí...
});</pre>
Como ves en realidad llamamos a una función y le pasamos una función de callback con un parámetro T (podéis llamarlo como queráis). La cual se ejecutará una vez cargado el script de Twitter @Anywhere. Con esta API, de momento, puedes realizar lo siguiente:
<ul>
	<li><a title="Auto-linkification of Twitter usernames" href="http://pixelovers.com/anywhere-auto-linkification-twitter-usernames-610375">Autoenlazar nombres de usuario de Twitter</a></li>
	<li><a title="Anywhere: Hovercards" href="http://pixelovers.com/anywhere-hovercards-633853">Hovercards</a></li>
	<li>Botones de Follow</li>
	<li>Caja de Tweet</li>
	<li>Login de usuario</li>
</ul>
Os invito a que la probéis.