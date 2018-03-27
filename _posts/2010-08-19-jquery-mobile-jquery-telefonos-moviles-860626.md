---
ID: 2484
post_title: 'jQuery Mobile: jQuery para teléfonos moviles'
author: JuanMa Garrido
post_excerpt: |
  <p>
  El objetivo de jQuery Mobile es el de ofrecer las herramientas
  necesarias para “desarrollar JavaScript de alto nivel y con un
  interfaz unificado, que funcione en los navegadores de los
  dispositivos moviles mas utilizados”… suena bien, no?
  </p>
  <p>
  <img style=
  "float: right; margin: 20px; border: 0px initial initial;" src=
  http://stc.obolog.net/multimedia/fotos/861000/860626/860626-284171.jpg
  alt="" width="150"/>
  </p>
  <p>
  Entre otras cosas, este Framework nos ofrece unas plantillas
  optimizadas para moviles con la idea de unificar el diseño de
  widgets y layouts.
  </p>
  <p>
  Podeis ver algunos de estos diseños&nbsp;<a href=
  "http://jquerymobile.com/designs/" target="_blank">aquí</a>
  </p>
  <p>
  Pero la principal diferencia que ofrece este nuevo Framework es
  la amplia variedad de navegadores para moviles con la que estan
  trabajando para ofrecer la maxima compatibilidad.
  </p>
  <p>
  Para conseguir esto, estan utilizando una tabla
  llamada&nbsp;<a href="http://jquerymobile.com/gbs/" target=
  "_blank">Graded Browser Support</a>&nbsp;(ideada por Yahoo) en la
  que se clasifican los browsers y dispositivos en diferentes
  grados:
  </p>
  <ul>
  <li>
  <strong>Grado A&nbsp;</strong>: browser de alta calidad y en
  dispositivos populares.
  </li>
  <li>
  <strong>Grado B</strong>&nbsp;:&nbsp; browser de baja calidad
  en dispositivos populares o browser de alta calidad en pocos
  dispositivos del mercado
  </li>
  <li>
  <strong>Grado C</strong>&nbsp;: browser de baja calidad y poco
  utilizado .&nbsp;
  </li>
  </ul>
  <p>
  Podeis ver como queda esta tabla actualmente en la siguiente
  imagen:
  </p>
  <p>
  <img style=
  vertical-align: text-bottom; text-align: center; margin: 10px; border: 0px initial initial;
  src=
  http://stc.obolog.net/multimedia/fotos/861000/860626/860626-284173.jpg
  alt="" width="450"/>
  </p>
  <p>
  Pues bien, el objetivo de jQuery Mobile es ofrecer soporte a
  todos los navegadores de grado A y B
  </p>
  <p>
  Asi que, una buena noticia para los desarrolladores web ya que
  esta nueva herramienta nos va a facilitar (y mucho) el desarrollo
  de aplicaciones para moviles.
  </p>
  <p>
  ¡Ah! Se me olvidaba… está previsto que salga a finales de año.
  </p>
  <p>
  <em>&nbsp;NOTA:</em>
  </p>
  <p>
  <em>Hace poco pude “asistir” (via web) a una conferencia online
  en la que John Resig nos contaba como se debian abordar las
  pruebas de rendimiento y de compatibilidad en un desarrollo en JS
  para moviles. Podeis ver esta presentación en&nbsp;</em><a href=
  http://www.slideshare.net/jeresig/testing-mobile-javascript
  target="_blank"><em>slideshare</em></a><em>.</em>
  </p>
  <p>
  <em>En esta charla analizaba los dispositivos moviles y los
  browsers disponibles en el mercado y nos explicaba cómo hacer un
  testeo para moviles en condiciones (basado sobre todo, como
  decia, en&nbsp;</em><a href=
  "http://developer.yahoo.com/yui/articles/gbs/" target=
  "_blank"><em>Yahoo!s Graded Browser Support
  technique</em></a><em>).</em>
  </p>
  <p>
  <em>Todo lo que explicaba en esta charla es lo que estan
  aplicando para el desarrollo de jQuery Mobile&nbsp; ;-)</em>
  </p>
layout: post
permalink: >
  https://pixelovers.com/jquery-mobile-jquery-telefonos-moviles-860626/
published: true
post_date: 2010-08-19 21:19:00
---
<div id="_mcePaste" style="position: absolute; left: -10000px; top: 0px; width: 1px; height: 1px; overflow-x: hidden; overflow-y: hidden;">/app/uploads/sites/7/2010/08/860626-284172.jpg</div>
<img class="" style="float: left; margin: 20px;" src="/app/uploads/sites/7/2010/08/860626-284172.jpg" alt="" width="498" height="200" />

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

John Resig (creador de jQuery),  <a href="http://jquerymobile.com/2010/08/announcing-the-jquery-mobile-project/" target="_blank">nos presentaba</a>  hace unos dias oficialmente el nuevo proyecto del equipo de jQuery: <a href="http://jquerymobile.com" target="_blank">jQuery Mobile</a>.

Hasta ahora, para el desarrollo frontend de webs para dispositivos moviles habia que utilizar <a href="http://pixelovers.com/interfaces-graficas-usuario-plantillas-diseno-489880" target="_blank">plantillas de diseño</a> que podiamos encontrar por la red y plugins del tipo <a href="http://pixelovers.com/jqtouch-plugin-jquery-desarrollo-web-moviles-368493" target="_blank">jQTouch</a>, pero no habia una solucion integrada y estable… hasta ahora.

<!--more-->

El objetivo de jQuery Mobile es el de ofrecer las herramientas necesarias para “desarrollar JavaScript de alto nivel y con un interfaz unificado, que funcione en los navegadores de los dispositivos moviles mas utilizados”… suena bien, no?

<img class="" src="http://stc.obolog.net/multimedia/fotos/861000/860626/860626-284171.jpg" alt="" width="373" height="334" />

Entre otras cosas, este Framework nos ofrece unas plantillas optimizadas para moviles con la idea de unificar el diseño de widgets y layouts.

Podeis ver algunos de estos diseños <a href="http://jquerymobile.com/designs/" target="_blank">aquí</a>

Pero la principal diferencia que ofrece este nuevo Framework es la amplia variedad de navegadores para moviles con la que estan trabajando para ofrecer la maxima compatibilidad.

Para conseguir esto, estan utilizando una tabla llamada <a href="http://jquerymobile.com/gbs/" target="_blank">Graded Browser Support</a> (ideada por Yahoo) en la que se clasifican los browsers y dispositivos en diferentes
grados:
<ul>
	<li><strong>Grado A </strong>: browser de alta calidad y en dispositivos populares.</li>
	<li><strong>Grado B</strong> :  browser de baja calidad en dispositivos populares o browser de alta calidad en pocos dispositivos del mercado</li>
	<li><strong>Grado C</strong> : browser de baja calidad y poco utilizado .</li>
</ul>
Podeis ver como queda esta tabla actualmente en la siguiente imagen:

<img style="vertical-align: text-bottom; text-align: center; margin: 10px; border: 0px initial initial;" src="http://stc.obolog.net/multimedia/fotos/861000/860626/860626-284173.jpg" alt="" width="450" />

Pues bien, el objetivo de jQuery Mobile es ofrecer soporte a todos los navegadores de grado A y B

Asi que, una buena noticia para los desarrolladores web ya que esta nueva herramienta nos va a facilitar (y mucho) el desarrollo de aplicaciones para moviles.

¡Ah! Se me olvidaba… está previsto que salga a finales de año.

<em> NOTA:</em>

<em>Hace poco pude “asistir” (via web) a una conferencia online en la que John Resig nos contaba como se debian abordar las pruebas de rendimiento y de compatibilidad en un desarrollo en JS para moviles. Podeis ver esta presentación en </em><a href="http://www.slideshare.net/jeresig/testing-mobile-javascript" target="_blank"><em>slideshare</em></a><em>.</em>

<em>En esta charla analizaba los dispositivos moviles y los browsers disponibles en el mercado y nos explicaba cómo hacer un testeo para moviles en condiciones (basado sobre todo, como decia, en </em><a href="http://developer.yahoo.com/yui/articles/gbs/" target="_blank"><em>Yahoo!s Graded Browser Support
technique</em></a><em>).</em>

<em>Todo lo que explicaba en esta charla es lo que estan aplicando para el desarrollo de jQuery Mobile  ;-)</em>