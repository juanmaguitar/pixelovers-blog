---
ID: 2377
post_title: Hojas de estilo para impresión
author: Albert Garcia
post_excerpt: |
  <p>
  Pod&eacute;is ver un ejemplo pr&aacute;ctico en las <a href="http://serious-samurize.en.softonic.com/">fichas de programa de <strong>Softonic Ingl&eacute;s</strong></a> , que renovamos hace poco para incluir este tipo de mejoras:
  </p>
  <p align="center">
  <img class="fotobonita" src="http://stc.obolog.net/multimedia/fotos/10000/9628/9628-10775_p.jpg" alt="9628-10775.jpg" title="9628-10775.jpg" width="417" height="300" /><br />
  versi&oacute;n online
  </p>
  <p align="center">
  <img class="fotobonita" src="http://stc.obolog.net/multimedia/fotos/10000/9628/9628-10776_p.jpg" alt="9628-10776.jpg" title="9628-10776.jpg" width="419" height="300" /><br />
  versi&oacute;n para impresi&oacute;n
  </p>
  <p align="left">
  Como &uacute;ltimo detalle: <strong>a menos que indiqu&eacute;is en
  vuestra hoja de estilos gen&eacute;rica el media=&quot;screen&quot;, el documento de
  impresi&oacute;n heredar&aacute; todas las propiedades de dicha hoja de estilos</strong>.
  </p>
  <p align="left">
  Aunque es posible redefinir y sobreescribir todas las propiedades de
  nuevo en la hoja de estilos de impresi&oacute;n, lo m&aacute;s sencillo es lo que
  indico arriba: <strong>especificad el media = &quot;screen&quot; en vuestra CSS gen&eacute;rica</strong>.
  De esta forma en el CSS de impresi&oacute;n os evitar&eacute;is tener que eliminar el
  formato de todos los elementos: s&oacute;lo tendr&eacute;is que definir aquellas
  clases e ids que necesit&eacute;is.
  </p>
layout: post
permalink: >
  https://pixelovers.com/hojas-estilo-impresion-9628/
published: true
post_date: 2007-04-05 00:00:00
---
Hoy vamos a hablar sobre cómo, mediante hojas de estilo, podemos optimizar nuestras páginas para ser impresas.

Aún a dia de hoy es habitual encontrar muchos sites que ofrecen a sus lectores versiones "imprimibles" de sus páginas, enlaces que nos envían a una nueva página en la que se han eliminado algunos elementos y se han formateado los contenidos de forma que encajen y se visualicen correctamente en papel.

<!--more-->

Dejando un lado el trabajo extra que esto supone, <strong>crear páginas específicas para impresión duplicando contenido del documento principal puede acarrear daños colaterales tales como penalizaciones en el posicionamiento de nuestra web</strong>, por contenido duplicado en Google. Aún existiendo técnicas para evitar esto ( NOINDEX ), no tenemos porqué arriesgarnos ni realizar ese esfuerzo extra de duplicación.

Mediante el atributo <a href="http://www.w3.org/TR/REC-CSS2/media.html"><em>media</em></a> de CSS, podemos enlazar a una hoja de estilos que actuará exclusivamente cuando el usuario trate de imprimir una página.
<div class="codigo"></div>
En esta nueva hoja de estilos trataremos de conseguir lo siguiente:

<strong>1. Eliminar contenidos no deseados</strong>

Posiblemente no sean necesarias ni la cabecera completa del site, ni las opciones de navegación principales, el <a href="http://developer.yahoo.com/ypatterns/pattern.php?pattern=breadcrumbs"><em>breadcrumb</em></a>, ni, si las hubiera, las columnas laterales con información adicional, ¡o la publicidad!. Al usuario le interesa el contenido principal de la página.
<div class="codigo">
<pre class="whitespace-before:0 whitespace-after:0 lang:xhtml decode:true ">#navigation, #breadcrumb, #sidebar, #footer { display: none }

</pre>
</div>
<strong>2. Formatear la página</strong>

Desde asegurarnos que los elementos van a encajar en la página correctamente ( nada de floats ni margins, todos los anchos porcentuales... ) hasta revisar el formato visual de los elementos ( lo que en la versión online enfatizamos usando el color rojo, quizás valga la pena enfatizarlo con negrita o subrayado en la versión impresa: el usuario posiblemente imprima en blanco y negro ).

También, para rizar el rizo, podemos tratar de añadir a los enlaces algo de información adicional, indicando a qué URL apunta cada uno, o recopilándolos todos al final de la página. Os recomiendo la lectura <a href="http://alistapart.com/articles/improvingprint">del artículo que trata precisamente sobre esto <strong>en A List Apart</strong></a> .

<strong>3. Tener especial cuidado con las imágenes</strong>

Es habitual, a la hora de maquetar una página mediante CSS, el uso de imágenes de fondo para conseguir ciertos efectos, delimitar contenedores, etc... Hay que tener en cuenta que, <strong>por defecto, la mayoría de navegadores no imprimen las imágenes de fondo</strong>, con lo que, por ejemplo, si el logotipo de la página está como fondo de una capa que contiene el nombre la misma... no se verá en la versión impresa.

Una forma de evitar esto sería usar un logo optimizado para impresión ( B/N ), incluído dentro del propio HTML de la página, pero oculto por CSS para la versión de pantalla, pero visible para la versión impresa
<div class="codigo">
<pre class="lang:css decode:true">#print_logo { display:none; }

</pre>
</div>
<div class="codigo">
<pre class="lang:css decode:true " title="print.css">#print_logo { display:block; }

</pre>
</div>
<div class="codigo"></div>
<img class="mce-pagebreak" src="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7" alt="" />

Podéis ver un ejemplo práctico en las <a href="http://serious-samurize.en.softonic.com/">fichas de programa de <strong>Softonic Inglés</strong></a> , que renovamos hace poco para incluir este tipo de mejoras:
<p align="center"><img class="fotobonita" title="9628-10775.jpg" src="http://stc.obolog.net/multimedia/fotos/10000/9628/9628-10775_p.jpg" alt="9628-10775.jpg" width="417" height="300" />
versión online</p>
<p align="center"><img class="fotobonita" title="9628-10776.jpg" src="http://stc.obolog.net/multimedia/fotos/10000/9628/9628-10776_p.jpg" alt="9628-10776.jpg" width="419" height="300" />
versión para impresión</p>
<p align="left">Como último detalle: <strong>a menos que indiquéis en vuestra hoja de estilos genérica el media="screen", el documento de impresión heredará todas las propiedades de dicha hoja de estilos</strong>.</p>
<p align="left">Aunque es posible redefinir y sobreescribir todas las propiedades de nuevo en la hoja de estilos de impresión, lo más sencillo es lo que indico arriba: <strong>especificad el media = "screen" en vuestra CSS genérica</strong>. De esta forma en el CSS de impresión os evitaréis tener que eliminar el formato de todos los elementos: sólo tendréis que definir aquellas clases e ids que necesitéis.</p>