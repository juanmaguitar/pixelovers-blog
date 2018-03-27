---
ID: 3658
post_title: >
  Acelera tu WordPress con tecnologías de
  servidor del 2016
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/tecnologias-2016-optimizar-la-velocidad-sitio-wordpress/
published: true
post_date: 2016-04-25 11:28:25
---
<a href="http://pixelovers.com/app/uploads/sites/7/2016/04/show-off-your-fiercestyling-skills-this-may-28at-talent-week.png"><img class="alignnone size-full wp-image-3680" src="http://pixelovers.com/app/uploads/sites/7/2016/04/show-off-your-fiercestyling-skills-this-may-28at-talent-week.png" alt="show off your fiercestyling skills this may 28at talent week!" width="800" height="800" /></a>

<blockquote>PHP7? NGINX? HHVM? CDN? He mirado el post por encima y no me entero de ná. Este articulo es muy pro para mi.</blockquote>

Que noooo.... sigue leyendo :)

Si no eres técnico este articulo te interesa igual ya que te servirá para conocer y entender aquellas tecnologías que debería tener tu hosting para que tu wordpress vaya lo mejor posible.

<hr />

Tener un blog (o un sitio web) con wordpress es bastante sencillo. Hay muchas maneras de empezar a publicar tus posts y tenerlos online rápidamente. Hace poco en pixelovers os contábamos, por ejemplo, <a href="http://pixelovers.com/montar-blog-wordpress-facilmente/">cómo tener tu blog wordpress online en menos de 5 minutos.</a>

Pero una vez que el blog está en marcha y vemos que nuestras visitas crecen, es el momento de empezar a mejorarlo...<!--more-->

<h2><a id="user-content-por-qué-es-importante-mejorar-la-velocidad-de-carga-de-mi-blog" class="anchor" href="#por-qu%C3%A9-es-importante-mejorar-la-velocidad-de-carga-de-mi-blog"></a>¿Por qué es importante mejorar la velocidad de carga de mi blog?</h2>

Al hablar de "mejorar" nuestro blog, solemos entender con tener: más visitas, más lectores, más audiencia en social media, mejor posicionamiento en google, mejor diseño, mejor experiencia de usuario, mayor velocidad de carga, etc...

De todas estas, <strong>la mejora que más importancia tiene para tu site, sin duda es: la velocidad de carga</strong>.

A mayor velocidad de carga mejor experiencia de usuario, pero además la velocidad de carga es uno de los factores que Google tiene en cuenta a la hora de posicionar nuestro site por lo que tambien: a mayor velocidad de carga, mejor posicionamiento SEO

Algunos bloggers se centran en crear contenido que sea atractivo desde el punto de vista SEO para mejorar la visibilidad en Google pero se olvidan de las mejoras técnicas que pueden hacer en su blog para que vaya más rápido. A veces el poner en marcha determinadas tecnologías/técnicas en el servidor para acelerar la carga de nuestro site (tan simple a veces como cambiar al hosting adecuado que haga todo esto por ti) puede tener un impacto mucho mayor a la hora de que Google posicione mejor nuestro blog (en general, cuanto mas rápido cargue tu blog más le gustarás a Google)

Resumiendo. Mejorar la velocidad de nuestro site wordpress tiene mútiples beneficios:

<ul>
    <li>Mejor experiencia del usuario</li>
    <li>Mejor ranking SEO</li>
</ul>

O sea, que tendrás a todo el mundo contento :)

<h2><a id="user-content-qué-cosas-puedo-hacer-para-mejorar-la-velocidad-de-mi-blog" class="anchor" href="#qu%C3%A9-cosas-puedo-hacer-para-mejorar-la-velocidad-de-mi-blog"></a>¿Qué cosas puedo hacer para mejorar la velocidad de mi blog?</h2>

Para mejorar esta velocidad de carga podemos atacar muchos frentes que podríamos juntar en dos grandes grupos:

<ul>
    <li><strong>Mejoras en nuestro servidor (hosting) </strong>utilizando aquellas tecnologías y técnicas que sirvan y procesen más rápido nuestro contenido.</li>
    <li><strong>Mejoras</strong> <strong>en nuestro wordpress y contenido</strong> (compresión, optimización, simplificación) para que se sirva más rápido. <em>La mayoría de estas mejoras las podemos hacer a base de plugins.</em></li>
</ul>

Para la mayoría de usuarios de wordpress, mejorar esta velocidad desde el servidor es tan sencillo cómo mudarse a un proveedor de hosting que ofrezcan todo esto.

Los sitio gratuitos están bien para empezar, pero si quieres algo medio bueno las únicas opciones que merecen la pena son de pago

El <a href="http://siteground.es">hosting de SiteGround</a> es una opción muy buena donde tienes todas estas tecnologías disponibles y muchas más.

<h2><a id="user-content-tecnologias-en-mi-servidor-hosting-para-acelerar-mi-site" class="anchor" href="#tecnologias-en-mi-servidor-hosting-para-acelerar-mi-site"></a>Qué tecnologías puedo utilizar desde mi servidor de hosting para acelerar mi sitio wordpress</h2>

<h3><a href="http://php.net/">PHP7</a></h3>

<em>Acelera el procesado del código PHP</em>

Cómo todos sabeis wordpress utiliza el lenguage de servidor PHP. Pues bien, cada lenguaje de programación suele ir evolucionando y van saliendo diferentes versiones. La última de PHP es la 7 (<a href="http://php.net/archive/2015.php#id2015-12-03-1">se lanzó el diciembre pasado</a>), y <strong>es la versión que actualmente más rápido procesa el código PHP que hay detrás de Wordpress.</strong>

<a href="http://pixelovers.com/app/uploads/sites/7/2016/04/wp-php7-performance.jpg"><img class="alignnone size-full wp-image-3666" src="http://pixelovers.com/app/uploads/sites/7/2016/04/wp-php7-performance.jpg" alt="wp-php7-performance" width="700" height="391" /></a>

Esta versión es bastante estable y <a href="http://www.itsmdaily.com/php-7-and-wordpress-plugin-compatibility/">parece que ser que va bastante bien con los plugins más utilizados</a> de todas maneras esta nueva versión trae muchos cambios, así que es posible que aparezcan algunos errores al hacer el cambio. Si estas actualizado a la última versión de Wordpress y tienes tus plugins actualizados, los errores deberían ser mínimos.

Las versiones anteriores son desde la PHP 5.x para abajo (no, no hay PHP 6.x)

<h3><a href="http://hhvm.com/">HHVM</a></h3>

<em>Acelera el procesado del código PHP</em>

Hasta hace poco la alternativa más potente para acelerar el procesado del código PHP en el servidor era utilizar una version especial de PHP llamada HHVM. <a href="https://www.facebook.com/notes/facebook-engineering/speeding-up-php-based-development-with-hhvm/10151170460698920/">Desde Facebook</a> se creó esta <a href="http://www.hubnest.com/blog-18-what-is-hhvm-and-why-you-should-start-using-it">versión hackeada de PHP</a> para sobre todo acelerar su ejecución.

Si tu servidor no tiene PHP7 disponible aún, o no quieres utilizarlo aun por que te da muchos problemas con tu site, utilizar HHVM es una buena alternativa para mejorar la eficiencia del PHP de tu site wordpress.

<h3><a href="https://www.nginx.com/">NGINX</a></h3>

<em>Sirve el contenido de tu web (estático y dinámico) más rápido</em>

En términos generales, nginx es más rápido y eficiente que el otro servidor web popular: <a href="https://httpd.apache.org/">Apache</a>

Siendo estrictos, las últimas versiones de ambos servidores web son <a href="http://www.hostingadvice.com/how-to/nginx-vs-apache/#performance">igual de rápidas</a> a la hora de servir contenido dinámico pero nginx es más rápido para servir archivos estáticos (imágenes, JS, CSS...)

Si no tienes implementado ningún <a href="http://ayudawp.com/cdn-wordpress/">CDN para tu sitio wordpress</a> optar por NGINX es la mejor opción. Si utilizar un CDN que sirva tus archivos estáticos (imágenes, JS, CSS...) por otro lado, <a href="http://www.speedemy.com/apache-vs-nginx-2015/">tanto apache (debidamente configurado) como nginx</a> te van ir igual de rápido

Si te decides por nginx, <a href="https://www.nginx.com/blog/9-tips-for-improving-wordpress-performance-with-nginx/">aqui tienes algunos "tuneos"</a> más que puedes hacer en tu site para que vaya aun más rapido

<h3><a href="https://http2.github.io/">HTTP2</a></h3>

<em>Protocolo mejorado para el envío de archivos desde el servidor </em>

Si está activado el protocolo <a href="http://es.engadget.com/2015/03/06/que-es-http2-como-funciona/">HTTP2</a> (la última version del protocolo HTTP) en tu servidor, los usuarios de tu site que utilicen versiones modernas de navegadores automáticamente utilizarán este protocolo (que es más rápido) para acceder a los contenidos de ti sitio.

<h3><a href="https://es.wikipedia.org/wiki/Red_de_entrega_de_contenidos">CDN</a></h3>

<em>Utiliza una infraestructura de servidores por todo el mundo para servir más rápido tus archivos</em>

En los sitios wordpress hay dos tipos de contenido (archivos) claros: contenido dinámico y contenido estático.

El <em>contenido dinámico</em> es el que se procesa en los archivos PHP y que cambia segun los contenidos de la Base de Datos. Ese contenido ya hemos hablado de como servirlo más rápido  utilizando PHP7, HHVM o NGINX.

Pero hay otro tipo de contenido llamado <em>contenido estático</em> (imágenes, css, js...) que no necesita ningún tratamiento en el servidor porque realmente se procesa en el navegador. Como no requiere de ningún proceso en el servidor, podemos servirlo desde cualquier otro servidor distinto y nuestro site va a funcionar igual.

Con esta idea funcionan los CDN. Un CDN es un grupo de servidores repartidos por todo el mundo que nos permite servir el contenido estático desde el servidor que esté mas cerca del usuario y por tanto más rapido.

<a href="http://pixelovers.com/app/uploads/sites/7/2016/04/NCDN_-_CDN.png"><img class="alignnone size-full wp-image-3678" src="http://pixelovers.com/app/uploads/sites/7/2016/04/NCDN_-_CDN.png" alt="NCDN_-_CDN" width="1324" height="568" /></a>

Asi que si montamos nuestro Wordpress para que sirva nuestro contenido estático desde un CDN vamos a notar un cambio brutal en la velocidad con la que se carga nuestro site.

Si quieres empezar por algo para acelerar tu site, empieza utilizando un CDN para tu contenido estático.

<h2>Conclusión</h2>

En este post hemos visto lo importante que es mejorar la velocidad de carga de nuestro site y las tecnologías que podemos utilizar desde el servidor para mejorar esto.

¿Qué te ha parecido este post? ¿Conocías estas tecnologías?

Esperamos vuestros comentarios