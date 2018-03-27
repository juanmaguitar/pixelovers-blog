---
ID: 2390
post_title: 'JQuery 1.1.3: más rápido, más estable, igual de ligero'
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/jquery-113-mas-rapido-mas-estable-igual-ligero-15801/
published: true
post_date: 2007-07-02 23:55:42
---
<img class="ma-m alignnone" title="15801-15085.jpg" src="/app/uploads/sites/7/2007/07/15801-15085.jpg" alt="15801-15085.jpg" width="255" height="81" align="left" /> <strong>JQuery</strong>, <a href="http://pixelovers.com/p/frameworks-javascript-ajax-12083">mi framework javascript preferido</a>, <a href="http://jquery.com/blog/2007/07/01/jquery-113-800-faster-still-20kb/">se ha actualizado hoy a la versión 1.1.3</a>. En esta nueva versión <strong>aseguran haber mejorado la velocidad de parseo del DOM en más de un 800%</strong>, convirtiéndose en el framework que mejores resultados da sobre el navegador (aún) mayoritario: IE.

<!--more-->En las pruebas de rendimiento que se han realizado sobre la suite de pruebas <a href="http://mootools.net/slickspeed/"><strong>SlickSpeed</strong></a> los resultados son sorprendentes, ya no sólo cuando comparamos el rendimiento de esta nueva versión sobre sus principales alternativas ( Prototype, mootools, Dojo... ), si no sobretodo cuando comparamos con la anterior versión de la misma librería.
<table border="0" width="100%">
<thead>
<tr>
<th>Navegador</th>
<th>jQuery 1.1.2</th>
<th>jQuery 1.1.3</th>
<th>% Mejora</th>
</tr>
</thead>
<tbody>
<tr>
<th>IE 6</th>
<td>4890ms</td>
<td>661ms</td>
<th>740%</th>
</tr>
<tr>
<th>Firefox 2</th>
<td>5629ms</td>
<td>567ms</td>
<th>993%</th>
</tr>
<tr>
<th>Safari 2</th>
<td>3575ms</td>
<td>475ms</td>
<th>753%</th>
</tr>
<tr>
<th>Opera 9.1</th>
<td>3196ms</td>
<td>326ms</td>
<th>980%</th>
</tr>
<tr>
<td colspan="3" align="right">Mejora media:</td>
<th>867%</th>
</tr>
</tbody>
</table>
Algunas de las mejoras y novedades que encontraremos en esta actualización:
<ul>
	<li>Nuevos selectores</li>
	<li>Renderización de las animaciones más rápidas y suaves</li>
	<li>Mejoras en el manejo de eventos</li>
	<li>Posibilidad de usar múltiples ".is()"</li>
	<li>Implementación de Jquery.browser.version para saber qué navegador y versión está usando el usuario</li>
</ul>
En el mismo post nos avanzan algunos planes de futuro bastante jugosos. Particularmente me ha parecido interesante la iniciativa de Paul Bakaus de montar una <a href="http://dev.jquery.com/browser/trunk/plugins/ui"><strong>JQuery UI</strong></a>, una completa librería que implementará Draggables, Droppables, Sortables, Resizables... todo lo que hasta ahora sólo era posible hacer con plugins como <a href="http://interface.eyecon.ro/"><strong>Interface</strong></a>.

Estaremos atentos a las novedades.