---
ID: 2452
post_title: Namespace en eventos de jQuery
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/namespace-eventos-jquery-313039/
published: true
post_date: 2009-12-10 09:00:00
---
Namespace o espacio de nombre (españolización que no se usa) es la <strong>contextualización de una variable o método</strong>, es decir, consiste en asociar un identificador a un grupo de variables y/o métodos.

<!--more-->

Ahora que sabemos que significa, vamos a ver como se aplica esto a los eventos en jQuery y luego veremos una aplicación práctica de los namespaced events. Todos sabemos como añadir un manejador de evento (click, por ejemplo) a un elemento mediante el método <a lang="en_EN" title="Evento bind de jQuery" href="http://docs.jquery.com/Events/bind" hreflang="en_EN">bind</a>:
<pre class="lang:js decode:true">$("a").bind("click", function() { /* Code... */ });</pre>
Ahora si queremos contextualizar ese evento click, que pertenezca a un grupo utilizamos el siguiente código:
<pre class="lang:js decode:true">$("a").bind("click.namespace", function() { /* Code... */ });</pre>
Esto funcionará, igual que el anterior ejemplo, en cada click que se haga a los elementos a, pero además podremos llamar únicamente a esta función mediante el metodo `<a lang="en_EN" title="Evento trigger de jQuery" href="http://docs.jquery.com/Events/trigger" hreflang="en_EN">trigger</a>` o desligar un grupo de funciones asociadas a un evento,
<pre class="lang:js decode:true">$("a").trigger("click.namespace");</pre>
Con esto hemos lanzamos el evento click con el espacio de nombre "namespace" de los elementos `a`.
<pre class="lang:js decode:true">$("a").unbind(".namespace");</pre>
Y con esto hemos desligado todos los tipos de eventos del espacio de nombre namespace, ya sean eventos `click`,  `dbclick`,  `mousedown`,  `mouseup`,  etc..

¿Se te ocurre como podrías utlizar los espacios de nombre en los eventos? Aquí te dejo un <strong>ejemplo simple de namespaced events</strong>. Consiste en un formulario que añade los valores que introduces en el campo "name" en una lista. La particularidad es que he dividido la tarea en 2 funciones, una para crear la lista y otra para añadir elementos, la primera de ellas la bindeo antes que la segunda y la desvindeo al acabarse ella misma. De esta manera consigo que la primera vez se llame a ambas funciones y las sucesivas solamente a la segunda.

HTML:
<pre class="lang:xhtml decode:true">&lt;form action="" method="post" id="addName"&gt;
  &lt;p&gt;
    &lt;label for="Name"&gt;Nombre:&lt;/label&gt;
    &lt;input type="text" name="name" value="" id="name"/&gt;
  &lt;/p&gt;
  &lt;p&gt;&lt;input type="submit" value="Añadir nombre"/&gt;&lt;/p&gt;
&lt;/form&gt;</pre>
Javascript:
<pre class="lang:js decode:true">//Bind Event for the first time
$('#addName').bind('submit.first', function(){
    $(this).after('&lt;p&gt;Lista de nombres:&lt;/p&gt;&lt;ul id="listNames"&gt;&lt;/ul&gt;').unbind('submit.first');
 });</pre>
<pre class="lang:js decode:true">//Bind Event for ever
$('#addName').bind("submit", function(){
if('' == this.name.value) return false;
$('#listNames').append('&lt;li&gt;' + this.name.value + '&lt;/li&gt;');
return false;
});</pre>
Ese es un ejemplo para ver el funcionamiento del namespacing, pero en este caso, ya que eliminamos el evento en la primera ejecución sería más útil utilizar el atajo <strong>one</strong>, quedando el primer evento de la siguiente manera:
<pre class="lang:js decode:true">//Bind Event for the first time
$('#addName').one(function(){
    $(this).after('&lt;p&gt;Lista de nombres:&lt;/p&gt;&lt;ul id="listNames"&gt;&lt;/ul&gt;');
 });</pre>
¿Qué te aparecido? ¿Te resulta útil?

Cuéntanos dónde y cómo lo has aplicado para que aprendamos todos trucos nuevos de jQuery.