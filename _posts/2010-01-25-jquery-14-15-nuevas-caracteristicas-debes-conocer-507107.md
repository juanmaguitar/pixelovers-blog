---
ID: 2468
post_title: 'jQuery 1.4: 15 nuevas características que debes conocer'
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/jquery-14-15-nuevas-caracteristicas-debes-conocer-507107/
published: true
post_date: 2010-01-25 15:30:00
---
Estamos preparando un análisis de la nueva versión jQuery 1.4. Pero mientras la probamos y estudiamos las nuevas funcionalidades, leo en <a title="jQuery 1.4: 15 nuevas características que debes conocer " href="http://www.webintenta.com/jquery-1-4-15-nuevas-caracteristicas-que-debes-conocer.html" target="_blank">Intenta</a> un interesante artículo sobre <a lang="en_EN" title="jQuery 1.4 Released: The 15 New Features you Must Know" href="http://net.tutsplus.com/tutorials/javascript-ajax/jquery-1-4-released-the-15-new-features-you-must-know/" target="_blank" rel="nofollow" hreflang="en_EN">jQuery 1.4 Released: The 15 New Features you Must Know</a>. ¿Conoces ya estas nuevas características?

<!--more-->
<ol>
	<li>Pasar atributos a <strong>jQuery</strong>(...)  – `<a title="jQuery() - jQuery API" href="http://api.jquery.com/jQuery/#jQuery2" target="_blank">jQuery</a>( html, propiedades )`</li>
	<li>¡Tódo <strong>"hasta que"</strong>!  – `.<a title=".nextUntill() - jQuery API" href="http://api.jquery.com/nextUntil/" target="_blank">nextUntil</a>([ selector ])`, `.<a title=".prevUntil() - jQuery API" href="http://api.jquery.com/prevUntil/" target="_blank">prevUntil</a>([ selector ])` y `.<a title=".parentsUntil() - jQuery API" href="http://api.jquery.com/parentsUntil/" target="_blank">parentsUntil</a>([ selector ])`</li>
	<li>Enlazar <strong>múltiples</strong> controladores de <strong>eventos</strong> – `.<a title=".bind() - jQuery API" href="http://api.jquery.com/bind/" target="_blank">bind</a>( eventos )`</li>
	<li>Per-property-easing (Facilitando por propiedad) – `.<a title=".animate() - jQuery API" href="http://api.jquery.com/animate/#per-property-easing" target="_blank">animate</a>(propiedades, opciones)`</li>
	<li>¡Nuevos <strong>eventos live</strong>! – `.<a title=".live() - jQuery API" href="http://api.jquery.com/live/" target="_blank">live</a>("submit|change|focusin|focusout", controlador)`</li>
	<li>Control del <strong>contexto</strong> de una función – `<a title="jQuery.proxy() - jQuery API" href="http://api.jquery.com/jQuery.proxy/" target="_blank">jQuery.proxy</a>(función, contexto)`</li>
	<li><strong>Demora</strong> una cola de Animación – `.<a title=".delay() - jQuery API" href="http://api.jquery.com/delay/" target="_blank">delay</a>(duración, [ nombre de la cola ])`</li>
	<li>Comprobar si un elemento <strong>tiene algo</strong> – `.<a title=".has() - jQuery API" href="http://api.jquery.com/has/" target="_blank">has</a>(selector)` y `<a title="jQuery.contains() - jQuery API" href="http://api.jquery.com/jQuery.contains/" target="_blank">jQuery.contains</a>(contenedor, contenido)`</li>
	<li><strong>Desenvolver</strong> elementos – `<a title=".unwrap() - jQuery API" href="http://api.jquery.com/unwrap/" target="_blank">.unwrap()</a>`</li>
	<li><strong>Eliminar</strong> elementos <strong>sin borrar datos</strong> – `.<a title=".detach() - jQuery API" href="http://api.jquery.com/detach/" target="_blank">detach</a>([ selector ])`</li>
	<li>Mejoras en <strong>index</strong>(...) – `.<a title=".index() - jQuery API" href="http://api.jquery.com/index/" target="_blank">index</a>(selector)`</li>
	<li>Los métodos de manipulación DOM aceptan "<strong>callbacks</strong>":
<ul>
	<li>`<a title=".after() - jQuery API" href="http://api.jquery.com/after" target="_blank">after</a>`</li>
	<li>`<a title=".before() - jQuery API" href="http://api.jquery.com/before" target="_blank">before</a>`</li>
	<li>`<a title=".append() - jQuery API" href="http://api.jquery.com/append" target="_blank">append</a>`</li>
	<li>`<a title=".prepend() - jQuery API" href="http://api.jquery.com/prepend" target="_blank">prepend</a>`</li>
	<li>`<a title=".addClass() - jQuery API" href="http://api.jquery.com/addClass" target="_blank">addClass</a>`</li>
	<li>`<a title=".toggleClass() - jQuery API" href="http://api.jquery.com/toggleClass" target="_blank">toggleClass</a>`</li>
	<li>`<a title=".removeClass() - jQuery API" href="http://api.jquery.com/removeClass" target="_blank">removeClass</a>`</li>
	<li>`<a title=".wrap() - jQuery API" href="http://api.jquery.com/wrap" target="_blank">wrap</a>`</li>
	<li>`<a title=".wrapAll() - jQuery API" href="http://api.jquery.com/wrapAll" target="_blank">wrapAll</a>`</li>
	<li>`<a title=".wrapInner() - jQuery API" href="http://api.jquery.com/wrapInner" target="_blank">wrapInner</a>`</li>
	<li>`<a title=".val() - jQuery API" href="http://api.jquery.com/val" target="_blank">val</a>`</li>
	<li>`<a title=".text() - jQuery API" href="http://api.jquery.com/text" target="_blank">text</a>`</li>
	<li> `<a title=".replaceWith() - jQuery API" href="http://api.jquery.com/replaceWith" target="_blank">replaceWith</a>`</li>
	<li>`<a title=".css() - jQuery API" href="http://api.jquery.com/css" target="_blank">css</a>`</li>
	<li>`<a title=".attr() - jQuery API" href="http://api.jquery.com/attr" target="_blank">attr</a>`</li>
	<li>`<a title=".html() - jQuery API" href="http://api.jquery.com/html" target="_blank">html</a>`</li>
</ul>
</li>
	<li>Determinar el <strong>tipo del objeto</strong> – `<a title="jQuery.isPlainObject() - jQuery API" href="http://api.jquery.com/jQuery.isPlainObject/" target="_blank">jQuery.isPlainObject</a>(objeto)` y `<a title="jQuery.isEmptyObject() - jQuery API" href="http://api.jquery.com/jQuery.isEmptyObject/" target="_blank">jQuery.isEmptyObject</a>(objeto)`</li>
	<li>Mejoras en <strong>Closest</strong>(...) – `.<a title=".closest() - jQuery API" href="http://api.jquery.com/closest/" target="_blank">closest</a>(selector, [ contexto ])`</li>
	<li>Nuevos eventos! <strong>focusIn</strong> y <strong>focusOut</strong> – `.<a title=".focusin() - jQuery API" href="http://api.jquery.com/focusin/" target="_blank">focusin</a>(manejador)` y `.<a title=".focusout() - jQuery API" href="http://api.jquery.com/focusout/" target="_blank">focusout</a>(manejador)`</li>
</ol>