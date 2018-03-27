---
ID: 2485
post_title: 'Sticky Footer: Como mantener el Footer en la parte inferior del navegador'
author: JuanMa Garrido
post_excerpt: |
  <p>
  Asi que, resumiendo… ¿cómo se va a comportar nuestro Footer
  cuando apliquemos esta tecnica?
  </p>
  <ul>
  <li>Que hay mucho contenido… pues la pagina hará su Scroll (como
  mandan los canones) y debajo de todo tendremos a nuestro Footer
  </li>
  </ul>
  <ul>
  <li>Que hay poco contenido… pues veremos toda nuestra pagina sin
  Scroll y ahí debajo bien situado, pegadito al borde de abajo,
  veremos a nuestro Footer saludando :-)
  </li>
  </ul>
  <p>
  Esta técnica nos viene de la mano de&nbsp;<a href=
  "http://ryanfait.com/" target="_blank">Ryan Fait&nbsp;</a>&nbsp;y
  lo unico que hay que hacer es añadir un DIV de mas.
  </p>
  <p>
  Es decir para una estructura HTML como esta…
  </p>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code><br /><br /><br />    </code>
  </pre>
  <div id="container">
  &nbsp;
  </div>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code> </code>
  </pre>
  <div id="header">
  …
  </div>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code> </code>
  </pre>
  <div id="”content”">
  …
  </div>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code><br /><br />      </code>
  </pre>
  <div class="push">
  &nbsp;
  </div>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code><br />    <strong>    <br /></strong></code>
  </pre>
  <div id="”footer”">
  …
  </div>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code>  <br /><br />  <br /><br /></code>
  </pre>
  <p>
  aplicaríamos este CSS …
  </p>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  <code><br />  * { margin: 0; }<br />  html, body { height: 100%; }<br />  /* El margin-bottom de container es el valor negativo de la altura del footer */ <br />  #container { min-height: 100%; height: auto !important; height: 100%; <br />               margin: 0 auto -4em;  }<br />  /* .push debe tener la misma altura que footer */<br />  #footer, .push { height: 4em; clear:both; }     <br /><br /></code>
  </pre>
  <p>
  Puedes ver&nbsp;<a href="http://ryanfait.com/sticky-footer/"
  target="_blank">un ejemplo</a>&nbsp;de esta tecnica de la mano
  del propio autor.&nbsp;
  </p>
  <p>
  ¿Y tu? ¿Conoces alguna otra técnica “definitiva” para solucionar
  este problema?
  </p>
  <p>
  Esperamos vuestros comentarios
  </p>
layout: post
permalink: >
  https://pixelovers.com/sticky-footer-mantener-footer-parte-inferior-navegador-862098/
published: true
post_date: 2010-08-24 09:02:00
---
<p style="text-align: left;">En la maquetación de nuestros sitios web nos encontramos muchas veces con que tenemos que solucionar un pequeño problema: necesitamos mantener el footer pegado al pie de la pagina sea como sea el contenido de esta.</p>
Este tipo de problema con el Footer tambien lo puedes encontrar por la red con el nombre de  “Sticky Footer “ (Pie de paginavpegajoso) y aunque hay varias soluciones por la red,  yo voy a compartir aquí una que me funciona muy bien. Y si algo te funciona, ¿para que cambiar? ¿No?

<!--more-->

Asi que, resumiendo… ¿cómo se va a comportar nuestro Footer cuando apliquemos esta tecnica?
<ul>
	<li>Que hay mucho contenido… pues la pagina hará su Scroll (como mandan los canones) y debajo de todo tendremos a nuestro Footer</li>
</ul>
<ul>
	<li>Que hay poco contenido… pues veremos toda nuestra pagina sin Scroll y ahí debajo bien situado, pegadito al borde de abajo, veremos a nuestro Footer saludando :-)</li>
</ul>
Esta técnica nos viene de la mano de <a href="http://ryanfait.com/" target="_blank">Ryan Fait </a> y lo unico que hay que hacer es añadir un DIV de mas.

Es decir para una estructura HTML como esta…
<pre class="lang:xhtml decode:true ">&lt;html&gt;
    &lt;head&gt;
        &lt;link rel="stylesheet" href="layout.css" ... /&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;div class="wrapper"&gt;
            &lt;p&gt;Your website content here.&lt;/p&gt;
            &lt;div class="push"&gt;&lt;/div&gt;
        &lt;/div&gt;
        &lt;div class="footer"&gt;
            &lt;p&gt;Copyright (c) 2008&lt;/p&gt;
        &lt;/div&gt;
    &lt;/body&gt;
&lt;/html&gt;</pre>
aplicaríamos este CSS …
<pre class="lang:css decode:true ">* {
  margin: 0; 
}
html, body {
  height: 100%;
}
.wrapper {
  min-height: 100%;
  height: auto !important;
  height: 100%;
  margin: 0 auto -4em;
}
.footer, .push {
  height: 4em;
}</pre>
Puedes ver <a href="http://ryanfait.com/sticky-footer/" target="_blank">un ejemplo</a> de esta tecnica de la mano del propio autor.

¿Y tu? ¿Conoces alguna otra técnica “definitiva” para solucionar este problema?

Esperamos vuestros comentarios