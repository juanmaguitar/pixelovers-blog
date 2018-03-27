---
ID: 3291
post_title: 'CSS para Surferas I: ¿Qué es CSS?'
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/css-para-surferas-i-que-es-css/
published: true
post_date: 2015-05-10 08:53:26
---
<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/css-surferas.png"><img class="alignnone wp-image-3342 size-full" title="CSS para surferas / principiantes - ¿qué es css?" src="http://pixelovers.com/app/uploads/sites/7/2015/05/css-surferas.png" alt="CSS para surferas / principiantes - ¿qué es css?" width="680" height="360" /></a>

Mi novia escribe en un blog sobre surf llamado <a href="http://surfmocion.com">surfmocion.com</a> y el otro día me decía que estaba muy contenta porque había conseguido aumentar el tamaño de la letra en una página de su blog con CSS :)

Pero que más allá de saber que el CSS sirve para cambiar el diseño de la web, no sabía muy bien cómo funcionaba todo esto y que se quería apuntar a un curso o algo para aprender, porque quería poder cambiar ella sola el diseño de su blog.

Asi que le dije que yo le podía explicar si quería...

<ul>
    <li><em>Si quieres te puedo explicar yo cómo va esto del CSS</em></li>
    <li><em><img class="" src="http://s.w.org/images/core/emoji/72x72/1f60d.png" alt="😍" width="15" height="15" /></em></li>
    <li><em>Ademas lo puedo montar como una serie de posts para que lo tengas de referencia cuando lo necesites</em></li>
    <li><em><img class="" src="http://s.w.org/images/core/emoji/72x72/1f60d.png" alt="😍" width="15" height="15" /> <img class="" src="http://s.w.org/images/core/emoji/72x72/2764.png" alt="❤️" width="15" height="15" /></em></li>
    <li><em>Y le puedo dar el enfoque que necesitas, es decir que tengas las nociones básicas para que puedas modificar los estilos en tu blog</em></li>
    <li><em><img class="" src="http://s.w.org/images/core/emoji/72x72/1f60d.png" alt="😍" width="15" height="15" /> <img class="" src="http://s.w.org/images/core/emoji/72x72/2764.png" alt="❤️" width="15" height="15" /> <img class="" src="http://s.w.org/images/core/emoji/72x72/1f389.png" alt="🎉" width="15" height="15" /></em></li>
    <li><em>Oks, <a href="https://www.youtube.com/watch?v=cfsU6GuMz08">Challenge Accepted</a>!! <img class="" src="http://s.w.org/images/core/emoji/72x72/1f60e.png" alt="😎" width="15" height="15" /></em></li>
</ul>

Asi que empecemos explicando "el modelo de capas", un concepto que nos va a ayudar a entender mejor qué es el CSS y su función en una pagina web

<!--more-->

<h2> El modelo de capas</h2>

Cuando vemos una página web <a href="http://alistapart.com/article/behavioralseparation">podemos imaginar lo que vemos separado en 3 capas</a> (asociadas a 3 tecnologías)

<ul>
    <li>La capa del contenido que se maneja con HTML</li>
    <li>La capa del diseño que se maneja con CSS</li>
    <li>La capa del comportamiento (acciones, movimiento) que se maneja con Javascript</li>
</ul>

<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/languages.png"><img class="aligncenter wp-image-3491 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2015/05/languages-300x176.png" alt="modelo de capas HTML5 CSS3 JS" width="300" height="176" /></a>

<h4>La capa del contenido (HTML)</h4>

En esta capa se maneja la <em>estructura de la información</em> (el contenido, el texto) que estamos mostrando. Con las etiquetas (<em>tags</em>) HTML lo que hacemos es darle significado semántico al texto, es decir diferenciamos lo que es un titular (<code>h1</code>), de lo que es un párrafo (<code>p</code>), de lo que es una lista (<code>ul</code>), etc...

Un código HTML de una pagina cualquiera podría ser <a href="https://github.com/pixelovers/css-surferas/blob/master/index.html">esto</a>

Y sin estilos CSS esta pagina HTML se veria en tu navegador <a href="http://pixelovers.github.io/css-surferas/index.html">asi</a> (por defecto tu navegador "interpreta" estos tags en un formato standard: los h1 se muestran en fuentes mas grandes, los enlaces en azul y subrayados, etc... )

Normalmente este código HTML está en archivos <code>.html</code> aunque también puede estar en otro tipo de archivos (<code>.php</code> por ejemplo)

<h4>La capa del diseño (CSS)</h4>

Desde esta <em>capa</em> controlamos cómo presentamos esta información, es decir que desde aquí podemos cambiar el diseño y estilo (colores, tamaños, márgenes...) a nuestro HTML. Para ello utilizamos el lenguaje CSS con el que mediante un sistema de <em>reglas</em> podemos cambiar los estilos de elementos concretos de nuestro HTML (del <code>h1</code>, del <code>p</code>, del <code>ul</code>, etc...)

Lo que se suele hacer es adjuntar un archivo CSS donde están definidos todos los estilos de la pagina. Con este sistema podemos hacer que una página con el mismo HTML se vea totalmente distinta aplicando otro CSS.

Por ejemplo este <a href="https://github.com/pixelovers/css-surferas/blob/master/index.html">html</a> se ve <a href="http://pixelovers.github.io/css-surferas/index.html">así</a> sin estilos

Pero aplicándole diferentes estilos por CSS se puede ver <a href="http://pixelovers.github.io/css-surferas/css-garden-210/index.html">así</a>, <a href="http://pixelovers.github.io/css-surferas/css-garden-211/index.html">así</a>, <a href="http://pixelovers.github.io/css-surferas/css-garden-212/index.html">así</a> o <a href="http://pixelovers.github.io/css-surferas/css-garden-213/index.html">así</a>

Mola, no?

Si <a href="http://es.wikihow.com/ver-el-c%C3%B3digo-fuente-de-una-p%C3%A1gina-de-internet">miras el código HTML</a> de <a href="http://pixelovers.github.io/css-surferas/css-garden-210/index.html">esta página</a>, <a href="http://pixelovers.github.io/css-surferas/css-garden-211/index.html">esta</a>, <a href="http://pixelovers.github.io/css-surferas/css-garden-212/index.html">esta</a> o <a href="http://pixelovers.github.io/css-surferas/css-garden-213/index.html">esta</a> veras que el HTML es exactamente el mismo y que estos archivos se diferencian solo en una linea

<pre class="lang:xhtml decode:true ">&lt;link rel="stylesheet" media="screen" href="210.css"&gt;</pre>

En esta linea es donde cargamos un CSS u otro

Menuda diferencia <a href="http://www.csszengarden.com/">sólo cambiando el archivo CSS</a> que cargamos, ¿no?

<h4>La capa del comportamiento (Javascript)</h4>

Sin entrar en mucho detalle aquí, hay una tercera capa necesaria cuando queremos añadir acciones en nuestra pagina web (por ejemplo que se muestre un mensaje cuando pulsamos un botón). Esta capa se controla mediante código Javascipt que podemos añadir mediante archivos <code>.js</code> (de la misma manera que añadimos estilos añadiendo archivos <code>.css</code>)

Si quieres <a href="http://apuntesjs.com">aprender más sobre Javascript aqui tienes unos buenos libros</a> para empezar ;)

<h2>¿Qué significan las siglas CSS?</h2>

OK, ya tenemos ubicada la función y el potencial del CSS en una página web así que ahora vamos a centrarnos en las características propias del CSS

<strong><a href="http://es.wikipedia.org/wiki/Hoja_de_estilos_en_cascada">CSS</a> son las siglas de <em>Cascading Style Sheets</em></strong> (Hojas de Estilo en Cascada):

<ul>
    <li><em>Style Sheets</em> (Hojas de Estilo) porque cómo ya hemos visto en los archivos CSS (las "hojas") tenemos definidos los estilos de la página</li>
    <li><em>Cascading</em> (en Cascada) porque podemos cargar varios archivos CSS y si hay estilos definidos que afecten a los mismos elementos, estos se aplican en "cascada" siguiendo unos criterios de orden, prioridad y peso. Estas normas para decidir que estilo se está aplicando a tu elemento CSS tienen un poco de miga pero a "grosso modo" el ultimo CSS que cargues suele tener prioridad sobre el anterior ;)</li>
</ul>

<h2 id="como-funciona">¿Y cómo funciona?</h2>

<strong>CSS funciona a base de <a href="http://line25.com/articles/10-css-rules-every-web-designer-should-know">reglas</a></strong>. Una regla CSS tiene dos partes: un selector y un bloque de declaraciones.

<pre class="lang:css decode:true  ">h1 {color: blue; font-size:12px;}</pre>

<code>h1</code> es el <em>selector</em> y <code>{color: blue; font-size:12px;}</code> es el <em>bloque de declaraciones</em>

<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/selector.gif"><img class="alignnone size-full wp-image-3331" src="http://pixelovers.com/app/uploads/sites/7/2015/05/selector.gif" alt="selector" width="569" height="119" /></a>

<h3>El selector</h3>

El <strong><em>selector</em></strong> "selecciona" el elemento HTML al que queremos cambiar el estilo. Hay <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#selectors">muchos tipos de selectores</a> con los que podemos seleccionar elementos HTML para cambiarles el estilos

<h3>Las declaraciones</h3>

El <strong><em>bloque de declaraciones</em></strong> contiene <em>una o más declaraciones</em> La declaración es la parte de la regla que establece cuál será el efecto de diseño a aplicar.

Cada <strong><em>declaración</em></strong> incluye:

<ul>
    <li>un <em>nombre de propiedad</em></li>
    <li>un <em>valor</em></li>
</ul>

...ambos separados por dos puntos <code>:</code> y terminando siempre con punto y coma <code>;</code>

Hay <a href="https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS#Propiedades">muchas propiedades</a> que podemos utilizar para cambiar los estilos de nuestra pagina web

<hr />

Y esto es todo por ahora, espero que os haya quedado un poco más claro lo qué es el CSS. Seguiremos con más posts de la serie "CSS para surferas" :)

Si quereis seguir investigando por vuestra cuenta aqui os dejo unos cuantos enlaces

<h2>Enlaces y mas:</h2>

<ul>
    <li><a href="https://developer.mozilla.org/es/docs/Web/CSS/Introducci%C3%B3n">https://developer.mozilla.org/es/docs/Web/CSS/Introducci%C3%B3n</a></li>
    <li><a href="https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS">https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS</a></li>
    <li><a href="https://developer.mozilla.org/es/demos/tag/tech:css3">https://developer.mozilla.org/es/demos/tag/tech:css3</a></li>
</ul>