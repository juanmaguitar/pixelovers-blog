---
ID: 2404
post_title: >
  CSS Sprites. Mejora el rendimiento de tu
  web (I)
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/css-sprites-mejora-rendimiento-web-i-37249/
published: true
post_date: 2007-11-06 09:04:03
---
Con este artículo empezaremos una serie de posts que tratarán de diversas técnicas y consejos que podemos seguir para mejorar el rendimiento y los tiempos de carga de nuestra página web. Y es que <strong>el rendimiento de una aplicación web no sólo depende de la programación del lado del servidor, si no también del marcado, el uso que hagamos de hojas de estilo, de imágenes, de nuestra programación javascript</strong>... Todos ellos campos que afectan directamente al desarrollador web en su faceta de maquetador/diseñador.

<!--more-->

Hoy empezaremos desarrollando una técnica CSS muy sencilla y efectiva: Los <strong>CSS Sprites</strong>.
<h2>La problemática.</h2>
Una de nuestras máximas prioridades a la hora de optimizar nuestra aplicación web debe ser reducir las peticiones que ésta hará al servidor una vez el HTML se haya cargado en el navegador del cliente. Cada archivo de hoja de estilos, cada archivo Javascript, cada imagen... <strong>cada elemento externo en definitiva, se solicita de forma separada y aumenta por tanto la transferencia y el tiempo de carga</strong>, esto resulta obvio. Lo que no resulta tan evidente es que <strong>ese aumento no es proporcional a la suma del tamaño de los archivos externos</strong>, es decir, la carga de 10 elementos de 5 KB no es igual de rápida que la de un elemento de 50 KB.

Además de sumar los tiempos de transferencia para cada archivo, deberemos sumar por un lado el tiempo que tarda en realizarse la propia conexión+petición+respuesta y el tamaño correspondiente a las cabeceras del archivo. Recordemos, en relación a las cabecera, que éstas se adjuntan a cada petición al servidor y que si, además, nuestra aplicación usa cookies, éstas también se adjuntarán a cabeceras para cada archivo. <strong>Podría darse el caso, por ejemplo en un archivo de imagen pequeño, en qué el tamaño de las cabeceras + cookies ¡superara al tamaño del propio archivo</strong>!
<h2>La solución.</h2>
Este sería un claro ejemplo de una técnica antigua retomada para solucionar un problema moderno. Y es que para encontrar el origen de los CSS Sprites debemos mirar atrás hacia los antiguos juegos en 2D ( o los actuales juegos para móviles ), que usaban los "sprites" para las animaciones de sus personajes u otros elementos del juego.
<p align="center"><img class="fotobonita" title="37249-34955.jpg" src="/app/uploads/sites/7/2007/11/37249-34955.jpg" alt="37249-34955.jpg" width="475" height="71" /></p>
Como ves, los sprites no eran más que imágenes que contenían a su vez varias imágenes pequeñas, que en el caso de los videojuegos se utilizaban para recrear una animación. En nuestro caso, la solución a las múltiples peticiones para imágenes en nuestras hojas de estilo pasará por el uso de imágenes grandes que contengan a su vez varias imágenes más pequeñas. De esta forma, para mostrar diversos fondos o varios iconos, estaremos realizando una única petición al servidor, con el correspondiente ahorro en tiempo de carga y transferencia.
<h2>Implementación.</h2>
<strong>
El "truco" en esta técnica está en el uso correcto del posicionamiento de backgrounds para mostrar sólo aquella parte de la imagen que nos interesa</strong>. Pongamos como ejemplo un menú, en el que queremos mostrar un icono diferente por cada opción.

Nuestro HTML podría ser algo parecido a:

<code>
&lt;ul&gt;
&lt;li class="option1"&gt;Opción 1&lt;/li&gt;
&lt;li class="option2"&gt;Opción 2&lt;/li&gt;
&lt;li class="option3"&gt;Opción 3&lt;/li&gt;
&lt;/ul&gt;
</code>

y para el CSS usaríamos

<code>
.option1, .option2, .option3 { padding-left:20px; }
.option1 { background:url(iconos.png) 0 0 no-repeat;
.option2 { background:url(iconos.png) 0 -30px no-repeat;
.option3 { background:url(iconos.png) 0 -60px no-repeat;</code>

Como verás, hemos jugado con el posicionamiento vertical de la imagen para mostrar sólo aquella parte de la misma que nos interesa, la que contiene el icono en cuestión:
<p align="center"><img class="fotobonita" title="37249-34957.jpg" src="/app/uploads/sites/7/2007/11/37249-34957.jpg" alt="37249-34957.jpg" width="29" height="111" align="middle" />               <img class="fotobonita" title="37249-34969.jpg" src="/app/uploads/sites/7/2007/11/37249-34969.jpg" alt="37249-34969.jpg" width="126" height="129" align="middle" /></p>
A partir de aquí podemos aplicar esta técnica de trabajo a muchos otros casos, ya no sólo iconos, sino fondos de imagen, pestañas, u otros elementos gráficos de interfaz.

Es fácil hacerse una idea del ahorro conexiones que podemos conseguir: una página con 20 iconos y 3 fondos de imagen diferentes para distintos contenedores pasaría de 23 peticiones de imágenes desde las CSS a sólo 2: una imagen conteniendo todos los iconos y otra conteniendo los fondos.
<h2>Más información.</h2>
<ul>
	<li>Ejemplo práctico: <a href="http://www.yahoo.com">La home de <strong>Yahoo</strong></a></li>
	<li><a href="http://www.alistapart.com/articles/sprites"><strong>CSS Sprites</strong> en <strong>A List Apart</strong></a></li>
</ul>