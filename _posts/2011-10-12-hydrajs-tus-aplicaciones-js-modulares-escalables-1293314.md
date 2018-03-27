---
ID: 2495
post_title: >
  Hydra.js, para hacer tus aplicaciones JS
  modulares y escalables
author: JuanMa Garrido
post_excerpt: |
  <p>
  En su dia, <a href="http://www.nczonline.net/" target=
  "_blank">Nicholas Zakas</a>&nbsp;(ex-Front End Engineer de Yahoo)
  hizo una <a href=
  http://www.slideshare.net/nzakas/scalable-javascript-application-architecture
  target="_blank">presentación</a> de las ventajas de hacer una
  aplicación con esta arquitectura y de cómo implementarlo.&nbsp;
  </p>
  <p>
  El esquema general de esta arquitectura es este:
  </p>
  <p>
  <img class="undefined" title="" src=
  http://stc.obolog.net/photos/4e95/4e9577703091cs51272_p.jpg
  alt=" TAGS:" align="center"/>
  </p>
  <p>
  Desde hace unos meses tenemos disponible <a href=
  "https://github.com/tcorral/Hydra.js" target=
  "_blank"><strong>Hydra.js</strong></a>&nbsp;un gestor de modulos
  que nos permite implementar todo este sistema de modulos en
  nuestro site de manera sencilla.&nbsp;
  </p>
  <p>
  Su autor es&nbsp;<a href="https://github.com/tcorral">Tomas
  Corral</a> actual Javascript Expert en Softonic.com y
  Evangelizador del Performance &amp;&nbsp;Buenas Prácticas en
  el&nbsp;JS.&nbsp;
  </p>
  <p>
  Algunas de las ventajas de Hydra son:
  </p>
  <ul>
  <li>Ningun módulo conoce la existencia de otros modulos (lo que
  implica que si falla un modulo, el resto seguiran funcionando)
  </li>
  <li>Un modulo puede notificar algo y le llegará a todos los
  modulos que esten esuchando
  </li>
  <li>Un modulo puede ser extendido&nbsp;
  </li>
  <li>Los modulos pueden ser testeados mediante Unit Testings
  </li>
  <li>Sólo ocupa 1.5kb comprimido
  </li>
  </ul>
  <div>
  ¿Cómo quedaria un modulo tipo en Hydra? Pues asi:
  </div>
  <pre style=
  "margin-top: 20px; background-color: #efefef; padding: 1em 0.5em; font-family: monospace;">
  
  Hydra.module.register('moduleId', function(action)
  {
  return {
  init: function (oData) {
  action.listen(['action1', 'action2', 'actionN'], this.handleAction, this);
  $("#button").click(function(){
  action.notify({
  type: 'listenedAction',
  data: 'data'
  });
  });
  },
  actionHandlers: {
  action1: function (oData) {},
  action2: function (oData) {},
  actionN: function (oData) {}
  },
  handleAction: function (oNotifier){
  var oHandler = this.actionHandlers[oNotifier.type]
  if(typeof oHandler === "undefined")
  {
  return;
  }
  oHandler.call(this, oData);
  oHandler = null;
  },
  destroy: function () {}
  };
  });
  </pre>
  <p>
  &nbsp;
  </p>
  <p>
  Para más info sobre Hydra puedes visitar <a href=
  "https://github.com/tcorral/Hydra.js" target="_blank">su pagina
  en GitHub</a> desde donde te puedes hacer un clone del proyecto.
  </p>
  <p>
  ¿Que te ha parecido este gestor de modulos? ¿Lo conocias? ¿Has
  implementado alguna arquitectura similar en tu aplicación?
  &nbsp;Esperamos vuestros comentarios
  </p>
  <p>
  &nbsp;
  </p>
layout: post
permalink: >
  https://pixelovers.com/hydrajs-tus-aplicaciones-js-modulares-escalables-1293314/
published: true
post_date: 2011-10-12 12:26:00
---
<a href="http://pixelovers.com/app/uploads/sites/7/2011/10/16-04-2015-13-07-25.png"><img class="alignnone size-full wp-image-2807" src="http://pixelovers.com/app/uploads/sites/7/2011/10/16-04-2015-13-07-25.png" alt="16-04-2015 13-07-25" width="569" height="183" /></a>

¿Tu JavaScript se va haciendo cada vez mas grande y se está volviendo immanejable? ¿Estas buscando alguna arquitectura que te permita hacer tu aplicacion más escalable?

Para aplicaciones que se van haciendo grandes la mejor solucion es la de aplicar una <strong>arquitectura de diseño modular</strong>.

<!--more-->

Dicho de forma sencilla <strong>un modulo</strong> seria el código que controla un trozo de HTML (y nada más), o dicho de otra forma, un grupo de HTML + CSS + JS autónomo.

Por ejemplo, en Yahoo utilizan esta arquitectura lo que les permite realizar codigo JS individualmente a cada modulo que implementan. Esto seria un modulo de Yahoo:

<img class="undefined" title="" src="/app/uploads/sites/7/2011/10/4e956f6145cf3s69268.jpg" alt=" TAGS:" align="center" />

En su dia, <a href="http://www.nczonline.net/" target="_blank">Nicholas Zakas</a> (ex-Front End Engineer de Yahoo) hizo una <a href="http://www.slideshare.net/nzakas/scalable-javascript-application-architecture" target="_blank">presentación</a> de las ventajas de hacer una aplicación con esta arquitectura y de cómo implementarlo.

El esquema general de esta arquitectura es este:

<img class="undefined" title="" src="http://stc.obolog.net/photos/4e95/4e9577703091cs51272_p.jpg" alt=" TAGS:" align="center" />

Desde hace unos meses tenemos disponible <a href="https://github.com/tcorral/Hydra.js" target="_blank"><strong>Hydra.js</strong></a> un gestor de modulos que nos permite implementar todo este sistema de modulos en nuestro site de manera sencilla.

Su autor es <a href="https://github.com/tcorral">Tomas Corral</a> ex-Javascript Arquitect en Softonic.com y
Evangelizador del Performance &amp; Buenas Prácticas en
el JS.

Algunas de las ventajas de Hydra son:
<ul>
	<li>Ningun módulo conoce la existencia de otros modulos (lo que implica que si falla un modulo, el resto seguiran funcionando)</li>
	<li>Un modulo puede notificar algo y le llegará a todos los modulos que esten esuchando</li>
	<li>Un modulo puede ser extendido</li>
	<li>Los modulos pueden ser testeados mediante Unit Testings</li>
	<li>Sólo ocupa 1.5kb comprimido</li>
</ul>
<div>¿Cómo quedaria un modulo tipo en Hydra? Pues asi:</div>
<pre class="lang:js decode:true ">Hydra.module.register('moduleId', function(action) {
    return {
        init: function (oData) {
            action.listen(['action1', 'action2', 'actionN'], this.handleAction, this);
            $("#button").click(function(){
                action.notify({
                    type: 'listenedAction',
                    data: 'data'
                });
            });
        },
        actionHandlers: {
            action1: function (oData) {},
            action2: function (oData) {},
            actionN: function (oData) {}
        },
        handleAction: function (oNotifier){
            var oHandler = this.actionHandlers[oNotifier.type]
            if(typeof oHandler === "undefined")
            {
                return;
            }
            oHandler.call(this, oData);
            oHandler = null;
        },
        destroy: function () {}
    };
});
</pre>
&nbsp;

Para más info sobre Hydra puedes visitar <a href="https://github.com/tcorral/Hydra.js" target="_blank">su pagina en GitHub</a> desde donde te puedes hacer un clone del proyecto.

¿Que te ha parecido este gestor de modulos? ¿Lo conocias? ¿Has implementado alguna arquitectura similar en tu aplicación?

Esperamos vuestros comentarios