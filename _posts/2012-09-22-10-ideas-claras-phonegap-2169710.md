---
ID: 2501
post_title: 10 Ideas Claras sobre PhoneGap
author: JuanMa Garrido
post_excerpt: |
  <div style="margin-left: 2em;">
  <ol style="-webkit-padding-start: 0;">
  <li style="margin: 30px 0;">
  <p>
  <strong>PhoneGap es una tecnologia contenedora de
  aplicaciones que nos permite crear, utilizando HTML, CSS y
  Javascript, aplicaciones para móviles que se instalan
  nativamente</strong>
  </p>
  <p>
  <img style="max-width: 500px;" src=
  http://phonegap.com/uploads/artwork/Build-Diagram-3.png
  alt=""/>
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  <strong>La interfaz de una aplicación PhoneGap se crea
  utilizando HTML, CSS y Javascript</strong>. Esta interfaz
  nos la muestra PhoneGap a traves de un componente que es un
  navegador que toma el 100% del ancho y el 100% del alto de
  nuestro dispositivo.
  </p>
  <p>
  <img style="max-width: 200px; margin: 10px auto;" src=
  http://phonegap.com/uploads/2012/05/web-view_updated.png
  alt=""/>
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  <strong>La vista web utilizada por PhoneGap es la <a href=
  "http://docs.phonegap.com/en/2.0.0/guide_cordova-webview_index.md.html#Embedding%20WebView">
  misma vista web utilizada por el sistema operativo
  nativo</a></strong>. Asi, en <em>iOS</em>, esta vista será
  la clase <code>UIWebView</code> de Objective C; en
  <em>Android</em> será el componente
  <code>android.webkit.WebView</code>.
  </p>
  <p>
  <em>Al haber diferencias en los motores de renderizado web
  entre sistemas operativos, tendremos que tener en cuenta
  esto para el desarrollo (y testeo) de nuestra
  interfaz.</em>
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  <strong><a href=
  "http://docs.phonegap.com/en/2.0.0/">PhoneGap proporciona
  una API</a> (Application Programming Interface) que nos
  permite acceder a las funcionalidades nativas de los
  dispositivos móviles</strong> utilizando Javascript. Así,
  podemos desarrollar toda la lógica de nuestra aplicación en
  Javascript y utilizar la API de PhoneGap para acceder a las
  funcionalidades nativas del dispositivo.
  </p>
  <p>
  <img style="max-width: 500px;" src=
  "http://phonegap.com/uploads/2012/05/API_updated.png" alt=
  ""/>
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  <strong>Además de las funcionalidades que nos ofrece
  PhoneGap “de serie”, podemos <a href=
  "http://docs.phonegap.com/en/2.0.0/guide_plugin-development_index.md.html">
  crear nuestros propios “plugins nativos</a>“.</strong> Los
  <a href=
  "http://www.tricedesigns.com/2012/03/01/phonegap-native-plugins/">
  plugins nativos</a> de PhoneGap nos permiten crear nuestras
  propias clases nativas con su correspondiente interfaz en
  Javascript para usarlas en nuestras aplicaciones PhoneGap
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  Las aplicaciones PhoneGap son desarrolladas con HTML, CSS y
  Javascript, sin embargo, <strong>el producto final de una
  aplicación PhoneGap es un archivo binario (IPA, APK, XAP…)
  listo para ser distribuido en los correspondientes
  marketplaces</strong>
  </p>
  <p>
  <img style="max-width: 500px;" src=
  http://phonegap.com/uploads/2012/05/export_updated.png
  alt=""/>
  </p>
  <p>
  Para aplicaciones iOS se genera un archivo IPA (iOS
  Application Archive), para Android se genera in archivo APK
  (Android Package), para Windows Phone se genera un archivo
  XAP (Application Package), etc…
  </p>
  <p>
  Estos formatos son los mismo utilizados por las
  aplicaciones “nativas” y se pueden distribuir a traves de
  los canales correspondientes (iTunes Store, Android Market,
  Amazon Market, BlackBerry App World, Windows Phone
  Marketplace, etc…)
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  <strong>La aplicacion cliente de PhoneGap se comunica con
  una aplicación en el servidor para recibir/enviar
  datos.</strong> La aplicacion en el servidor gestiona la
  logica de negocio y se comunica con la Base de Datos.
  </p>
  <p>
  <img style="max-width: 500px;" src=
  http://phonegap.com/uploads/2012/05/architecture_updated.png
  alt=""/>
  </p>
  <p>
  El servidor suele ser un servidor web (Apache, IIS, nginx,
  etc..) que sirve una aplicacion escrita en un lenguaje de
  servidor como Java, PHP, Ruby, Node.js, etc… PhoneGap es
  agnostico en cuanto a tecnologia backend y puede trabajar
  con cualquier aplicacion en el servidor que utilize
  protocolos web estándares.
  </p>
  <p>
  La aplicación en el servidor implementa la lógica de
  negocio y los cálculos, y generalmente se encarga de
  leer/escribir en la base de datos.
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  Las aplicaciones PhoneGap no suelen hablar directamente con
  una base de datos. Esta comunicacion es gestionada a traves
  de una aplicación en el servidor. <strong>La comunicacion
  con el servidor se suele basar en peticiones HTTP standard
  para contenido HTML, como <a href=
  "http://es.wikipedia.org/wiki/REST">REST-ful</a>, XML,
  JSON, <a href="http://en.wikipedia.org/wiki/SOAP">SOAP</a>
  o <a href=
  "http://es.wikipedia.org/wiki/WebSocket">websockets</a>.</strong>
  </p>
  <p>
  Serian exactamente las misma técnicas que utilizarias en
  una aplicación de escritorio basada en <a href=
  "http://en.wikipedia.org/wiki/Ajax_(programming">AJAX</a>
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  <strong>La arquitectura de la aplicación cliente suele
  utilizar un <a href=
  "http://en.wikipedia.org/wiki/Single-page_application">modelo
  de página única</a> donde toda la lógica de la aplicación
  está en una única pagina HTML.</strong> Esta pagina
  permanece cargada en memoria y los gestiona todo. Los datos
  se muestran actualizando el DOM HTML, los datos se guardan
  desde la aplicacion en el servidor a traves de técnicas
  AJAX y las variables se mantienen en memoria a traves de
  Javascript
  </p>
  </li>
  <li style="margin: 30px 0;">
  <p>
  Para desarrollar aplicaciones PhoneGap, <strong>se suelen
  utilizar frameworks (como <a href=
  "http://jquerymobile.com/">jQuery Mobile</a> y <a href=
  "http://www.sencha.com/products/touch/">Sencha Touch</a>)
  que nos facilitan hacer que nuestra app se comporte y se
  vea como una aplicación nativa.</strong>
  </p>
  </li>
  </ol>
  </div>
  <h3>
  Enlaces y más:
  </h3>
  <ul>
  <li>
  <a href=
  http://www.tricedesigns.com/2012/08/13/presentations-intro-to-phonegap-web-data-viz-phonegap-native-plugins/
  target="_blank">Presentations: Intro To PhoneGap, Web Data Viz
  &amp; PhoneGap Native Plugins</a>
  </li>
  <li>
  <a href="http://www.phonegap.com/blog" target="_blank">PhoneGap
  Blog</a>
  </li>
  <li>
  <a href=
  http://phonegap.com/2012/05/02/phonegap-explained-visually/
  target="_blank">PhoneGap Explained Visually</a>
  </li>
  </ul>
  <p style="margin: 0;">
  ¿Que opinas de PhoneGap? ¿Lo has utilizado ya? ¿Alguna
  alternativa mejor para desarrollo de aplicaciones para moviles?
  ¿Cual es tu experiencia? ¿Nos puedes recomendar algun framework
  para el desarrollo de la interfaz?&nbsp;Esperamos vuestros
  comentarios
  </p>
  <p style="margin: 0;">
  &nbsp;
  </p>
  <p style="margin: 0;">
  &nbsp;
  </p>
layout: post
permalink: >
  https://pixelovers.com/10-ideas-claras-phonegap-2169710/
published: true
post_date: 2012-09-22 10:36:00
---
<a href="http://pixelovers.com/app/uploads/sites/7/2012/09/Phonegap-Logo.png"><img class="alignnone wp-image-2870 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2012/09/Phonegap-Logo-300x300.png" alt="Phonegap-Logo" width="300" height="300" /></a>

<a href="http://www.phonegap.com/">PhoneGap</a> es una de las mejores opciones (y mi favorita) que existen en el mercado para crear aplicaciones para móviles utilizando HTML5 + CSS3 + JS.

Vamos a intentar dejar claras en este post 10 ideas fundamentales sobre PhoneGap.

<!--more-->

<!-- pagebreak -->
<div style="margin-left: 2em;">
<ol style="-webkit-padding-start: 0;">
	<li style="margin: 30px 0;"><strong>PhoneGap es una tecnologia contenedora de aplicaciones que nos permite crear, utilizando HTML, CSS y Javascript, aplicaciones para móviles que se instalan nativamente<a href="http://pixelovers.com/app/uploads/sites/7/2012/09/Build-Diagram-3.png"><img class="aligncenter size-full wp-image-2871" src="http://pixelovers.com/app/uploads/sites/7/2012/09/Build-Diagram-3.png" alt="Build-Diagram-3" width="1500" height="921" /></a></strong></li>
	<li style="margin: 30px 0;"><strong>La interfaz de una aplicación PhoneGap se crea utilizando HTML, CSS y Javascript</strong>. Esta interfaz nos la muestra PhoneGap a traves de un componente que es un navegador que toma el 100% del ancho y el 100% del alto de nuestro dispositivo.<a href="http://pixelovers.com/app/uploads/sites/7/2012/09/web-view_updated.png"><img class="aligncenter size-full wp-image-2872" src="http://pixelovers.com/app/uploads/sites/7/2012/09/web-view_updated.png" alt="web-view_updated" width="325" height="481" /></a></li>
	<li style="margin: 30px 0;"><strong>La vista web utilizada por PhoneGap es la <a href="http://docs.phonegap.com/en/2.0.0/guide_cordova-webview_index.md.html#Embedding%20WebView"> misma vista web utilizada por el sistema operativo nativo</a></strong>. Asi, en <em>iOS</em>, esta vista será la clase <code>UIWebView</code> de Objective C; en <em>Android</em> será el componente <code>android.webkit.WebView</code>.<em>Al haber diferencias en los motores de renderizado web entre sistemas operativos, tendremos que tener en cuenta esto para el desarrollo (y testeo) de nuestra interfaz.</em></li>
	<li style="margin: 30px 0;"><strong><a href="http://docs.phonegap.com/en/2.0.0/">PhoneGap proporciona una API</a> (Application Programming Interface) que nos permite acceder a las funcionalidades nativas de los dispositivos móviles</strong> utilizando Javascript. Así, podemos desarrollar toda la lógica de nuestra aplicación en Javascript y utilizar la API de PhoneGap para acceder a las funcionalidades nativas del dispositivo.<a href="http://pixelovers.com/app/uploads/sites/7/2012/09/API_updated.png"><img class="aligncenter size-full wp-image-2873" src="http://pixelovers.com/app/uploads/sites/7/2012/09/API_updated.png" alt="API_updated" width="526" height="196" /></a></li>
	<li style="margin: 30px 0;"><strong>Además de las funcionalidades que nos ofrece PhoneGap “de serie”, podemos <a href="http://docs.phonegap.com/en/2.0.0/guide_plugin-development_index.md.html"> crear nuestros propios “plugins nativos</a>“.</strong> Los <a href="http://www.tricedesigns.com/2012/03/01/phonegap-native-plugins/"> plugins nativos</a> de PhoneGap nos permiten crear nuestras propias clases nativas con su correspondiente interfaz en Javascript para usarlas en nuestras aplicaciones PhoneGap</li>
	<li style="margin: 30px 0;">Las aplicaciones PhoneGap son desarrolladas con HTML, CSS y Javascript, sin embargo, <strong>el producto final de una aplicación PhoneGap es un archivo binario (IPA, APK, XAP…) listo para ser distribuido en los correspondientes marketplaces<a href="http://pixelovers.com/app/uploads/sites/7/2012/09/export_updated.png"><img class="aligncenter size-full wp-image-2874" src="http://pixelovers.com/app/uploads/sites/7/2012/09/export_updated.png" alt="export_updated" width="452" height="182" /></a></strong>Para aplicaciones iOS se genera un archivo IPA (iOS Application Archive), para Android se genera in archivo APK (Android Package), para Windows Phone se genera un archivo XAP (Application Package), etc…Estos formatos son los mismo utilizados por las aplicaciones “nativas” y se pueden distribuir a traves de los canales correspondientes (iTunes Store, Android Market, Amazon Market, BlackBerry App World, Windows Phone Marketplace, etc…)</li>
	<li style="margin: 30px 0;"><strong>La aplicacion cliente de PhoneGap se comunica con una aplicación en el servidor para recibir/enviar datos.</strong> La aplicacion en el servidor gestiona la logica de negocio y se comunica con la Base de Datos.<a href="http://pixelovers.com/app/uploads/sites/7/2012/09/architecture_updated.png"><img class="aligncenter size-full wp-image-2875" src="http://pixelovers.com/app/uploads/sites/7/2012/09/architecture_updated.png" alt="architecture_updated" width="355" height="145" /></a>El servidor suele ser un servidor web (Apache, IIS, nginx, etc..) que sirve una aplicacion escrita en un lenguaje de servidor como Java, PHP, Ruby, Node.js, etc… PhoneGap es agnostico en cuanto a tecnologia backend y puede trabajar con cualquier aplicacion en el servidor que utilize protocolos web estándares.La aplicación en el servidor implementa la lógica de negocio y los cálculos, y generalmente se encarga de leer/escribir en la base de datos.</li>
	<li style="margin: 30px 0;">Las aplicaciones PhoneGap no suelen hablar directamente con una base de datos. Esta comunicacion es gestionada a traves de una aplicación en el servidor. <strong>La comunicacion con el servidor se suele basar en peticiones HTTP standard para contenido HTML, como <a href="http://es.wikipedia.org/wiki/REST">REST-ful</a>, XML, JSON, <a href="http://en.wikipedia.org/wiki/SOAP">SOAP</a> o <a href="http://es.wikipedia.org/wiki/WebSocket">websockets</a>.</strong>Serian exactamente las misma técnicas que utilizarias en una aplicación de escritorio basada en <a href="http://en.wikipedia.org/wiki/Ajax_(programming">AJAX</a></li>
	<li style="margin: 30px 0;"><strong>La arquitectura de la aplicación cliente suele utilizar un <a href="http://en.wikipedia.org/wiki/Single-page_application">modelo de página única</a> donde toda la lógica de la aplicación está en una única pagina HTML.</strong> Esta pagina permanece cargada en memoria y los gestiona todo. Los datos se muestran actualizando el DOM HTML, los datos se guardan desde la aplicacion en el servidor a traves de técnicas AJAX y las variables se mantienen en memoria a traves de Javascript</li>
	<li style="margin: 30px 0;">Para desarrollar aplicaciones PhoneGap, <strong>se suelen utilizar frameworks (como <a href="http://jquerymobile.com/">jQuery Mobile</a> y <a href="http://www.sencha.com/products/touch/">Sencha Touch</a>) que nos facilitan hacer que nuestra app se comporte y se vea como una aplicación nativa.</strong></li>
</ol>
</div>
<h3>Enlaces y más:</h3>
<ul>
	<li><a href="http://www.tricedesigns.com/2012/08/13/presentations-intro-to-phonegap-web-data-viz-phonegap-native-plugins/" target="_blank">Presentations: Intro To PhoneGap, Web Data Viz &amp; PhoneGap Native Plugins</a></li>
	<li><a href="http://www.phonegap.com/blog" target="_blank">PhoneGap Blog</a></li>
	<li><a href="http://phonegap.com/2012/05/02/phonegap-explained-visually/" target="_blank">PhoneGap Explained Visually</a></li>
</ul>
<p style="margin: 0;">¿Que opinas de PhoneGap? ¿Lo has utilizado ya? ¿Alguna alternativa mejor para desarrollo de aplicaciones para moviles? ¿Cual es tu experiencia? ¿Nos puedes recomendar algun framework para el desarrollo de la interfaz? Esperamos vuestros comentarios</p>