---
ID: 3508
post_title: >
  Cómo ordenar un array de strings según
  unas prioridades específicas
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/como-ordenar-un-array-segun-unos-pesos-especificos/
published: true
post_date: 2015-12-18 18:08:33
---
El otro día en un proyecto me surgió la necesidad de dejar preparado un código para que dado un array de strings, éste quedara ordenado en base a unas prioridades especificas.

Por ejemplo, dado un array de tipos de media (obtenido por ejemplo a través de una consulta a una API), me interesa que los tipo "foto" queden siempre al principio del array,  luego los tipo "audio", etc...

<pre class="lang:js decode:true">/* criteria: "foto","mapa","audio","video","interactivo" */
fnOrderMedia = makeFnSortArray("foto","audio","mapa","video","interactivo");

["audio", "mapa", "foto"].sort(fnOrderMedia)
// ["foto","audio","mapa"]
</pre>

<!--more-->Otro caso típico es el de ordenar paises para un dropdown, donde por ejemplo puedo querer que determinados paises aparezcan siempre primero (por ejemplo "Spain", "France", "Italy") y todo lo que no esté en mi lista de "primeros" quede ordenado alfabeticamente

<pre class="lang:js decode:true">/* criteria: "spain","portugal","france" */
fnOrderCountries = makeFnSortArray("spain","portugal","france");

["germany", "france", "italy", "spain", "england"].sort(fnOrderCountries)
// ["spain","france","england","germany","italy"]
</pre>

Al final, generalizando, me interesa poder ordenar un array de strings en base a un criterio personalizado y todo lo que no esté en ese criterio quede ordenado alfabeticamente.

Para esto me monté una función <em>factory</em> creadora de funciones "que ordenan en base a un array de prioridades" lista para pasársela como <em>callback</em> al <strong>método <em><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort">sort</a></em> </strong>del <em>prototype</em> de array.

Aqui teneis el código en ES2015 de esta función factory y de su aplicación:

<pre class="lang:js decode:true" title="orderArrayCriteria ES2015">const makeFnSortArray = ( ...criteria ) =&gt; {

  const order = criteria.reduce( ( o, item, i) =&gt; {
    o[item] = ++i; 
    return o;
  }, {})
  
  return (a, b) =&gt; {
    if ( (order[b] &amp;&amp; !order[a]) || order[a] &gt; order[b] ) return 1;
    if ( (order[a] &amp;&amp; !order[b]) || (order[a] &lt; order[b]) ) return -1;
    if ( a &gt; b ) return 1;
    if ( a &lt; b ) return -1;
    return 0;
  }
}
 
 
const fnOrderMedia = makeFnSortArray("foto","mapa","audio");
 
["audio", "foto", "interactivo", "mapa", "video"].sort(fnOrderMedia) 
// ["foto","mapa","audio","interactivo","video"]

</pre>

Y aqui teneis el código en ES5:

<pre class="lang:js decode:true " title="orderArrayCriteria ES5">"use strict";

var makeFnSortArray = function makeFnSortArray() {
  for (var _len = arguments.length, criteria = Array(_len), _key = 0; _key &lt; _len; _key++) {
    criteria[_key] = arguments[_key];
  }

  var order = criteria.reduce(function (o, item, i) {
    o[item] = ++i;
    return o;
  }, {});

  return function (a, b) {
    if (order[b] &amp;&amp; !order[a] || order[a] &gt; order[b]) return 1;
    if (order[a] &amp;&amp; !order[b] || order[a] &lt; order[b]) return -1;
    if (a &gt; b) return 1;
    if (a &lt; b) return -1;
    return 0;
  };
};

var fnOrderMedia = makeFnSortArray("foto", "mapa", "audio");

["audio", "foto", "interactivo", "mapa", "video"].sort(fnOrderMedia);
// ["foto","mapa","audio","interactivo","video"]</pre>

Y aqui podeis verlo en funcionamiento con unos cuantos tests:

<iframe width="100%" height="400" src="//jsfiddle.net/juanma/4ckaq2y6/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>