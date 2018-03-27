---
ID: 2379
post_title: >
  Cómo evitar problemas con la cache del
  navegador
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/evitar-problemas-cache-navegador-10139/
published: true
post_date: 2007-04-18 23:59:30
---
<p>En esta ocasión veremos como evitar un problema con el que seguro os habréis topado en más de una ocasión: <strong>El navegador no detecta un cambio que hemos realizado en un archivos estático ( CSS / Javascript / imagen ) y usa la copia cacheada en disco</strong>, impidiendo que la web muestre los estilos correctos, actualizados, o lanzando un error Javascript por el uso de una función no existente, hasta que forzamos una actualización con Ctrl-F5.</p>

<!--more-->

<p>La caché de los navegadores actúa en el 90% de las ocasiones como nuestro aliado. Permite que determinados archivos estáticos se carguen una única vez por usuario, y se lean desde el disco en sucesivas visitas, reduciendo drásticamente los tiempos de carga.</p>

<p>De todas formas, el caché también puede jugar en nuestra contra en determinadas ocasiones: Si hemos realizado modificaciones a un archivo estático <strong>en un intervalo corto de tiempo</strong>, y además estas modificaciones <strong>han hecho variar muy poco el tamaño</strong> de nuestro archivo, es muy probable que el navegador no detecte que existe una nueva versión, y <strong>en vez de descargar el fichero más actual, haga uso de la copia que guarda en el disco</strong> para montar la página.</p>

<p>Como apuntábamos al principio, <strong>las consecuencias de esto suelen ser desastrosas</strong>: webs descuadradas o errores javascript por culpa de funciones que "deberían estar", pero que el navegador no ha cargado. Y, claro , el Ctrl-F5 sirve para mostrar la página al compañero de mesa o para tranquilizar al jefe que ha pegado un bote en la silla al ver el resultado, pero el usuario no tiene ni idea... va a verlo todo descuadrado hasta que expire la caché o le dé por forzar la recarga ( cosa poco probable ).</p>

<p><strong>La solución a este problema es sencillamente añadir un parámetro a la llamada que hagamos al archivo estático</strong>. Los hay que optan por usar una fecha, y otros simplemente un valor numérico. Yo soy de estos últimos: como suelo usar <a href="http://subversion.tigris.org/"><strong>Subversion</strong></a> para el control de versiones, lo que hago es actualizar el valor con el nº de versión correspondiente. De esta forma puedo saber, además, cuándo se hizo la última modificacion "sensible" a la hoja de estilos, echando un vistazo al <em>showlog</em>.</p>

<pre class="lang:xhtml decode:true">
 
    <link rel="stylesheet" type="text/css" href="/css/estilos.css?id=393" />

</pre>

<p>Cada vez que cambiamos el parámetro que hemos añadido a la llamada al CSS ( o Javascript, o imagen... ), lo que estamos haciendo es forzar al navegador a descargar de nuevo el archivo, retomando de esta forma el control sobre cuándo cachear y cuándo no.</p>