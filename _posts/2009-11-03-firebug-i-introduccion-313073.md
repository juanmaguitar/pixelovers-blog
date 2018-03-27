---
ID: 2453
post_title: 'Firebug I: Introducción'
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/firebug-i-introduccion-313073/
published: true
post_date: 2009-11-03 09:00:00
---
<img style="float: right;" title="Icono de Firebug" src="/app/uploads/sites/7/2009/11/313073-190897.jpg" alt="Icono de Firebug" width="152" height="154" /><strong>Firebug</strong> es un complemento que no puede faltar en tu Firefox. ¿Qué no usas Firebug? ¿Cómo maquetas o desarrollas en front sin este plugin? Antes de contestar, descargate <a title="Descargar Firefox" href="http://getfirefox.com" target="_blank">Firefox</a> (si es que no lo tienes ya) y el <a title="Complemento Firebug para Firefox" href="http://getfirebug.com" target="_blank">complemento Firebug para Firefox</a>. También te recomiendo una serie de complementos que añaden más potencia, aún si cabe, a Firebug:

<!--more-->
<ul>
	<li><a title="Complemento Yslow para Firefox" href="https://addons.mozilla.org/es-ES/firefox/addon/5369" target="_blank">Yslow</a>: <strong>Analiza las páginas web</strong> y por qué van lentas basándose en las reglas de Yahoo! para los sitios web de alto rendimiento.</li>
	<li><a title="Complemento Firequery para Firefox" href="https://addons.mozilla.org/es-ES/firefox/addon/12632" target="_blank">FireQuery</a>: Es una colección de mejoras de Firebug cunado se usa <strong>jQuery</strong>.</li>
	<li><a title="Complemento Firecookie para Firefox" href="https://addons.mozilla.org/es-ES/firefox/addon/6683" target="_blank">Firecookie</a>: Es una extensión para Firebug que permite <strong>ver y gestionar las cookies</strong> de tu navegador</li>
	<li><a title="Complemento FireRainbow para Firefox" href="https://addons.mozilla.org/en-US/firefox/addon/9603" target="_blank">FireRainbow</a>: <strong>Sintaxis de Javascript resaltada</strong> para Firebug 1.3 + (Si usas Firebug 1.2: <a title="Complemento Rainbow for Firebug para Firefox" href="https://addons.mozilla.org/es-ES/firefox/addon/7575" target="_blank">Rainbow for Firebug</a>)</li>
</ul>
Firebug puedes <strong>editar, depurar y monitorear CSS, HTML y JavaScript en vivo</strong> en cualquier página web. Por ello es un plugin imprescindible para maquetadores y desarrolladores de front. Vamos a ver sus caracteristicas y más adelante haremos un análisis específico para maquetadores (HTML+CSS) y para desarrolladores de front (Javascript+jQuery).
<ul>
	<li><strong>Inspeccionar y editar HTML:</strong> Firebug facilita <strong>encontrar elementos HTML</strong> enterrados en la profundidad de la página. Una vez hayas encontrado lo que busca, Firebug te ofrece una gran cantidad de información, y te permite <strong>editar el código HTML en vivo</strong>.</li>
	<li><strong>CSS maquetación al pixel</strong>: La pestaña de CSS de Firebug te dice todo lo que necesitas saber acerca de los <strong>estilos de la  página</strong> web, y si no te gusta como está, puedes <strong>hacer cambios</strong> y verlos en el momento.</li>
	<li><strong>Ver CSS métrica</strong>: Cuando tus cajas en CSS no están alineadas correctamente puede ser difícil entender por qué. <strong>Deja a Firebug ser tus ojos</strong> y te medirá y te ilustrará todas los offset, los margins, los borders, los paddings y los tamaños.</li>
	<li><strong>Supervisar la actividad de la red</strong>: Tus páginas tardan en cargar, pero ¿por qué? ¿Te vuelves loco y escribes mucho código JavaScript? ¿Ha olvidado comprimir las imágenes? ¿Son tus servidores de anuncios los que se están echando una siesta? <strong>Firebug fracciona todo archivo por archivo</strong>.</li>
	<li><strong>Depuración y perfilador de JavaScript</strong>: Firebug incluye un <strong>potente depurador de JavaScript</strong> que te permite detener la ejecución en cualquier momento y ver el estado del mundo. Si el código es un poco lento, utiliza el perfilador de JavaScript para medir el rendimiento y encontrar rápidamente los cuellos de botella.</li>
	<li><strong>Encontrar rápidamente los errores</strong>: Cuando las cosas van mal, Firebug te permite conocer de inmediato y te proporciona <strong>información útil y detallada acerca de los errores</strong> en JavaScript, CSS y XML.</li>
	<li><strong>Explorar el DOM</strong>: El Modelo de Objetos del Documento es una enorme jerarquía de objetos y funciones que está a la epera de ser acariciada por JavaScript. Firebug te ayuda a <strong>encontrar objetos DOM</strong> rápidamente y luego editarlos sobre la marcha.</li>
	<li><strong>Ejecutar código JavaScript sobre la marcha</strong>: La línea de comandos es una de las herramientas más antiguas de la caja de herramientas de la programación. Firebug te da una buena <strong> línea de comandos para JavaScript</strong> con modernas comodidades.</li>
	<li><strong>Registo para JavaScript</strong>: Tener un fantástico depurador JavaScript es genial, pero a veces la manera más rápida de encontrar errores es sólo para volcar la mayor cantidad de información posible a la consola. Firebug te ofrece un conjunto de potentes <strong>funciones de registro</strong> que te ayudan a obtener respuestas rápidas.</li>
</ul>
<h2>Configuración de Firebug</h2>
Después de ver todas estas funcionalidades seguro que te hemos convencido y ya lo tienes instalado. Así que vamos a ver las opciones básicas de configuración para que puedas empezar a trabajar con este complemento de una manera cómoda y eficaz.

<img style="float: right;" title="Opciones de Firebug" src="/app/uploads/sites/7/2009/11/313073-190899.jpg" alt="Opciones de Firebug" width="195" height="200" />Habrás visto que tras la instalación te aparece un pequeño escarabajo en gris en la barra de estado inferior. Cuando lo pulsas se colorea y aparece una ventana en la parte inferior del navegador. Para acceder a las opciones debemos pulsar el escarabajo de la parte superior izquierda de esta nueva ventana. Se desplegará el listado de opciones siguiente:
<ul>
	<li>Abrir Firebug [F12]</li>
	<li>Abrir Firebug en ventana nueva [Mayus+F12]</li>
	<li>Open with editor</li>
	<li>Tamaño del texto</li>
	<li>Opciones</li>
	<li>Firebug Online</li>
	<li>Inspeccionar elemento [Ctrl+Shift+C | ⌘⇧C]</li>
	<li>Perfilar Javascript [Ctrl+Shift+P | ⌘⇧P]</li>
	<li>Linea de Comandos [Ctrl+Shift+L | ⌘⇧L]</li>
	<li>Buscar [Ctrl+Shift+K | ⌘⇧K]</li>
	<li>Customize shortcuts</li>
	<li>About... (versión)</li>
</ul>
Te recomiendo que en el apartado <strong>Opciones</strong> selecciones las siguientes:
<ul>
	<li><strong>Shade box model</strong>: Cuando inspecciones elementos te mostrará el modelo de caja del elemento, coloreando de azul el contenido, de morado el padding y de amarillo el margin. Si la deshabilitas, simplemente te pondrá un borde azul en el elemento inspeccionado.</li>
	<li><strong>Enable Accesibility Enhancements</strong>: Te marca con un cadrado naranja la opción que tienes marcada, tal y como se ve en la foto anterior, donde está marcado el escarabajo</li>
	<li><strong>Activate Same Origin URLs</strong>: Con esta opción activa recordaremos el estado del Firebug mientras estemos en el mismo dominio. Si activamos Firebug en dominio.com también estará en dominio.com/folder y en foo.dominio.com.</li>
</ul>
Con estas nociones básica podeis investigar un poquillo las opciones que ofrece Firebug e ir familiarizandoos con este maravilloso plugin. En próximos artículos veremos como sacarle el máximo partido a Firebug en los diferentes entornos HTML, CSS y Javascript, así como las opciones que nos ofrecen los complementos para Firebug.

Cuentanos qué es lo que más te gusta de Firebug y cómo le sacas el máximo rendimiento. ¿Te gustaría compartir con nosotros de qué manera te ayuda Firebug en el día a día como frontend developer?