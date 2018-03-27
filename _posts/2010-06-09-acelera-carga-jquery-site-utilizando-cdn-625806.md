---
ID: 2479
post_title: >
  Acelera la carga de jQuery en tu site
  utilizando un CDN
author: JuanMa Garrido
post_excerpt: |
  <h3>
  ¿Cómo lo utilizo en mi site?
  </h3>
  <p>
  Para cargar jQuery desde el CDN de Google, pondriamos en el
  HEADER de nuestro HTML lo siguiente:
  </p>
  <pre style="background-color: #ecfcea;">
  <code>
  <script src="http://www.google.com/jsapi" type="text/javascript">
  </script><script type="text/javascript">
  
  google.load("jquery", "1.3.2");
  </script>
  </code>
  </pre>
  <p>
  Y para cargarlo desde el CDN de Microsoft pondriamos esto:
  </p>
  <pre style="background-color: #ecfcea;">
  <code>
  <script type="text/javascript" src=
  "http://ajax.microsoft.com/ajax/jquery/jquery-1.4.2.js">
  </script>
  </code>
  </pre>
  <h3>
  ¿Qué ventajas tiene usar un CDN?
  </h3>
  <p>
  Usar CDN tiene varias ventajas:
  </p>
  <ul>
  <li>Liberas a tu servidor de la carga de estos archivos
  </li>
  <li>Incrementas las posibilidades de que el fichero esté
  cacheado, ya que otros sitios que usen tu CDN enlazaran al mismo
  fichero
  </li>
  <li>Un CDN muy probablemente servirá el fichero más rapido que
  desde tu propio servidor de hosting
  </li>
  </ul>
  <h3>
  ¿Qué CDN gratuito me conviene utilizar?
  </h3>
  <p>
  Pues en <a href=
  "http://royal.pingdom.com/2010/05/11/cdn-performance-downloading-jquery-from-google-microsoft-and-edgecast-cdns/">
  Pingdom.com</a> han hecho una comparativa de rendimiento entre
  los de Google, Microsoft y Edgecast, y han llegado a unas
  interesantes conclusiones:
  </p>
  <ul>
  <li>El CDN de Google es el más lento de los 3 en America del
  Norte y en Europa
  </li>
  <li>En Europa el CDN de Microsoft es el más rapido
  </li>
  <li>En América del Norte, el CDN de Edgecast es el más rapido
  </li>
  <li>El CDN de Edgecast gana en terminos de rendimiento medio
  </li>
  </ul>
  <p>
  <img title="Comparativa CDN gratuito" src=
  http://stc.obolog.net/multimedia/fotos/626000/625806/625806-257853.jpg
  alt="Comparativa CDN gratuito" width="580" height="300"/>
  </p>
  <p>
  Un último factor a considerar es que el CDN más usado es con el
  que tendras más posibilidades de tener tu archivo cacheado, pero
  por ahora no hay datos de cual es el CDN más utilizado.
  </p>
  <p>
  ¿Y tu? ¿Qué opinas del uso del CDN? ¿Lo utilizas? ¿Cuál utilizas?
  ¿Alguno gratuito que no hayamos nombrado aquí?
  </p>
  <h2>
  Enlaces y más
  </h2>
  <ul>
  <li>
  <a href="http://code.google.com/intl/es-ES/apis/ajaxlibs/">CDN
  Google</a>
  </li>
  <li>
  <a href="http://www.asp.net/ajaxlibrary/cdn.ashx">CDN
  Microsoft</a>
  </li>
  <li>
  <a href="http://www.edgecast.com/index.htm">Edgecast</a>
  </li>
  <li>
  <a href=
  "http://royal.pingdom.com/2010/05/11/cdn-performance-downloading-jquery-from-google-microsoft-and-edgecast-cdns/">
  CDN performance: Downloading jQuery from Google, Microsoft, and
  Edgecast CDNs</a>
  </li>
  <li>
  <a href=
  "http://encosia.com/2008/12/10/3-reasons-why-you-should-let-google-host-jquery-for-you/">
  3 reasons why you should let Google host jQuery for you</a>
  </li>
  <li>
  <a href=
  "http://robertoyudice.com/desarrollo-web/porque-deberias-de-usar-un-cdn-content-delivery-network-y-como/">
  Porque deberias de usar un CDN (Content delivery network) y
  como</a>
  </li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/acelera-carga-jquery-site-utilizando-cdn-625806/
published: true
post_date: 2010-06-09 23:37:00
---
<p style="text-align: left;">Si utilizas jQuery, es una buena idea que cargues la librería desde un CDN (Content Delivery Network).<!--more--></p>

<h3>Pero, ¿qué es un CDN?</h3>
Es el nombre que recibe un grupo de servidores repartidos por todo el mundo en puntos estratégicos y pensados para la distribución de ficheros.

Hay varios <strong>CDN’s gratuitos</strong>, entre ellos el de <a href="https://developers.google.com/speed/libraries/">Google</a>, el de <a href="http://www.asp.net/ajaxlibrary/cdn.ashx">Microsoft</a> y el de .

Tambien hay  CDN's de pago. Algunos puede que te suenen como <a href="http://www.edgecast.com/">Edgecast</a>, <a href="http://spanish.akamai.com/enes/">Akamai</a> o <a href="http://aws.amazon.com/cloudfront/" target="_blank">Amazon CloudFront</a>
<h3>¿Cómo funciona un CDN?</h3>
La idea es que en vez de cargar las librerias desde tu servidor de hosting, las cargues directamente desde el CDN. De este modo cuando se haga la petición se cargará la librería (o librerias solicitadas) desde el nodo mas cercano al cliente con lo que se
cargará más rapido.
<h3>¿Cómo lo utilizo en mi site?</h3>
Para cargar jQuery desde el CDN de Google, pondriamos en el
HEADER de nuestro HTML lo siguiente:
<pre class="lang:xhtml decode:true">&lt;script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"&gt;&lt;/script&gt;</pre>
Y para cargarlo desde el CDN de Microsoft pondriamos esto:
<pre class="lang:xhtml decode:true">&lt;script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-2.0.0.min.js
" type="text/javascript"&gt;&lt;/script&gt;</pre>
<h3>¿Qué ventajas tiene usar un CDN?</h3>
Usar CDN tiene varias ventajas:
<ul>
	<li>Liberas a tu servidor de la carga de estos archivos</li>
	<li>Incrementas las posibilidades de que el fichero esté cacheado, ya que otros sitios que usen tu CDN enlazaran al mismo fichero</li>
	<li>Un CDN muy probablemente servirá el fichero más rapido que desde tu propio servidor de hosting</li>
</ul>
<h3>¿Qué CDN gratuito me conviene utilizar?</h3>
Pues en  <a href="http://royal.pingdom.com/2010/05/11/cdn-performance-downloading-jquery-from-google-microsoft-and-edgecast-cdns/">Pingdom.com</a> han hecho una comparativa de rendimiento entre los de Google, Microsoft y Edgecast, y han llegado a unas interesantes conclusiones:
<ul>
	<li>El CDN de Google es el más lento de los 3 en America del Norte y en Europa</li>
	<li>En Europa el CDN de Microsoft es el más rapido</li>
	<li>En América del Norte, el CDN de Edgecast es el más rapido</li>
	<li>El CDN de Edgecast gana en terminos de rendimiento medio</li>
</ul>
<img title="Comparativa CDN gratuito" src="http://stc.obolog.net/multimedia/fotos/626000/625806/625806-257853.jpg" alt="Comparativa CDN gratuito" width="580" height="300" />

Un último factor a considerar es que el CDN más usado es con el que tendras más posibilidades de tener tu archivo cacheado, pero por ahora no hay datos de cual es el CDN más utilizado.

¿Y tu? ¿Qué opinas del uso del CDN? ¿Lo utilizas? ¿Cuál utilizas?
¿Alguno gratuito que no hayamos nombrado aquí?
<h2>Enlaces y más</h2>
<ul>
	<li><a href="http://code.google.com/intl/es-ES/apis/ajaxlibs/">CDN Google</a></li>
	<li><a href="http://www.asp.net/ajaxlibrary/cdn.ashx">CDN Microsoft</a></li>
	<li><a href="http://www.edgecast.com/index.htm">Edgecast</a></li>
	<li><a href="http://royal.pingdom.com/2010/05/11/cdn-performance-downloading-jquery-from-google-microsoft-and-edgecast-cdns/">CDN performance: Downloading jQuery from Google, Microsoft, and
Edgecast CDNs</a></li>
	<li><a href="http://encosia.com/2008/12/10/3-reasons-why-you-should-let-google-host-jquery-for-you/">3 reasons why you should let Google host jQuery for you</a></li>
	<li><a href="http://robertoyudice.com/desarrollo-web/porque-deberias-de-usar-un-cdn-content-delivery-network-y-como/">Porque deberias de usar un CDN (Content delivery network) y
como</a></li>
</ul>