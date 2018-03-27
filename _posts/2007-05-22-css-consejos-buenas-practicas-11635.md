---
ID: 2383
post_title: 'CSS: Consejos y buenas prácticas'
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/css-consejos-buenas-practicas-11635/
published: true
post_date: 2007-05-22 00:00:00
---
<img title="11635-12987.jpg" src="/app/uploads/sites/7/2007/05/11635-12987.jpg" alt="11635-12987.jpg" width="177" height="200" align="right" />Justo esta semana pasada empezamos en la oficina una fase de revisión de marcado y de css de una web bastante grande, y en la que participaremos varios desarrolladores. Ésto nos ha obligado a acordar algunas convenciones a la hora de trabajar, en cuanto a codificación, estructura, nomenclatura... y a plasmarlas por escrito para que todo el equipo, ahora y en el futuro, pueda consultarlas en un documento de referencia.

En esa guía, además, hemos tratado de incluir algunas recomendaciones de "buenas prácticas" entre las que voy a tratar de resumir algunas de ellas, las más importantes a mi entender.<!--more-->
<h2>Consideraciones previas</h2>
<ul>
	<li><strong>Asegúrate de definir siempre un DOCTYPE, ¡y úsalo!</strong>
De otra forma, el navegador entrará en el <a href="http://sigt.net/archivo/que-pasa-en-el-modo-chapuzas-quirks-mode.xhtml"><em>Quirk Mode</em></a>, aumentando el tiempo de renderizado y provocando algunos desajustes en cuanto a la interpretación de ciertas propiedades CSS.</li>
</ul>
<ul>
	<li><strong>Evita usar estilos incrustados o elementos presentacionales en tu marcado.</strong>
Reserva etiquetas &lt;strong&gt; y &lt;em&gt; para aquellos textos que realmente requieran ser enfatizados, y nada de estilos incrustados con styles dentro de tu código HTML. Los estilos SIEMPRE separados del contenido.</li>
</ul>
<ul>
	<li><strong>Valida tu código a medida que codifiques.</strong>
Te evitarás muchos dolores de cabeza al final del proceso. Gran parte de problemas de renderizado son consecuencia de marcado no válido.De igual forma, asegúrate de que esa propiedad tan molona de CSS que estás usando sea estándar y no exclusiva para IE.</li>
</ul>
<ul>
	<li><strong>Resetea las propiedades CSS para eliminar diferencias entre navegadores desde el principio.</strong>
Es muy buena idea empezar tu hoja de estilos general con una serie de declaraciones que reseteen propiedades como los margin, los padding y los border de los elementos más comunes. Echa un vistazo al <a href="http://developer.yahoo.com/yui/reset/">reset.css que ofrece la librería de Yahoo</a> o al <a href="http://www.torresburriel.com/weblog/2007/03/11/reset-css-o-como-empezar-de-nuevo-manejando-estilos/">artículo de Daniel</a> que lo comenta más a fondo.</li>
</ul>
<ul>
	<li><strong>Usa el navegador más moderno y con mejor soporte de los estándares durante el desarrollo y el testeo, antes de probarlo en los navegadores "problemáticos", y no al revés</strong>.
Puede que no sigas esta norma y no tengas ningún problema, pero si testeas primero en IE6 tienes muchas probabilidades de terminar con un CSS lleno de hacks, o peor, de terminar metiendo "hacks" para los navegadores que sí cumplen los estándares. Tu objetivo tiene que ser conseguir el código y el CSS más limpio y cross-browser posible y, créeme, la mejor manera de conseguirlo es ésta.</li>
</ul>
<ul>
	<li><strong>Usa el menor número de archivos posible. </strong>Es mejor un sólo archivo de 30Kb que 3 archivos de 10Kb.Piensa que para cada uno de los archivos estáticos enlazados desde un documento HTML ( CSS, Javascript, imágenes, etc... ), éste debe realizar una conexión HTTP y lanzar una petición, con sus correspondientes cabeceras, cookies si las hubiere... todo suma y al final, tanto en tamaño como en tiempo de descarga, penalizarás al usuario.</li>
</ul>
<h2>Estructura, nomenclatura y otras yerbas</h2>
<ul>
	<li><strong>Sea cual sea, trata de ser consistente en el idioma usado cuando codifiques, tanto en los nombres como en los comentarios. </strong>
Esto toma especial importancia en grandes equipos o con personas de diferentes procedencias.</li>
</ul>
<ul>
	<li><strong>Usa siempre minúsculas y guiones o guiones bajos para separar palabras. </strong>
Algunos navegadores antiguos han demostrado tener problemas con mayúsculas-minúsculas, así que ve a los seguro.</li>
</ul>
<ul>
	<li><strong>Sé descriptivo en los nombres y huye de usar aquellos que se refieran a la apariencia de los elementos.</strong>
Mejor usar un #main-product que un #m-prod, y nada de clases del tipo .centered, .red... O te encontrarás con que cuando toque cambiar el color o la alineación de contenidos, tendrás que ir modificando las clases de cada elemento... ¡¿Dónde están entonces las ventajas de gestionar el diseño desde una hoja de estilos?!</li>
</ul>
<ul>
	<li><strong>Trata de sacar partido de la cascada</strong>
Evita crear demasiadas instancias siempre que no sean imprescindibles. Por ejemplo
<pre class="lang:css decode:true">#main_table { width:100% }
#main_table th { font-weight:bold; text-align:center }
#main_table td { text-align:right; font-size:1.5em }

</pre>
es mejor que
<pre class="lang:css decode:true">#main_table { width:100% }
.cell_header { font-weight:bold; text-align:center }
.cell_contents { text-align:right; font-size:1.5em }

</pre>
Además, los nombres pueden ayudar a ubicar un elemento dentro de la jerarquía de capas. Por ejemplo, posiblemente sea mucho más práctico usar #header_logo que no #logo a secas.</li>
</ul>
<ul>
	<li><strong>Usa criterios consistentes para organizar las declaraciones de estilos dentro de tu CSS.</strong>
Puedes decidir enunciar las declaraciones según su orden de aparición dentro del código, o agruparlas por el tipo de elemento al que se refieren ( listados, titulares, imágenes... ) Sea cual sea, <strong>que éste sea constante</strong>, o te vas a volver loco cuando la hoja de estilos adquiera un tamaño importante...</li>
</ul>
<ul>
	<li><strong>Trata de comprimir lo más posible el archivo resultante.</strong>
Ésto lo puedes conseguir no sólo eliminando espacios y saltos de linea sobrantes en tu hoja de estilos mediante <a href="http://www.cdburnerxp.se/cssparse/css_optimiser.php">alguno de los compresores gratuítos disponibles en internet</a>, si no <a href="http://httpd.apache.org/docs/2.0/mod/mod_deflate.html">configurando tu Apache para que sirva comprimidos los archivos determinados tipos de archivos</a> ( HTML, Javascript, CSS ). Piensa que algunos archivos estáticos se enlazan desde todas ( o casi ) las páginas de tu site. Puedes ahorrarte mucho tráfico con esto.</li>
</ul>
<ul>
	<li><strong>Evita usar comillas alrededor de las llamadas a imágenes.</strong>
Todos los navegadores lo entenderán correctamente. Con comillas, en cambio, tendrás problemas en IE para Mac. Pudiendo tenerlos a todos contentos... ¿porqué no hacerlo?</li>
</ul>
<h2>Consideraciones adicionales</h2>
<ul>
	<li><strong>En el 90% de los casos, la solución más sencilla será la que menos problemas dé entre navegadores.  <acronym title="Keep It Simple Stupid">KISS</acronym>.</strong>
<img title="11635-12988.jpg" src="/app/uploads/sites/7/2007/05/11635-12988.jpg" alt="11635-12988.jpg" width="200" height="197" align="right" />
Normalmente podrás usar varias combinaciones para conseguir el mismo
efecto visual. Trata de encontrar la combinación más simple de
elementos y propiedades. Mezcla paddings en el contenedor e hijos,
margins e indentaciones negativos, y suma algunos posicionamientos absolutos en
elementos anidados y tendrás los ingredientes perfectos para un
bonito... caos.</li>
</ul>
<ul>
	<li><strong>Los hacks son la última solución.</strong>
Invierte hoy 30 minutos más en encontrar la alternativa cross-browser y
ahórrate horas la semana que viene tratando de modificar tu hoja de
estilos.</li>
</ul>
<ul>
	<li>Una mala y una buena noticia: ¿La mala? No te asustes, pero sí, <strong>algunos navegadores tienen bugs de render, sin explicación ni justificación alguna</strong>. ¿La buena? En sitios como <a href="http://www.positioniseverything.net/">PositionIsEverything</a> han identificado muchas de ellas y pueden ahorrarte algunos quebraderos de cabeza. Un simple e inocuo position:relative; o un zoom:1; solucionan muchos de estos bugs.</li>
</ul>
<ul>
	<li>En la línea de lo que comentábamos al principio respecto a la cantidad de archivos CSS a enlazar desde tu página, <strong>hay algunas técnicas que pueden ayudarte a reducir la cantidad de archivos de imagen que uses para construir tu página</strong>: <a href="http://alistapart.com/articles/slidingdoors/">CSS Sliding Doors</a> &amp; <a href="http://alistapart.com/articles/sprites">CSS Sprites</a>. Hacer más con menos, <em>keep in mind</em>.</li>
</ul>
<ul>
	<li>La guinda del pastel: <strong>no te olvides de preparar una hoja de estilos para impresión</strong>. Hace unos días dábamos algunos consejos desde <strong>Pixelovers</strong> al respecto en <a href="http://pixelovers.com/p/hojas-de-estilo-para-impresion-9628">Hojas de estilo para impresión</a>.</li>
</ul>
<ul>
	<li>Puedes <strong><a href="http://pixelovers.com/p/como-evitar-problemas-con-la-cache-del-navegador-10139">usar parámetros en la llamada a tu CSS para mantener el control sobre la caché del navegador</a></strong>, y decidir cuándo debe expirar tu hoja de estilos o forzar a tus usuarios a descargarla de nuevo en su siguiente visita.</li>
</ul>
<h2>Conclusiones</h2>
Para empezar, concluyo que finalmente el artículo ha salido algo más largo de lo que había previsto, pero había algunos puntos que no quería que quedaran en el tintero, así que espero disculpes mis excesos. :)

Sin duda, elaborar una guia de estilo a modo de referencia es una práctica recomendable, cuando tengas que enfrentarte un proyecto de dimensiones considerables, y con más motivo si van a ser varios diseñadores / desarrolladores los que "metan mano" al código. Aún y codificando correctamente, cumpliendo estándares y produciendo código válido, semántico, etc... cada uno tiene sus costumbres y su manera de hacer, y mezclar formas de trabajar sin cierto orden en un mismo proyecto puede resultar algo problemático para mantener la web en un futuro. Definir una referencia de estilo, estructura y/o nomenclatura puede reducir, y mucho, esos problemas en equipos grandes.

¿Y tú, cómo trabajas? <strong>¿Coinciden estas recomendaciones con las que incluirías tú en tu HOW-TO?</strong>
<h2>Enlaces y más</h2>
<ul>
	<li><a href="http://www.w3.org/TR/CSS21/">Especificación CSS 2.1</a></li>
	<li><a href="http://jigsaw.w3.org/css-validator/">Validador CSS</a></li>
	<li><a href="http://www.smashingmagazine.com/2007/05/10/70-expert-ideas-for-better-css-coding/">Optimizador CSS</a></li>
	<li><a href="http://www.smashingmagazine.com/2007/05/10/70-expert-ideas-for-better-css-coding/">70 expert ideas for better css coding</a> en <strong>Smashing Magazine</strong></li>
	<li><a href="http://www.mezzoblue.com/archives/2003/11/19/css_crib_she/">CSS Crib Sheet</a> de <strong>Dave Shea</strong></li>
</ul>