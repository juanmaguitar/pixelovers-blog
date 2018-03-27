---
ID: 2481
post_title: 'Anywhere: Hovercards'
author: Jorge del Casar
post_excerpt: |
  <p>La forma sencilla de llamar a esta funci&oacute;n es mediante:</p>
  <pre style="color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; margin: 8px;"><code>T.hovercards();</code></pre>
  <p>Cabe destacar que esta funci&oacute;n llamar&aacute;, implicitamente, a linkifyUser, por lo que no ser&aacute; necesario hacer cosas como:</p>
  <pre style="color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; margin: 8px;"><code>T.linkifyUsers().hovercards();</code></pre>
  <p>Pero igual que&nbsp;<var>linkifyUsers</var>&nbsp;tiene opciones de personalizaci&oacute;n, aparte del selector de la funci&oacute;n T, del que hablamos en el art&iacute;culo de&nbsp;<var>linkifyUsers</var>, as&iacute; que nos centraremos en los par&aacute;metros de la propia funci&oacute;n&nbsp;<var>hovercards</var>. Esta funci&oacute;n puede recibir como par&aacute;metro un objeto con las siguientes propiedades:</p>
  <ul>
  <li><strong style="font-weight: bold;">linkify</strong>: Esta propiedad sirve para indicar si queremos llamar a la funci&oacute;n&nbsp;<var>linkifyUsers</var>&nbsp;o no (por defecto el valor es true).</li>
  <li><strong style="font-weight: bold;">infer</strong>: Nos permitir&aacute; indicarle a la funci&oacute;n si el nombre de usuario se encuentra dentro del texto del elemento seleccionado o no (por defecto es false).&nbsp; Esta propiedad no es compatible con la anterior, si ponemos infer a true linkify pasar&aacute; a false.</li>
  <li><strong style="font-weight: bold;">username</strong>: nos permite identificar cual es el nombre de usuario, cuando no se encuentra en el texto del elemento. Esta propiedad tampoco es compatible con linkify, si especificamos un username linkify pasar&aacute; a false.</li>
  <li><strong style="font-weight: bold;">expanded</strong>:Permite mostrar la hovercard con la informaci&oacute;n extendida. Con toda la que sale tras pulsar en el "more...". Parece ser que no lo tienen implementado. No me ha funcionado y no he encontrado evidencia alguna en el c&oacute;digo.</li>
  <li><strong style="font-weight: bold;">complete</strong>: Tal y como suced&iacute;a en&nbsp;<var>linkifyUsers</var>&nbsp;hemos encontrado en el c&oacute;digo tambi&eacute;n la llamada a la funci&oacute;n<var>complete</var>&nbsp;en&nbsp;<var>hovercards</var>.&nbsp;<strong style="font-weight: bold;">Atributo no documentado</strong>.</li>
  <li><strong style="font-weight: bold;">selector</strong>: Por defecto es: 'a.twitter-anywhere-user' pero puedes indicarle otro selecotr sobre el que aplicar las hovercards, por ejemplo si utilizaste el atributo className de linkifyUsers.&nbsp;<strong style="font-weight: bold;">Atributo no documentado.</strong></li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/anywhere-hovercards-633853/
published: true
post_date: 2010-06-18 17:00:00
---
Continuando con serie de artículos dedicados al anywhere, ya  vimos la semana pasada como <a title="Anywhere: Auto-linkification of Twitter usernames" href="http://pixelovers.com/anywhere-auto-linkification-twitter-usernames-610375">enlazar nombre de usuario de Twitter</a>. Y esta semana hemos analizado la función <var>hovercards</var>, la cual nos permite mostrar la ficha de usuario de Twitter en los nombres de usuario que haya en nuestra página.

<!--more-->

<img title="Twitter Hovercards" src="/app/uploads/sites/7/2010/06/633853-259813.jpg" alt="Twitter Hovercards" width="344" height="174" />

La forma sencilla de llamar a esta función es mediante:
<pre style="color: #000000; font: normal normal normal 12px/1.5em \'Lucida Grande\', Helvetica, Arial, sans-serif; margin: 8px;"><code>T.hovercards();</code></pre>
Cabe destacar que esta función llamará, implicitamente, a linkifyUser, por lo que no será necesario hacer cosas como:
<pre style="color: #000000; font: normal normal normal 12px/1.5em \'Lucida Grande\', Helvetica, Arial, sans-serif; margin: 8px;"><code>T.linkifyUsers().hovercards();</code></pre>
Pero igual que <var>linkifyUsers</var> tiene opciones de personalización, aparte del selector de la función T, del que hablamos en el artículo de <var>linkifyUsers</var>, así que nos centraremos en los parámetros de la propia función <var>hovercards</var>. Esta función puede recibir como parámetro un objeto con las siguientes propiedades:
<ul>
	<li><strong style="font-weight: bold;">linkify</strong>: Esta propiedad sirve para indicar si queremos llamar a la función <var>linkifyUsers</var> o no (por defecto el valor es true).</li>
	<li><strong style="font-weight: bold;">infer</strong>: Nos permitirá indicarle a la función si el nombre de usuario se encuentra dentro del texto del elemento seleccionado o no (por defecto es false).  Esta propiedad no es compatible con la anterior, si ponemos infer a true linkify pasará a false.</li>
	<li><strong style="font-weight: bold;">username</strong>: nos permite identificar cual es el nombre de usuario, cuando no se encuentra en el texto del elemento. Esta propiedad tampoco es compatible con linkify, si especificamos un username linkify pasará a false.</li>
	<li><strong style="font-weight: bold;">expanded</strong>:Permite mostrar la hovercard con la información extendida. Con toda la que sale tras pulsar en el "more...". Parece ser que no lo tienen implementado. No me ha funcionado y no he encontrado evidencia alguna en el código.</li>
	<li><strong style="font-weight: bold;">complete</strong>: Tal y como sucedía en <var>linkifyUsers</var> hemos encontrado en el código también la llamada a la función<var>complete</var> en <var>hovercards</var>. <strong style="font-weight: bold;">Atributo no documentado</strong>.</li>
	<li><strong style="font-weight: bold;">selector</strong>: Por defecto es:  <code>a.twitter-anywhere-user</code> pero puedes indicarle otro selecotr sobre el que aplicar las hovercards, por ejemplo si utilizaste el atributo className de linkifyUsers. <strong style="font-weight: bold;">Atributo no documentado.</strong></li>
</ul>