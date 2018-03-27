---
ID: 2436
post_title: >
  CDN (Content Delivery Network) gratis
  con Google App Engine
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/cdn-content-delivery-network-gratis-google-app-engine-118134/
published: true
post_date: 2008-08-12 09:04:05
---
<img title="Google App Engine" src="/app/uploads/sites/7/2008/08/118134-85768.jpg" alt="Google App Engine" width="200" height="200" align="right" />Ayer me comentaba un compañero de trabajo que estaba buscando un hosting donde alojar la web de su grupo: muchas imágenes, sonido, vídeo... mucho archivo estático. El problema que se encontraba muchas veces es que los planes que se adecuaban a su proyecto, en CPU, memoria y espacio en disco, se quedaban cortos en transferencia mensual y velocidad de la conexión, y viceversa: los que encajaban en cuanto a transferencia se excedían en todo lo demás (también en el precio). A raíz de esto, me acordé de un artículo que leí hace poco en <strong>Maestros del Web</strong>: <a href="http://www.maestrosdelweb.com/editorial/diez-pasos-faciles-para-usar-google-app-engine-como-tu-propia-red-de-distribucion-de-contenido/">10 pasos fáciles para usar Google App Engine como tu propia red de distribución de contenido</a>.

<!--more-->Una red de distribución de contenido (CDN) es lo que suelen usar las webs grandes para agilizar la distribución de archivos estáticos (imágenes, hojas de estilo, javascripts, multimedia...). Las CDNs permiten tener nuestros contenidos replicados en múltiples servidores por todo el mundo, acelerando la descarga de los mismos de cara a los clientes, puesto que éstos siempre se sirven desde la ubicación más cercana al usuario. Suelen ser sistemas demasiado caros para que pequeños proyectos o particulares se planteen siquiera su uso.

<img title="Content Distribution Network" src="/app/uploads/sites/7/2008/08/118134-85769.jpg" alt="Content Distribution Network" width="200" height="143" align="left" />Lo que propone Andreas Kohn en el artículo es utilizar la Google App Engine para montar nuestro propio CDN gratis, o a bajo coste (cobran a partir de 500MB de alojamiento o por encima de los 5 millones de PV. A pesar de esto, <a href="http://googleappengine.blogspot.com/2008/05/announcing-open-signups-expected.html">los precios son muy muy bajos</a>).

No lo he probado, pero parece muy sencillo de desarrollar. Disponer de la infraestructura de servidores de Google a nuestra disposición bien merece el esfuerzo, no? Está por ver, sin embargo, si el rendimiento vale la pena. En experiencias similares que otros han tenido tratando de utilizar Amazon S3 (el equivalente de Amazon en cuanto a alojamiento) con los mismos fines, los resultados no fueron muy buenos.