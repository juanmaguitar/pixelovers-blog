---
ID: 2374
post_title: >
  Limpieza de floats en Internet Explorer
  7
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/limpieza-floats-internet-explorer-7-8498/
published: true
post_date: 2007-02-25 00:00:00
---
<img src="http://ben-ward.co.uk/media/splashes/ie7.splash.png" alt=" " align="right" />Durante los últimos meses, Microsoft nos ha tenido en vilo ( sobretodo a los desarrolladores web ), pendientes del soporte a la especificación de CSS que tendría su nuevo navegador, <a href="http://www.microsoft.com/windows/ie/default.mspx">Internet Explorer 7</a> . Después de unos 5 años sin publicar una nueva versión, parecía que la cosa iba a salir "fina": <a href="http://blogs.msdn.com/ie/archive/2006/02/02/523679.aspx">El modelo de caja se ha implementado correctamente</a>, se soportan propiedades tan útiles como min/max-width, ... ¿¡Se acabaron las reglas sólo para IE!? No...

<!--more-->

Por poner un ejemplo, no se han implementado los pseudo-elementos :before y :after. ¿Trivial? Para nada. Entre otros muchos usos, como la inclusión de elementos que afecten a la presentación de ciertos bloques ( comillas antes y después de elementos cite, pipelines después de listas de enlaces horizontales... ) o la limpieza de floats a través del <a href="http://www.positioniseverything.net/easyclearing.html">easy clearing method</a> quedan totalmente inutilizada.

El antiguo hack para explorer es ignorado por el nuevo IE y además, al carecer éste de soporte para :before, tampoco la regla genérica funciona. Esto se traduce en un montón de sitios descuajeringados: el anterior método permitía que aquellos contenedores que tuvieran hijos flotantes obtuvieran una altura correcta, correspondiente a su hijo más alto.

Cuando ya había perdido toda esperanza de disponer, de nuevo, de un método lo más genérico posible que permitiera disponer de un marcado "limpio" para conseguir el deseado efecto... me encontré con el artículo de Roger Johansson, <a href="http://www.456bereastreet.com/archive/200603/new_clearing_method_needed_for_ie7/#content-secondary">New clearing method needed for IE7?</a>, en que justo se plantea esto mismo, y en el que, a través de la discusión generada por sus lectores, consigue llegar a una versión funcional para IE y que hace uso exclusivamente de CSS.

<strong>La solución:</strong>
<pre class="font-size:15 toolbar:1 whitespace-before:1 whitespace-after:1 lang:css decode:true">.clearfix:after {
  content:".";
  display:block;
  height:0;
  clear:both;
  visibility:hidden;
}
.clearfix {display:inline-block;}
/* Hide from IE Mac */
.clearfix {display:block;}
/* End hide from IE Mac */
</pre>
Con un pequeño añadido para IE 6, que se podría implementar de esta forma:
<div class="codigo">
<pre class="font-size:15 toolbar:1 whitespace-before:1 whitespace-after:1 lang:css decode:true ">* html .clearfix {height:1px;}
</pre>
</div>
<strong>Información adicional:</strong>
<ul>
	<li>La técnica original: <a href="http://www.positioniseverything.net/easyclearing.html">How To Clear Floats Without Structural Markup</a></li>
	<li><a href="http://www.tanfa.co.uk/archives/show.asp?var=300">EasyClearing, the Aslett/PIE way is NOT broken in IE7!</a></li>
	<li><a href="http://www.stuffandnonsense.co.uk/archives/clearing_floats_without_structural_markup_in_ie7.html">Clearing floats without structural markup in IE7</a></li>
</ul>