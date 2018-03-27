---
ID: 2460
post_title: >
  Cómo geoposicionar un dispositivo con
  el navegador
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/geoposicionar-dispositivo-navegador-435853/
published: true
post_date: 2009-12-22 10:20:00
---
<p><img class="fotobonita" style="float: right;" title="Geoposicionamiento" src="/app/uploads/sites/7/2009/12/435853-206830.jpg" alt="Geoposicionamiento" /></p>

<p>Hace unos d&iacute;as, el 27 de noviembre de 2009, publicaron un nuevo borrador en el W3C titulado: <a title="Read Geolocation API Specitication" lang="en_EN" hreflang="en_EN" href="http://dev.w3.org/geo/api/spec-source.html" target="_blank">Geolocation API Specification</a>. Esta especificaci&oacute;n define una API que proporciona secuencias de comandos de acceso a la informaci&oacute;n de localizaci&oacute;n geogr&aacute;fica asociada con el dispositivo de alojamiento. &iquest;Verdad que suena interesante?</p>
<!--more-->


<p>El objeto Geolocation lo podemos encontrar en la instancia navigator y debe implementar estos 3 m&eacute;todos:</p>

<ul>
<li><em>void</em><strong> getCurrentPosition</strong> (successCallback, errorCallback, options): Cuando se llama, de inmediato regresa y, a continuaci&oacute;n, de forma asincr&oacute;nica intenta obtener la ubicaci&oacute;n actual del dispositivo.</li>
<li><em>long</em><strong> watchPosition</strong> (successCallback, errorCallback, options): inmediatamente devuelve un valor <em>long</em> que identifica un&iacute;vocamente a una operaci&oacute;n watch y, a continuaci&oacute;n de forma asincr&oacute;nica inicia la operaci&oacute;n de watch. Esta operaci&oacute;n sigue controlando la posici&oacute;n del dispositivo e invocando la funci&oacute;n callback adecuada cada vez que el dispositivo cambia de posici&oacute;n. La operaci&oacute;n contin&uacute;a hasta que se llama al m&eacute;todo clearWatch con el identificador correspondiente.</li>
<li><em>void</em> <strong>clearWatch</strong> (watchId): el proceso identificado por el argumento watchId se interrumpe inmediatamente y dejan de invocarse los callbacks. Este identificador es el que devuelve la funci&oacute;n watchPosition.</li>
</ul>

<p><strong>Nota:</strong> <em>Estas funciones (</em>getCurrentPosition y&nbsp;watchPosition)<em> notificar&aacute;n al usuario de nuestras intenciones y ser&aacute; &eacute;l qui&eacute;n decida si permitir el acceso a esa informaci&oacute;n o no. </em></p>

<p><img title="Firefox geoposicionamiento" src="/app/uploads/sites/7/2009/12/435853-206832.jpg" alt="Firefox geoposicionamiento" /></p>

<p>Estas funciones se encuentran implementadas por un objeto llamdo <strong>Geolocation</strong> que se pertenece a la interfaz NavigatorGeolocation y deber&iacute;a implementarse por el objeto Navigator. As&iacute; que, podemos acceder a la posici&oacute;n actual del visitante mediante:</p>

<pre style="font-size: 3.55556px; line-height: 5.33333px;"><code>navigator.geolocation.getCurrentPosition(successCallback, errorCallback, options)</code></pre>

<p>&iquest;Y qu&eacute; significa: <strong>successCallback</strong>, <strong>errorCallback</strong>, <strong>options</strong> y <strong>watchId</strong>? Pues los dos primeros argumentos son obligatoriamente funciones y el tercero un objeto. En m&aacute;s detalle tenemos:</p>

<h2>successCallback</h2>

<p>Funcion que recibe por par&aacute;metro <em>Position</em> <strong>position</strong> que contiene los atributos <em>Coordinates</em> <strong>coords</strong> y <em>DOMTimeStamp</em> <strong>timestamp</strong>. El atributo coords contiene la siguiente informaci&oacute;n:</p>

<h3 style="font-size: 11.2333px; line-height: 14.4px;">Position.Coordinates</h3>

<ul>
<li><strong>latitude</strong>: coordenadas geograficas&nbsp; especificadas en grados.</li>
<li><strong>longitude</strong>: coordenadas geograficas&nbsp; especificadas en grados.</li>
<li><strong>altitude</strong>: denota la altura especificada en metros.</li>
<li><strong>accuracy</strong>: denota el nivel de precisi&oacute;n de las coordenadas de latitud y longitud, en metros.</li>
<li><strong>altitudeAccuracy</strong>: denota el nivel de precisi&oacute;n de la altitud.</li>
<li><strong>heading</strong>: representa la direcci&oacute;n del desplazamiento, tomado en grados en sentido horario desde el norte verdadero.</li>
<li><strong>speed</strong>: indica la velocidad del dispositivo en metros por segundo.</li>
</ul>

<p>La altitud, la precisi&oacute;n de la altitud, la direcci&oacute;n y la velocidad pueden existir o no dependiendiendo del dispositivo y en caso de no exisitir devolver&aacute;n null</p>

<h2>errorCallback</h2>

<p>Funci&oacute;n que recibe por par&aacute;metro <em>PositionError</em> <strong>error</strong> el cual contiene un <em>short</em> <strong>code</strong> y un <em>DOMString</em> <strong>message</strong>. El code puede tener un valor de 0 a 3 dependiendo de la causa, siendo:</p>

<ul>
<li>UNKNOWN_ERROR = 0</li>
<li>PERMISSION_DENIED = 1</li>
<li>POSITION_UNAVAILABLE = 2</li>
<li>TIMEOUT = 3</li>
</ul>

<h2>options</h2>

<p>Objeto que consta de los siguientes atributos:</p>

<ul>
<li><em>boolean</em> <strong>enableHighAccuracy</strong>: proporciona un indicio de que la aplicaci&oacute;n desea recibir los mejores resultados posibles. El valor por defecto es false.</li>
<li><em>long</em> <strong>timeout</strong>: indica la duraci&oacute;n m&aacute;xima de tiempo (expresado en milisegundos) que se permite para pasar de la llamada a getCurrentPosition() o watchPosition() hasta que se invoca el successCallback correspondiente.</li>
<li><em>long</em> <strong>maximumAge</strong>: indica que la aplicaci&oacute;n est&aacute; dispuesto a aceptar una posici&oacute;n en cach&eacute;, cuya edad no sea mayor que el tiempo especificado en milisegundos.</li>
</ul>

<p>&iquest;Qu&eacute; opinas de que un dispositivo pueda informar de la posici&oacute;n del mismo? &iquest;Se te ocurre alguna aplicaci&oacute;n, o ya le estas dando uso y quieres compartirlo?</p>