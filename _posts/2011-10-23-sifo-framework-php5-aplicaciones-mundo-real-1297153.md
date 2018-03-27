---
ID: 2497
post_title: >
  SIFO, el framework de PHP5 para
  aplicaciones del mundo real
author: JuanMa Garrido
post_excerpt: |
  <h2>
  Concretemos... ¿qué me ofrece SIFO?
  </h2>
  <h3>
  Patron MVC
  </h3>
  <p>
  SIFO utliiza el <a href=
  "http://es.wikipedia.org/wiki/Modelo_Vista_Controlador" target=
  "_blank">patrón MVC</a> (Modelo-Vista-Controlador) para separar
  tu proyecto en 3 capas:
  </p>
  <p>
  <img class="undefined" style="width: 300px;" title="" src=
  http://stc.obolog.net/photos/4e9b/4e9b1d8188a52s29286_p.jpg
  alt=" TAGS:" align="right"/>
  </p>
  <ul>
  <li>
  <strong>Modelos</strong>: Contienen la lógica de tu negocio. De
  donde se obtienen los datos (consultas a la base de datos)
  </li>
  <li>
  <strong>Vistas</strong>: Son los templates HTML con un poco de
  lógica (iteraciones). Es la capa de presentación de tu web. Por
  defecto se utiliza <a href="http://www.smarty.net/" target=
  "_blank">Smarty</a> como sistema de plantillas
  </li>
  <li>
  <strong>Controladores</strong>: Combinan las 2 capas anteriores
  con la lógica necesaria
  </li>
  </ul>
  <h3>
  Múltiples entornos de trabajo
  </h3>
  <p>
  A través del fichero
  <code>config/domains.config.php&nbsp;</code>podrás configurar tu
  aplicación para que se comporte diferente segun el entorno
  (dominio) en el que estés. Lo normal es utilizar al menos 2
  dominios: Uno para producción
  <code>[mycoolsite.com]</code>&nbsp;y otro local para desarrollo
  <code>[mycoolsite.local]</code>
  </p>
  <p>
  Entre otras cosas, puedes configurar para cada entorno:
  </p>
  <ul>
  <li>Mostrar/Ocultar el debug
  </li>
  <li>Los idiomas que acepta tu aplicación
  </li>
  <li>Los datos de acceso a los diferentes servicios, comandos de
  inicio, configuraciones master/slave (mysql)&nbsp;
  </li>
  </ul>
  <div>
  <h3>
  Routing
  </h3>
  <p>
  Cuando escribes una URL hay un mapeo que relaciona esa
  dirección con el controlador que debe contestar. Este mapeo
  está en el
  archivo&nbsp;<code>config/router.config.php</code>.&nbsp;
  </p>
  <p>
  Si quieres utilizar URL's traducidas puedes utilizar los
  archivos <code>config/router_xx_XX.config.php</code>. (donde
  xx_XX es el country code).
  </p>
  <h3>
  Debug potente
  </h3><a class="thickbox" href=
  http://stc.obolog.net/photos/4e9b/4e9b29a468db8s97996.jpg"><img class="fotobonita
  title="" src=
  http://stc.obolog.net/photos/4e9b/4e9b29a468db8s97996_t.jpg
  alt=" TAGS:" align="right"/></a>
  <p>
  El debug de SIFO te muestra un monton de información
  interesante sobre tu aplicacion:
  </p>
  <ul style="width: 65%;">
  <li>
  <em>Benchmark</em>: Analisis completo de los tiempos de
  ejecución por archivo y por metodo
  </li>
  <li>Parámetros que recibe cada <em>controlador</em>
  </li>
  <li>Valores que recibe cada <em>template</em> (smarty)
  </li>
  <li>
  <em>Queries</em> ejecutadas por la Base de Datos
  </li>
  <li>Datos almacenados en la <em>sesion</em> (y poder hacer
  <code>kill session</code>)
  </li>
  <li>Datos almacenados en las <em>cookies</em> del usuario
  </li>
  <li>Control de la <em>cache</em>
  </li>
  </ul>
  <div>
  Multilenguaje
  </div>
  <p>
  Con SIFO podrá hacer tu proyecto multilenguaje de una forma
  sencilla. Incluso tiene herramientas de traducción (basadas en
  archivos de configuracion o en bases de datos) que puedes
  utilizar para que tus colegas "no-programadores" te ayuden a
  introducir las traducciones.
  </p>
  <p>
  Todos los templates de smarty vienen con los plugins i18n que
  te permiten hacer tus templates en un único lenguaje e indicar
  qué frases deben ser traducidas.
  </p>
  </div>
  <div>
  <img class="fotobonita" title="" src=
  http://stc.obolog.net/photos/4ea4/4ea441e51a0cfs39120_p.jpg
  alt=" TAGS:" align="center"/>
  <div>
  <h3>
  Herencia entre proyectos
  </h3>
  <div>
  <p>
  <img class="fotobonita" title="" src=
  http://stc.obolog.net/photos/4ea4/4ea443913d2cds12737_p.jpg
  alt=" - " width="150" align="left"/>La herencia entre
  proyectos te permitirá crear varios proyectos (instancias)
  basados en un "padre".
  </p>
  <p>
  Asi, estos proyectos heredaran del "padre" sus
  configuraciones, templates controladores, modelos,
  librerias... con la posibilidad de sobreescribir, extender
  o limitar estas funcionalidades heredadas.
  </p>
  <h3>
  Y mucho mas...
  </h3>
  <ul>
  <li>
  <em>Lazy loading</em> (carga sólo las clases que
  necesites)
  </li>
  <li>Multiples <em>Bases de Datos</em> (Redis, Oracle,
  MySQL...)
  </li>
  <li>Crons en PHP desde <em>Linea de Comandos</em>
  </li>
  <li>Distinción entre contenido <em>Dinámico y Estático</em>
  (utiliza un CDN para tus imagenes, CSS...)
  </li>
  <li>Un montón de <em>clases
  útiles</em>&nbsp;(Geolocalización, Facebook, Twitter,
  Sphinx, Amazon...)
  </li>
  <li>
  <em>Extensible</em> (Utiliza tus propias librerias o
  clases)
  </li>
  <li>Y mas...
  </li>
  </ul>
  <h2>
  Me has convencido... Quiero probarlo ya!!
  </h2>
  <h3>
  Vale, vale.... Pues hay varias formas de conseguir tu copia
  de <a href="http://sifo.me/download" target=
  "_blank">SIFO</a> &nbsp;
  </h3>
  <ul>
  <li>Desde <strong><a href=
  "https://github.com/alombarte/SIFO" target=
  "_blank">Github</a></strong>
  </li>
  <li>Desde <strong><a href="http://code.google.com/p/sifo/"
  target="_blank">Google Code</a></strong>
  </li>
  </ul>
  <div>
  Si no quieres complicarte la vida con sistemas de control
  de versiones <a href=
  "http://code.google.com/p/sifo/downloads/list" target=
  "_blank">puedes bajarte un archivo comprimido</a>&nbsp;con
  todo el código de SIFO pero ¡OJO!... no contiene la ultima
  versión.
  </div>
  <div>
  &nbsp;
  </div>
  <div>
  Toda la info y documentación (actual y futura) sobre SIFO
  la puedes encontrar en su <a href="http://sifo.me/" target=
  "_blank">sitio oficial</a>&nbsp;
  </div>
  <div>
  &nbsp;
  </div>
  <hr />
  <p>
  ¿Que te ha parecido este framework? ¿Lo conocias? ¿Lo has
  probado? ¿Conoces alguno similar?
  </p>
  <p>
  Esperamos vuestros comentarios
  </p>
  </div>
  </div>
  </div>
layout: post
permalink: >
  https://pixelovers.com/sifo-framework-php5-aplicaciones-mundo-real-1297153/
published: true
post_date: 2011-10-23 13:00:00
---
<img class="fotobonita" title="" src="http://static.sifo.me/css/images/logo.jpg" alt=" - " width="498" height="242" />
<h2>¿Qué es SIFO?</h2>
<strong><a href="http://sifo.me/" target="_blank">SIFO</a></strong> es un framework que surge de la necesidad de reaprovechar todas las <em>soluciones
"definitivas"</em> que se iban descubriendo en el trabajo del día a día, y que se podian utilizar en más proyectos.

Con soluciones "definitivas" me refiero a las soluciones que despues de haber sido probadas en el mundo real han demostrado ser la mejor opción (cómo implementar la internacionalización, el trabajo en multiples entornos, la cache, el debug, etc...)

Lleva ya funcionando un tiempo en algunos sitios, tanto sitios de mucho trafico con multiples servidores cómo en sitios más modestos, asi que su practicidad y flexibilidad está más que probada.

<!--more-->

SIFO contiene un montón de librerias y clases que resuelven de forma sencilla los problemas básicos que te vas a encontrar en el desarrollo de un sitio web, lo que <strong>te permite centrar tu atención en resolver la lógica de tu negocio</strong>.

Además es gratuito!
<h2>Concretemos... ¿qué me ofrece SIFO?</h2>
<h3>Patron MVC</h3>
SIFO utliiza el <a href="http://es.wikipedia.org/wiki/Modelo_Vista_Controlador" target="_blank">patrón MVC</a> (Modelo-Vista-Controlador) para separar tu proyecto en 3 capas:
<ul>
	<li><strong>Modelos</strong>: Contienen la lógica de tu negocio. De donde se obtienen los datos (consultas a la base de datos)</li>
	<li><strong>Vistas</strong>: Son los templates HTML con un poco de lógica (iteraciones). Es la capa de presentación de tu web. Por defecto se utiliza <a href="http://www.smarty.net/" target="_blank">Smarty</a> como sistema de plantillas</li>
	<li><strong>Controladores</strong>: Combinan las 2 capas anteriores con la lógica necesaria</li>
</ul>
<img class="undefined" title="" src="http://stc.obolog.net/photos/4e9b/4e9b1d8188a52s29286_p.jpg" alt=" TAGS:" width="562" height="306" />
<h3>Múltiples entornos de trabajo</h3>
A través del fichero <code>config/domains.config.php </code>podrás configurar tu aplicación para que se comporte diferente segun el entorno (dominio) en el que estés. Lo normal es utilizar al menos 2 dominios: Uno para producción <code>[mycoolsite.com]</code> y otro local para desarrollo <code>[mycoolsite.local]</code>

Entre otras cosas, puedes configurar para cada entorno:
<ul>
	<li>Mostrar/Ocultar el debug</li>
	<li>Los idiomas que acepta tu aplicación</li>
	<li>Los datos de acceso a los diferentes servicios, comandos de inicio, configuraciones master/slave (mysql)</li>
</ul>
<div>
<h3>Routing</h3>
Cuando escribes una URL hay un mapeo que relaciona esa dirección con el controlador que debe contestar. Este mapeo está en el archivo <code>config/router.config.php</code>.

Si quieres utilizar URL\'s traducidas puedes utilizar los archivos <code>config/router_xx_XX.config.php</code>. (donde xx_XX es el country code).
<h3>Debug potente</h3>
El debug de SIFO te muestra un monton de información interesante sobre tu aplicacion:
<ul style="width: 65%;">
	<li><em>Benchmark</em>: Analisis completo de los tiempos de ejecución por archivo y por metodo</li>
	<li>Parámetros que recibe cada <em>controlador</em></li>
	<li>Valores que recibe cada <em>template</em> (smarty)</li>
	<li><em>Queries</em> ejecutadas por la Base de Datos</li>
	<li>Datos almacenados en la <em>sesion</em> (y poder hacer <code>kill session</code>)</li>
	<li>Datos almacenados en las <em>cookies</em> del usuario</li>
	<li>Control de la <em>cache</em></li>
</ul>
</div>
<div></div>
<div>
<div>

<a href="http://pixelovers.com/app/uploads/sites/7/2011/10/4e9b29a468db8s979962.jpg"><img class="alignnone  wp-image-2693" src="http://pixelovers.com/app/uploads/sites/7/2011/10/4e9b29a468db8s979962.jpg" alt="" width="518" height="481" /></a>
<h3>Multilenguaje</h3>
Con SIFO podrá hacer tu proyecto multilenguaje de una forma sencilla. Incluso tiene herramientas de traducción (basadas en archivos de configuracion o en bases de datos) que puedes utilizar para que tus colegas "no-programadores" te ayuden a introducir las traducciones.

Todos los templates de smarty vienen con los plugins i18n que te permiten hacer tus templates en un único lenguaje e indicar qué frases deben ser traducidas.

</div>
<div><img class="fotobonita" title="" src="http://stc.obolog.net/photos/4ea4/4ea441e51a0cfs39120_p.jpg" alt=" TAGS:" align="center" /></div>
<div>
<h3>Herencia entre proyectos</h3>
<div>

<a href="http://pixelovers.com/app/uploads/sites/7/2011/10/4ea443913d2cds127372.jpg"><img class="alignnone size-full wp-image-2695" src="http://pixelovers.com/app/uploads/sites/7/2011/10/4ea443913d2cds127372.jpg" alt="" width="256" height="256" /></a>
La herencia entre proyectos te permitirá crear varios proyectos (instancias)
basados en un "padre".

Asi, estos proyectos heredaran del "padre" sus configuraciones, templates controladores, modelos, librerias... con la posibilidad de sobreescribir, extender
o limitar estas funcionalidades heredadas.
<h3>Y mucho mas...</h3>
<ul>
	<li><em>Lazy loading</em> (carga sólo las clases que necesites)</li>
	<li>Multiples <em>Bases de Datos</em> (Redis, Oracle, MySQL...)</li>
	<li>Crons en PHP desde <em>Linea de Comandos</em></li>
	<li>Distinción entre contenido <em>Dinámico y Estático </em>(utiliza un CDN para tus imagenes, CSS...)</li>
	<li>Un montón de <em>clases útiles</em> (Geolocalización, Facebook, Twitter,
Sphinx, Amazon...)</li>
	<li><em>Extensible</em> (Utiliza tus propias librerias o clases)</li>
	<li>Y mas...</li>
</ul>
<h2>Me has convencido... Quiero probarlo ya!!</h2>
<h3>Vale, vale.... Pues hay varias formas de conseguir tu copia de <a href="http://sifo.me/download" target="_blank">SIFO</a></h3>
<ul>
	<li>Desde <strong><a href="https://github.com/alombarte/SIFO" target="_blank">Github</a></strong></li>
	<li>Desde <strong><a href="http://code.google.com/p/sifo/" target="_blank">Google Code</a></strong></li>
</ul>
<div>Si no quieres complicarte la vida con sistemas de control de versiones <a href="http://code.google.com/p/sifo/downloads/list" target="_blank">puedes bajarte un archivo comprimido</a> con todo el código de SIFO pero ¡OJO!... no contiene la ultima
versión.</div>
<div></div>
<div>Toda la info y documentación (actual y futura) sobre SIFO la puedes encontrar en su <a href="http://sifo.me/" target="_blank">sitio oficial</a></div>
<div></div>

<hr />

¿Que te ha parecido este framework? ¿Lo conocias? ¿Lo has probado? ¿Conoces alguno similar?

Esperamos vuestros comentarios

</div>
</div>
</div>