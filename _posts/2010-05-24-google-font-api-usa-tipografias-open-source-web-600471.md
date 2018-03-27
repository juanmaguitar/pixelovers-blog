---
ID: 2477
post_title: 'Google Font API: Usa tipografías open source en la web'
author: Jorge del Casar
post_excerpt: |
  <h2>Solo con CSS</h2>
  <p>Tienes varias formas de incluir las tipograf&iacute;as en tu web. La m&aacute;s  sencilla de todas es <strong>incluyendo una hoja de estilos</strong> adicional:</p>
  <pre><code>&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=<var>Font+Name</var>"/&gt;<br /></code></pre>
  <p>Luego simplemente usas la tipograf&iacute;a en tu hoja de estilos de forma  habitual:</p>
  <pre><code>CSS selector {<br />  font-family: '<var>Font+Name</var>', serif;<br />}</code></pre>
  <p>Si no quieres cargar todas las variantes, puedes <strong>especificar las variantes</strong> que  quieras a&ntilde;adiendo dos puntos y las variantes que quieras separadas por  comas:</p>
  <pre><code>&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=<var>Font+Name</var>:<var>variante</var>"/&gt;<br /></code></pre>
  <p>Si quieres a&ntilde;adir <strong>varias tipograf&iacute;as</strong>, no es necesario hacer 1 llamada  por cada una de ellas, simplemente con separar los nombres con pipes  "|" es suficiente:</p>
  <pre><code>&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Tangerine|Inconsolata|Droid+Sans"/&gt;<br /></code></pre>
  <p>Y si quieres hacer todo a la vez simplemente sigue todas las reglas  anteriores, y quedar&aacute; algo de esta forma:</p>
  <pre><code>&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Tangerine:bold,bolditalic|Inconsolata:italic|Droid+Sans"/&gt;<br /></code></pre>
  <h2>Con ayuda de Javascript</h2>
  <p>Si no quieres que la carga de tu p&aacute;gina se vea afectada por tener que  resolver otras DNS y cargar contenido de servidores que no puedes  controlar, puedes probar <strong>WebFont Loader</strong>. Una API de Javascript que te da  un mayor control sobre las tipograf&iacute;as cargadas. Esta forma tambi&eacute;n es  muy sencilla, pero requiere un m&iacute;nimo de conocimiento de Javascript. Con  a&ntilde;adir estas lineas en el head de tu p&aacute;gina tendr&iacute;amos todo listo para  usarla</p>
  <pre><code>&lt;script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/webfont/1/webfont.js"&gt;<br />    &lt;/script&gt;<br />    &lt;script type="text/javascript"&gt;<br />      WebFont.load({<br />        google: {<br />          families: [ 'Tangerine', 'Cantarell' ]<br />        }<br />      });<br />    &lt;/script&gt;</code></pre>
  <p>Esto carga las tipograf&iacute;as indicadas en families y si todo ha ido  correctamente y el navegador permite estas tipograf&iacute;as se a&ntilde;adir&aacute; en el  html las clases: 'wf-active' y 'wf-family-type-active' (por ejemplo:  'wf-cantarell-n4-active').</p>
  <p>Esto nos permite usar en nuestra hoja de estilo tipograf&iacute;as  alternativas en caso de no haber podido cargar las deseadas, de esta  forma:</p>
  <pre>.wf-inactive p {<br />   font-family: serif<br /> }<br /> .wf-active p {<br />    font-family: 'Cantarell', serif<br /> }<br /></pre>
  <p>Con WebFont Loader puedes solicitar fuentes a otros proveedores como por ejemplo TypeKit o incluso hacer llamadar a cualquier proovedor de tipograf&iacute;as <a title="Especificar el proveedor de tipograf&iacute;as" href="http://code.google.com/apis/webfonts/docs/webfont_loader.html#Specifying" target="_blank">especificando el proveedor</a>.</p>
  <p>En la llamada a WebFont Loader puedes <strong>especificar callbacks</strong> para ejecutar tu propio c&oacute;digo en un momento dado. Las funciones de calback de las que dispones son:</p>
  <ul>
  <li><strong>loading()</strong> Se llama cuando todos los m&oacute;dulos de proveedores de tipograf&iacute;as web (google, typekit, y/o custom) han reportadoq ue empiezan a cargar tipograf&iacute;as.</li>
  <li><strong>fontloading(fontFamily, fontDescription)</strong> Se llama cuando se empieza a cargar cada solicitud de tipograf&iacute;a web. El par&aacute;metro&nbsp; fontFamily es el nombre de la familia de la tipograf&iacute;a, y fontDescription representa el estilo y peso de la tipograf&iacute;a.</li>
  <li><strong>fontactive(fontFamily, fontDescription)</strong> Se llama cuando ha terminado de cargar cada una de las solicitudes.</li>
  <li><strong>fontinactive(fontFamily, fontDescription)</strong> Se llama si una solicitud ha fallado al cargar.</li>
  <li><strong>active()</strong> Se llama cuando todas las tipograf&iacute;as web han sido cargadas o bien no se haya podido cargar, siempre y cuando al menos una&nbsp; se cargado con &eacute;xito.</li>
  <li><strong>inactive()</strong> Se llama si el browser no soporta tipograf&iacute;as web o si ninguna de las fuentes se ha podido cargar.</li>
  </ul>
  <p>Sabiendo todo esto, no me he podido resistir a hacer pruebas con esta nueva API, as&iacute; que  os dejo una demo de uso, en las que cargo las fuentes bajo demanda.</p>
  <p><a title="Demo de Google Font API" href="http://demo.pixelovers.com/google-font-api-usa-tipografias-open-source-web-600471">Demo  de Google Font API</a></p>
  <p>&iquest;Qu&eacute; os ha parecido la API? &iquest;Qui&eacute;res ese&ntilde;arnos tus nuevos dise&ntilde;os  usando estas tipograf&iacute;as?</p>
layout: post
permalink: >
  https://pixelovers.com/google-font-api-usa-tipografias-open-source-web-600471/
published: true
post_date: 2010-05-24 10:09:00
---
<img class="ma-m alignnone" style="float: right;" title="Google font api" src="/app/uploads/sites/7/2010/05/600471-251844.jpg" alt="Google font api" width="196" height="40" />

Cada vez salen más y más APIs, y Google es uno de los qué más APIs libera. Esta vez ha presentado en las conferencias Google I/O, realizadas el pasado 19 y 20 de Mayo, la <a title="Google Font API" href="http://code.google.com/apis/webfonts/" target="_blank">Google Font API</a>.

<!--more-->Esta API te ayuda a añadir tipografías en cualquier página web. Esto tiene unos beficios claros como:
<ul>
	<li>Disponer de tipografías de código abierto de alta calidad</li>
	<li>Funciona en la mayoría de los navegadores</li>
	<li>Es extremadamente facil de usar.</li>
</ul>
<img class="ma-m alignnone" style="float: right;" title="Google font directory" src="/app/uploads/sites/7/2010/05/600471-251845.jpg" alt="Google font directory" width="200" height="30" />

Puedes ver todas las tipografías disponibles en el <a title="Direcotrio de tipografías de Google" href="http://code.google.com/webfonts" target="_blank">Directorio de Tipografías de Google</a>. De momento disponen de 18 fuentes, con variantes en itálica, negrita, italica negrita. Además 1 de ellas dispone de 10 familias diferentes. Por lo tanto contamos con un catálogo amplio que nos permitirá dar otro estilo a nuestra web y salirnos de las típicas tipografías universales.

<img class="ma-m alignnone" style="float: right;" title="Google Font API" src="/app/uploads/sites/7/2010/05/600471-251841.jpg" alt="Google Font API" width="128" height="128" />Además el catálogo está muy cuidado, ya que dispone de una ficha por cada una de las tipografías. En la ficha puedes encontrar el nombre del diseñador, con un enlace a su biografía y otros datos personales. También dispones de la descripción de la tipografía y el set de caracteres. También hay ejemplos de textos en diferentes tamaños, desde 36px hasta 12px, en diferentes  colores, #000, #333 y #666, y diferentes variantes, cursiva, negrita y negrita cursiva Puedes ver como ejemplo la <a title="Ficha de la tipografía Cararell" href="http://code.google.com/webfonts/family?family=Cantarell" target="_blank">ficha de la tipografía Cararell</a>.

Si te parece interesante y quieres ver como incluirlo en tu web acontinuación te cuento las diferentes formas, solo con CSS y con ayuda de Javascript.
<h2>Solo con CSS</h2>
Tienes varias formas de incluir las tipografías en tu web. La más sencilla de todas es <strong>incluyendo una hoja de estilos</strong> adicional:
<pre class="lang:xhtml decode:true">&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Font+Name"/&gt;</pre>
Luego simplemente usas la tipografía en tu hoja de estilos de forma habitual:
<pre class="lang:css decode:true  ">CSS selector {
  font-family: 'Font+Name', serif;
}</pre>
&nbsp;

Si no quieres cargar todas las variantes, puedes <strong>especificar las variantes</strong> que quieras añadiendo dos puntos y las variantes que quieras separadas por comas:
<pre class="lang:xhtml decode:true">&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Font+Name:variante"/&gt;</pre>
Si quieres añadir <strong>varias tipografías</strong>, no es necesario hacer 1 llamada por cada una de ellas, simplemente con separar los nombres con pipes "|" es suficiente:
<pre class="lang:xhtml decode:true ">&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Tangerine|Inconsolata|Droid+Sans"/&gt;</pre>
Y si quieres hacer todo a la vez simplemente sigue todas las reglas anteriores, y quedará algo de esta forma:
<pre class="lang:xhtml decode:true ">&lt;link rel="stylesheet" type="text/css" href="http://fonts.googleapis.com/css?family=Tangerine:bold,bolditalic|Inconsolata:italic|Droid+Sans"/&gt;</pre>
&nbsp;
<h2>Con ayuda de Javascript</h2>
Si no quieres que la carga de tu página se vea afectada por tener que resolver otras DNS y cargar contenido de servidores que no puedes controlar, puedes probar <strong>WebFont Loader</strong>. Una API de Javascript que te da un mayor control sobre las tipografías cargadas. Esta forma también es muy sencilla, pero requiere un mínimo de conocimiento de Javascript. Con añadir estas lineas en el head de tu página tendríamos todo listo para usarla
<pre class="lang:js decode:true ">&lt;script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/webfont/1/webfont.js"&gt;
&lt;/script&gt;
&lt;script type="text/javascript"&gt;
  WebFont.load({
    google: {
      families: [ 'Tangerine', 'Cantarell' ]
    }
  });
&lt;/script&gt;</pre>
Esto carga las tipografías indicadas en families y si todo ha ido correctamente y el navegador permite estas tipografías se añadirá en el html las clases: \'wf-active\' y \'wf-family-type-active\' (por ejemplo: \'wf-cantarell-n4-active\').

Esto nos permite usar en nuestra hoja de estilo tipografías alternativas en caso de no haber podido cargar las deseadas, de esta forma:
<pre class="lang:css decode:true ">.wf-inactive p {
   font-family: serif
 }
 .wf-active p {
    font-family: \'Cantarell\', serif
 }</pre>
Con WebFont Loader puedes solicitar fuentes a otros proveedores como por ejemplo TypeKit o incluso hacer llamadar a cualquier proovedor de tipografías <a title="Especificar el proveedor de tipografías" href="http://code.google.com/apis/webfonts/docs/webfont_loader.html#Specifying" target="_blank">especificando el proveedor</a>.

En la llamada a WebFont Loader puedes <strong>especificar callbacks</strong> para ejecutar tu propio código en un momento dado. Las funciones de calback de las que dispones son:
<ul>
	<li><strong>loading()</strong> Se llama cuando todos los módulos de proveedores de tipografías web (google, typekit, y/o custom) han reportadoq ue empiezan a cargar tipografías.</li>
	<li><strong>fontloading(fontFamily, fontDescription)</strong> Se llama cuando se empieza a cargar cada solicitud de tipografía web. El parámetro  fontFamily es el nombre de la familia de la tipografía, y fontDescription representa el estilo y peso de la tipografía.</li>
	<li><strong>fontactive(fontFamily, fontDescription)</strong> Se llama cuando ha terminado de cargar cada una de las solicitudes.</li>
	<li><strong>fontinactive(fontFamily, fontDescription)</strong> Se llama si una solicitud ha fallado al cargar.</li>
	<li><strong>active()</strong> Se llama cuando todas las tipografías web han sido cargadas o bien no se haya podido cargar, siempre y cuando al menos una  se cargado con éxito.</li>
	<li><strong>inactive()</strong> Se llama si el browser no soporta tipografías web o si ninguna de las fuentes se ha podido cargar.</li>
</ul>
¿Qué os ha parecido la API? ¿Quiéres eseñarnos tus nuevos diseños usando estas tipografías?