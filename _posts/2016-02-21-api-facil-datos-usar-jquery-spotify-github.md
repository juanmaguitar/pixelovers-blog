---
ID: 3576
post_title: 'Obteniendo datos de API&#8217;s (Spotify, Github&#8230;) fácilmente con jQuery'
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/api-facil-datos-usar-jquery-spotify-github/
published: true
post_date: 2016-02-21 12:31:12
---
<a href="http://pixelovers.com/app/uploads/sites/7/2016/02/phoyo-header.png" rel="attachment wp-att-3598"><img class="alignnone size-full wp-image-3598" src="http://pixelovers.com/app/uploads/sites/7/2016/02/phoyo-header.png" alt="phoyo-header" width="680" height="360" /></a>

La mayoria de los proyectos frontend "modernos" lidian de una manera u otra con API's. Pero cuando lidiamos con API's externas y queremos conectar con ellas via <a href="https://es.wikipedia.org/wiki/AJAX">AJAX</a> hay una serie de factores que tenemos que tener en cuenta.

<!--more-->
<strong>JSON</strong>

Primero, que el formato de intercambio de datos standard es JSON. Este formato, tal y como llega de forma nativa a través del objeto <a href="https://developer.mozilla.org/es/docs/XMLHttpRequest" target="_blank">XMLHttpRequest</a> es simplemente una cadena de texto. Para poder tratarlo correctamente tendremos que convertirlo antes en objeto Javascript (con  <a href="https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/JSON/parse"><code>JSON.parse()</code></a> por ejemplo).

<strong>Same-origin policy</strong>

Por otro lado AJAX tiene una limitación nativa llamada <em>"Same-origin policy"</em> (la politica del mismo origen) que básicamente limita las conexiones AJAX desde un archivo JS solo al dominio desde el que se ha servido el propio archivo JS.

Para lidiar con esta limitacion hay dos "soluciones" que la mayoria de las API publicas ofrecen para poder tener acceso a sus datos: JSONP y CORS

<strong>JSONP</strong>

<a href="http://es.wikipedia.org/wiki/JSONP">JSONP</a> (<em>JSON con Padding</em>) es una <em>técnica</em> mediante la que podemos obtener <strong>y tratar</strong> JSON desde otros dominios (utilizando javascript)

Con esta tecnica/hack obtenemos el JSON pasado como parámetro a una función que se ejecuta en el cliente.

<strong>CORS</strong>

<a href="http://enable-cors.org/">CORS</a> (Cross-Origin Resource Sharing) permite realizar peticiones a otros dominios siempre y cuando el dominio de destino (servidor) esté de acuerdo en recibir peticiones del dominio de origen.

Es una tecnología (<a href="http://www.w3.org/TR/cors/">especificación W3C</a>) <a href="http://caniuse.com/#feat=cors">implementada en los navegadores actuales</a>, que intercambia ciertas cabeceras HTTP con el servidor de destino para saber si debe permitir o no el intercambio de datos.

Para cada petición que se hace al servidor, éste devuelve una respuesta con unas cabeceras añadidas ( entre ellas <code>Access-Control-Allow-Origin</code> ) donde indica desde qué dominios puedes acceder a sus API's (si el valor es <code>Access-Control-Allow-Origin: *</code> puedes acceder desde cualquier dominio)

Cada vez más <a href="http://enable-cors.org/resources.html#apis">API's publicas</a> <a href="http://www.w3.org/wiki/CORS_Enabled#Who_is_doing_it_already.3F">permiten CORS</a> pero la mayoria ofrecen solo <a href="http://www.programmableweb.com/category/all/apis?data_format=21174">JSONP</a>.

<h2>Accediendo a API's sencillas utilizando <a href="http://api.jquery.com/jquery.ajax/" target="_blank">$.ajax()</a></h2>

Cuando empezamos a investigar cómo utilizar una determinada API encontramos diferentes maneras de acceder a ellas (algunas más fáciles que otras).

Algunas API's requieren que añadas un token en cada petición,  en otras además tienes que especificar desde su web (de developers) los dominios desde los que realizarás las peticiones (sólo serán aceptadas las peticiones que provengan de esos dominio), otras sólo permiten acceder a sus datos utilizando sus propias SDK... y así hasta unas cuantas formas más de "controlar" quien y cómo acceden a sus datos via API.

Pero... hay unas cuantas API's que se podrian considerar <em>sencillas</em> porque:

<ul>
    <li>Ni requieren token ni ninguna configuracion extra</li>
    <li>Tienen CORS implementado para cualquier origen</li>
</ul>

Por tanto, cualquier petición que hagamos a su API desde cualquier dominio (<code>localhost</code> por ejemplo) nos va a funcionar sin problemas.

Además, el método <code>$.ajax</code>, aparte de permitirnos expresar la petición de forma semántica y sencilla, tiene la ventaja añadida de que <em>devuelve directamente el objeto JSON transformado a objeto javascript</em>

Asi que, sabiendo todo esto, podemos utilizar el método <a href="http://api.jquery.com/jquery.ajax/"><code>$.ajax()</code></a> para hacer peticiones AJAX a estas API's de forma MUY sencilla.

<strong>La API de GitHub</strong>

Por ejemplo, la API de <strong><a href="https://developer.github.com/v3/">github</a> </strong>implementa <a href="https://developer.github.com/v3/#cross-origin-resource-sharing">CORS para cualquier origen</a>, lo que significa que podemos hacer peticiones utilizando <code>$.ajax</code> de forma tan sencilla como:

<pre class="lang:js decode:true ">  $.ajax({
    url: "https://api.github.com/users/juanmaguitar/repos",
    success: function( oData ) {
     // do things w/ oData (JS object)
    }
  })</pre>

Si miramos las cabeceras de esta petición (<code>request</code> y <code>response</code>) podemos ver lo siguiente

<a href="http://pixelovers.com/app/uploads/sites/7/2016/02/header-github-1.png" rel="attachment wp-att-3586"><img class="alignnone size-full wp-image-3586" src="http://pixelovers.com/app/uploads/sites/7/2016/02/header-github-1.png" alt="header-github" width="443" height="573" /></a>

Como la cabecera <code>Origin: http://localhost</code> enviada por nuestro navegador (<a href="http://enable-cors.org/client.html">que soporta CORS</a>) es un origen válido para la cabecera <code>Access-Control-Allow-Origin: *</code> devuelta por el servidor, la respuesta es válida y contiene la info pedida sin que tengamos que hacer nada mas.

Ejemplo en acción:

<iframe width="100%" height="300" src="//jsfiddle.net/juanma/5zahpaac/embedded/js,result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

<strong>La API de Spotify</strong>

La API de Spotify requiere autorización extra para algunas acciones, pero para sólo consultar información (utilizando <code>GET</code>) la API acepta consultas desde cualquier dominio... al menos hasta la fecha de hoy ;)

<a href="http://pixelovers.com/app/uploads/sites/7/2016/02/Captura-de-pantalla-2016-02-21-a-las-10.22.59.png" rel="attachment wp-att-3587"><img class="alignnone size-full wp-image-3587" src="http://pixelovers.com/app/uploads/sites/7/2016/02/Captura-de-pantalla-2016-02-21-a-las-10.22.59.png" alt="Captura de pantalla 2016-02-21 a las 10.22.59" width="574" height="585" /></a>

Por tanto las consultas a esta API quedan tan sencillas como:

<pre class="lang:js decode:true">  $.ajax({
    url: "https://api.spotify.com/v1/search?type=artist&amp;query=led%20zeppelin",
    success: function( oData ) {
     // do things w/ oData (JS object)
    }
  })</pre>

En la petición <a href="http://api.jquery.com/jquery.ajax/"><code>$.ajax()</code></a> podemos especificar en el <code>dataType</code> el tipo de datos que vamos a recibir. Si no lo especificamos, jQuery tratará de averiguarlo basándose en el <code>MIME type</code> de la respuesta.

Las peticiones marcadas (específicamente o automáticamente) como <a href="http://api.jquery.com/jquery.ajax/"><code>dataType: "json"</code></a>, son devueltas a la función callback <code>sucess</code> ya convertidas a objeto javascript.

<pre class="lang:js decode:true"> $.ajax({
    url: "https://api.spotify.com/v1/search?type=artist&amp;query=led%20zeppelin",
    dataType: "json",
    success: function( oData ) {
     // do things w/ oData (JS object)
     }
  })</pre>

Si queremos pasar parámetros podemos concatenarlos a la URL pasada en la propiedad url o podemos pasarlos a través de la propiedad <code>data</code> del objeto de configuración

<pre class="lang:js decode:true"> $.ajax({
    url: "https://api.spotify.com/v1/search",
    dataType: "json",
    data: {
      type: "artist",
      query : "led zeppelin"
    },
    success: function( oData ) {
     // do things w/ oData (JS object)
    }
  })</pre>

Ejemplo en acción:

<iframe width="100%" height="600" src="//jsfiddle.net/juanma/nfnt1qf9/embedded/js,html,result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

¿Qué te ha parecido este articulo? ¿Alguna API "sencilla" que estés utilizando y quieras compartir?