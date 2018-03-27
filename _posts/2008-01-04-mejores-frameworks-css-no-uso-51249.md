---
ID: 2408
post_title: >
  Los mejores frameworks CSS (y porqué no
  los uso)
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/mejores-frameworks-css-no-uso-51249/
published: true
post_date: 2008-01-04 23:14:01
---
La intención de un framework es principalmente ahorrar tiempo y minimizar el riesgo de errores en el desarrollo de aplicaciones. Los frameworks nos evitan, sobretodo en los momentos iniciales del desarrollo de una aplicación, repetir código para construir la base y nos permiten conseguir ciertas funcionalidades o módulos genéricos de forma más rápida y sencilla. Así como hay frameworks para PHP (<a href="http://www.cakephp.org/">CakePHP</a>, <a href="http://codeigniter.com/">CodeIgniter</a>, <a href="http://framework.zend.com/">The Zend Framework</a>...) o para Javascript (como no... <a href="http://www.jquery.com">JQuery</a>), también existen varios frameworks para CSS. Veamos en qué consisten.

<!--more-->
<h2>¿Qué es un framework CSS?</h2>
Igual que sus parientes orientados a lenguajes de servidor o cliente, el objetivo de un framework CSS será ahorrarnos realizar las tareas básicas al trabajar con hojas de estilo. Normalmente los frameworks CSS se componen de uno o varios archivos con declaraciones predefinidas que incluyen:
<ul>
	<li><strong>CSS Reset</strong>: Ya hablamos de las ventajas de resetear los estilos al empezar a trabajar la maquetación de una página, en nuestra lista de consejos y buenas prácticas para CSS.  Resetear los estilos nos permitirá homogeneinzar, a priori, las posibles diferencias de visualización entre navegadores, unificando las propiedades básicas de los elementos: márgenes, paddings, tamaños, formatos, etc.</li>
	<li><img title="51249-44848.jpg" src="/app/uploads/sites/7/2008/01/51249-44848.jpg" alt="51249-44848.jpg" width="200" height="161" align="right" /><strong>Layout</strong>:  Una parte de los frameworks va dirigida a una de las tareas más árduas a la hora de maquetar cualquier diseño: conseguir un determinado layout, más o menos complejo, que sea, además de óptimo, "cross-browser", e.d. compatible con todos los navegadores. Suelen disponer de múltiples opciones combinables para conseguir layouts complejos: múltiples columnas, anchos fijos, elásticos, líquidos...</li>
	<li><strong>Tipografías</strong>: Una gestión genérica de las tipografías que se usarán en la página. De nuevo, no sólo se trata de aplicar un uso inteligente de fuentes y tamaños, si no de unos altos de línea, márgenes, paddings... consistentes, que ayuden a  mantener un correcto ritmo vertical en la página.</li>
</ul>
<h2>Ventajas de usar un framework CSS</h2>
<ul>
	<li><strong>Permite agilizar el desarrollo</strong>, sobretodo en sus momentos iniciales.</li>
	<li><strong>Te ahorra las habituales batallitas entre navegadores</strong> para conseguir que tus layouts sean "cross-browser".</li>
	<li><strong>Partes de una base normalizada</strong> / homogeneizada sobre la que desarrollar un trabajo adicional.</li>
	<li>Si el framework CSS está bien documentado, <strong>agiliza el trabajo en un equipo relativamente grande</strong>.</li>
</ul>
<h2>Entonces... !¿Porqué no los uso?!</h2>
Eso me gustaría saber... No, es broma. De verdad que, aunque en el caso de frameworks de desarrollo para lenguajes como PHP o Javascript me parece una ventaja a la que sacar partido, creo que en el caso de las hojas de estilo, las ventajas no son suficientemente potentes como para superar el peso de las desventajas, que para mi son:
<ul>
	<li><strong>Curva de aprendizaje</strong>. Algunos frameworks son realmente complejos, y es necesaria bastante dedicación  y pruebas para llegar a controlarlos bien, conocer y usar todo su potencial.</li>
	<li><strong>Puede afectar negativamente a la semántica de tu marcado HTML</strong>. La mayoría de los frameworks contienen definiciones demasiado genéricas que además han sido pensadas y nombradas pensando únicamente en la apariencia que tendrán. Y si recordamos, uno de los consejos en el artículo que citábamos antes era "<strong>Sé descriptivo en los nombres y huye de usar aquellos que se refieran a la apariencia de los elementos.</strong>" Meeec. Va a ser que un contenedor llamado "big-square-at-the-left" no va a resultar muy práctico si dentro de unos meses debemos cambiar el layout de nuestra página. ¿No habíamos quedado que <strong>la ventaja principal de las hojas de estilo era separar contenido y presentación</strong>?</li>
	<li><strong>Gran parte del código nunca será utilizado</strong>. Los frameworks intentan prever todas las situaciones y contienen muchas definiciones genéricas que posiblemente nunca lleguemos a utilizar. Esta desventaja sería en realidad aplicable también a otro tipo de frameworks. Con la diferencia que un framework PHP por ejemplo, el cliente no debe descargar TODO el framework para que la aplicación funcione: se ejecuta en el servidor. El CSS en cambio sí debe descargarse al navegador, con lo que debemos cuidar su extensión si no queremos afectar negativamente al rendimiento.</li>
	<li>Por último, y posiblemente la más importante al menos para mi, es que <strong>usar un framework CSS te corta las alas a la hora de aprender, de entender cómo funcionan realmente las hojas de estilo</strong>. Muchas de las cosas que sé ahora las aprendí mientras me rompía los cuernos tratando de solucionar absurdos bugs de render de Explorer, o de conseguir flotar aquella caja rebelde, o buscando el motivo por el cual la cascada se iba a tomar viento al definir tal o cuál color. En mi opinión, condiciona excesivamente el trabajo del desarrollador.</li>
</ul>
<h2>Lista de frameworks CSS</h2>
De todas formas, te animo a que conozcas y pruebes algunos de estos frameworks ( quizás entonces entiendas mis motivos... o pienses que estoy loco )
<ul>
	<li><a href="http://www.yaml.de/en/"><strong>YAML</strong> (Yet Another Multicolumn Layout)</a></li>
	<li><strong><a href="http://code.google.com/p/blueprintcss/">Blueprint</a></strong></li>
	<li><strong><a href="http://www.contentwithstyle.co.uk/">Content with Style</a></strong></li>
	<li><a href="http://developer.yahoo.com/yui/grids/">YUI: <strong>Yahoo User Interface Library</strong> - Grids</a></li>
</ul>
<h2>Conclusión</h2>
Aunque no recomiende su uso, sí que hay algunas ideas que subyacen al trabajo con frameworks con las que comulgo, y te invito efusivamente a seguir, como son:
<ul>
	<li>El reseteo de los estilos al principio de tus CSS.</li>
	<li>La creación de una librería de "helpers" o snippets de código y declaraciones CSS que te sirvan como referencia para resolver situaciones comunes.</li>
	<li>Definir y mantener una estructura y una sintaxis del documento CSS que sea consistente, y aplicarla siempre en todos tus proyectos.</li>
</ul>
<h3>Otros artículos interesantes que inspiraron este post</h3>
<ul>
	<li><a href="http://www.smashingmagazine.com/2007/09/21/css-frameworks-css-reset-design-from-scratch/">CSS Framewoks | <strong>Smashing Magazine</strong></a></li>
	<li><a href="http://warpspire.com/features/css-frameworks/">Why I dont use CSS Frameworks | <strong>Warpspire</strong></a></li>
	<li><a href="http://mondaybynoon.com/2007/08/27/please-do-not-use-css-frameworks/">Please, do not use CSS Frameworks | </a><strong><a href="http://mondaybynoon.com/2007/08/27/please-do-not-use-css-frameworks/">Monday by Noon</a>
</strong></li>
</ul>