---
ID: 2462
post_title: >
  Geoposicionamiento web y la API de
  Google Maps V3
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/geoposicionamiento-web-api-google-maps-v3-444732/
published: true
post_date: 2009-12-29 10:24:00
---
El otro día hablabamos de <a title="Leer Cómo geoposicionar un dispositivo con el navegador" href="http://pixelovers.com/geoposicionar-dispositivo-navegador-435853">Cómo geoposicionar un dispositivo con el navegador</a>, pero por si sola no podemos darle mucha utilidad, puesto que necesitamos ejecutar algo en el successCallback. Y aquí es donde aparece la nueva versión de la <a title="Leer la documentación de la API de Google Maps V3" href="http://code.google.com/apis/maps/documentation/v3/" target="_blank">API de Google Maps V3</a>.

<!--more-->La API Javascript es muy parecida a su antecesora, la versión 2. Sin embargo ha cambiado mucho internamente, ya que ha sido <strong>diseñada para cargar más rápidamente</strong>, especialmente en <strong>navegadores móviles</strong>, como los dispositivos basados en Android y el iPhone™.

Una caracteristica muy destacable de esta nueva versión es que ha sido implementada usando un <strong>marco de trabajo MVC</strong>. También cabe descatacar la <strong>desaparición de API key</strong>, lo cual elimina trámites previos a la hora de implementar tu trabajo en diferentes dominios.

Ponerlo en marcha es realmente fácil. Sólo tienes que seguir estos <strong>5 sencillos pasos</strong>:
<ol>
	<li><strong>Incluir el código JavaScript</strong> de la API de Google Maps usando la etiqueta <em>script</em>
<pre class="lang:xhtml decode:true">&lt;script
   type="text/javascript"
   src="http://maps.google.com/maps/api/js?sensor=set_to_true_or_false"&gt;
&lt;/script&gt;</pre>
</li>
	<li><strong>Crear un elemento</strong> div llamado "map_canvas" para contener el Mapa.
<pre class="lang:xhtml decode:true">&lt;div id="map_canvas" style="width:100%; height:100%"&gt;&lt;/div&gt;</pre>
</li>
	<li><strong>Crear un objeto en JavaScript</strong> para guardar una serie de propiedades del mapa.
<pre class="lang:js decode:true">var myOptions = {
   zoom: 8,
   center: latlng,
   mapTypeId: google.maps.MapTypeId.ROADMAP
};</pre>
</li>
	<li><strong>Escribir una función de JavaScript</strong> para crear el objeto "mapa".
<pre class="lang:js decode:true">function initialize() {
   var latlng = new google.maps.LatLng([latitud], [longitud]);
   var map = new google.maps.Map(
      document.getElementById("map_canvas"),
      myOptions
   );
}</pre>
</li>
	<li><strong>Inicializar el objeto mapa</strong> en la función <em>onload</em> del <em>body</em>.
<pre class="lang:xhtml decode:true">&lt;body onload="initialize()"&gt;</pre>
</li>
</ol>
¿Qué te parece la nueva versión de la API de Google Maps? ¿Ya la has probado? Cuentanos qué te ha parecido.