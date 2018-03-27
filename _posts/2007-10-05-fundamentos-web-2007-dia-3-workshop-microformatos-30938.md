---
ID: 2402
post_title: 'Fundamentos web 2007: día 3 &#8211; Workshop sobre microformatos'
author: Albert Garcia
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/fundamentos-web-2007-dia-3-workshop-microformatos-30938/
published: true
post_date: 2007-10-05 10:37:00
---
<p style="text-align: left;" align="center"> Aquí vamos de nuevo, arrancando el tercer y último día de las jornadas, dedicado a un <em>workshop full day</em> que va a ser dirigido por <a href="http://tantek.com/"><strong>Tantek Çelik</strong></a>, sobre <a href="http://microformats.org/">Microformatos</a>.</p>
<p style="text-align: left;" align="center"><!--more--></p>
<strong>10:36</strong> - Tantek ha empezado haciendo una pequeña introducción hablando de los orígenes de la web semántica. Está hablando del concepto <a href="http://microformats.org/wiki/posh"><acronym title="Plain Old Semantic HTML">POSH</acronym></a>. Comenta que espera que la jornada sea lo más interactiva posible, invitando a participar a todos aquellos que quieran comentar cualquier cosa durante sus explicaciones.

Describe algunos de los microformatos más elementales, empezando por <em>rel</em>. El atributo <em>rel</em> puede usarse para implementar, por ejemplo, los microformatos <a href="http://microformats.org/wiki/rel-license">rel-license</a> ( para indicar la licencia aplicable a determinado contenido ), <a href="http://www.gmpg.org/xfn/"><acronym title="XHTML Friends Network">XFN</acronym></a> ( para indicar la relación existente entre dos personas ), <a href="http://microformats.org/wiki/rel-tag">rel-tag</a> ( para indicar que determinado enlace responde a una categorización _etiqueta_ ), <a href="http://microformats.org/wiki/vote-links">vote-links</a> ( para indicar que un enlace se usa para votar / valorar determinado contenido ).

<strong>11:16</strong> - He subido algunas fotos más al <a href="http://www.flickr.com/gp/91558571@N00/YMY58X">álbum de Flickr</a>. Mientrs tanto Tantek ha hablado de la importancia de tener en cuenta la accesibilidad cuando trabajemos con microformatos. Ha comentado también acerca de las etiquetas abbr y acronym, cuyo uso correcto estaba convencido que conocía y... no!

Hasta ahora utilizaba la etiqueta acronym para marcar cualquier conjunto de iniciales que sirva para identificar un concepto ( FBI, HTML, KISS, POSH, LAMP... ), cuando en realidad sólo debe usarse para aquellos que funcionan y se leen como una palabra. Haciendo caso a los ejemplos anteriores, sólo lo serían KISS, POSH o LAMP. Por mi parte sólo usaba ABBR para abreviaciones de palabras del tipo etc., telf., dña., d., e.g., ... Haciendo caso a <a href="http://www.w3.org/TR/html401/struct/text.html#h-9.2.1">la especificación</a>, FBI, HTML, WWW... deberían marcarse con la etiqueta ABBR. Nunca te acostarás sin saber una cosa más.

<strong>11:30</strong> - Está hablando sobre el microformato <a href="http://microformats.org/wiki/hcard">hCard</a>, utilizado para marcar perfiles de usuario ( nombre, nickname, email, dirección... ) El microformato hCard basa su estructura en el formato vCard, usado en la mayoría de software y dispositivos que trabajan con información de contactos ( agendas PDA, teléfonos, aplicaciones tipo Outlook... )

<strong>12:42</strong> - <img class="fotobonita" title="Operator" src="/app/uploads/sites/7/2007/10/30938-29236.jpg" alt="Operator" width="200" height="111" align="right" />Tras el descanso para el café, empieza retomando el tema del hCard, y recomienda a aquellos que hayan traído portátil instalar la extensión <a href="https://addons.mozilla.org/en-US/firefox/addon/4106"><strong>Operator</strong></a> para Firefox. Operator permite interactuar con aquellos elementos de una página que hagan uso de microformatos. Funciona como una barra de herramientas adicional que nos da acceso a aquellos contactos, eventos, direcciones, tags... que haya marcados en la página, ofreciendo opciones para exportar la información que contienen. Por ejemplo en el caso de contactos marcados con hCard, nos permite exportarlos a nuestro gestor de contactos ( Outlook, libreta de direcciones, la Agenda en Mac... ).
<p align="center"><img class="fotobonita" title="Operator" src="/app/uploads/sites/7/2007/10/30938-29237.jpg" alt="Operator" width="475" height="226" /></p>
<strong>12:56</strong> - Han repartido algunos ejercicios entre los asistentes. Se propone una práctica para marcar un perfil sencillo con nuestro nombre y nuestra web. En realidad no tiene más misterio que conocer qué nombres de clase usar y para qué. Revisad <a href="http://microformats.org/wiki/hcard">la especificación</a> y haced vosotros mismos algunas pruebas usando Operator para comprobar que lo hacéis correctamente. Como curiosidad podéis ver <a href="http://microformats.org/wiki/hcard#Implied_.22n.22_Optimization">algunos atajos permitidos para simplificar el marcado de nombres</a>.

<strong>13:41</strong> - Seguimos viendo ejemplos y realizando algunos ejercicios prácticos. Quizás lo más interesante es que está apuntando a algunas excepciones útiles para identificar o marcar casos concretos, combinando algunos de los atributos de determinada forma. Prometo una recopilación a posteriori... Ahora prefiero atender. <img title="Wink" src="http://www.obolog.com/js/tiny_mce/plugins/emotions/images/smiley-wink.gif" alt="Wink" border="0" />

<strong>14:09</strong> - Media hora más tarde de lo previsto... a comer!

--------

<strong>16:49</strong> - Finally! Termina con hCard y pasa a comentar hCalendar. Pone como ejemplo a <a href="http://upcoming.yahoo.com/"><strong>Upcoming</strong></a> ( algo así como <a href="http://www.eventtos.com"><strong>Eventtos</strong></a>, pero en inglés y con algunas funcionalidades orientadas a red social ). Recuerda que se pueden usar cualquiera de <a href="http://microformats.org/code/?page_id=20">los generadores de microformatos</a> disponibles en la propia página de microformats.org.

Resulta interesante la idea de combinar y / o anidar diferentes microformatos para conseguir estructuras complejas. Pone como ejemplo un evento marcado con hCalendar cuyo location se marca usando hCard, indicando que se trata de un negocio.

<strong>17:59</strong> - C'est fini. Hemos hecho un repaso de un par de microformatos algo más complejos, como son hReview y hResume, que combinan estructuras de microformatos más elementales. Como se veía venir... nada de XFN. Le atacaré ahora si se deja, o via mail. <img title="Wink" src="http://www.obolog.com/js/tiny_mce/plugins/emotions/images/smiley-wink.gif" alt="Wink" border="0" />

Ala, un placer compartirlo con ustedes. Ahora, a recoger y pillar el taxi para el aeropuerto, que esta noche llego tarde y empalmo con la despedida de soltero de Raúl. Let's rock.