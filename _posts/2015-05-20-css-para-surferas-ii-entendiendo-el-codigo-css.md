---
ID: 3465
post_title: 'CSS para surferas II &#8211; Entendiendo el código CSS'
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/css-para-surferas-ii-entendiendo-el-codigo-css/
published: true
post_date: 2015-05-20 14:50:34
---
<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/css-para-surferas.png"><img class="alignnone size-full wp-image-3474" src="http://pixelovers.com/app/uploads/sites/7/2015/05/css-para-surferas.png" alt="css-para-surferas" width="680" height="360" /></a>

En el <a href="http://pixelovers.com/css-para-surferas-i-que-es-css/">post anterior</a> de esta serie <a href="http://pixelovers.com/tag/css-para-surferas/">CSS para surferas</a> ya introdujimos el CSS explicando qué era y cómo funcionaba.

En este post vamos a explicar lo necesario para poder entender un código CSS. Si bien de primeras no entenderemos todo al detalle, si que sabremos lo qué es cada cosa y donde podemos encontrar más información si queremos profundizar.

Es decir que después de leer este post vas a ser capaz de entender <a href="https://raw.githubusercontent.com/pixelovers/css-surferas/master/css-garden-210/210.css">esto</a>

¿No te lo crees? Sigue leyendo :)

<!--more-->

Empecemos por la parte más fácil de detectar en cualquier código CSS: Los comentarios

<h2>Los comentarios</h2>

Los comentarios son contenidos de texto que son insertados para añadir información sobre el propio código y que se entienda mejor.

Estos comentarios son ignorados por el navegador por lo que se utilizan para añadir explicaciones y estructurar el código CSS.

El inicio de un comentario en CSS se indica con <code>/*</code> y el final del comentario se indica con <code>*/</code>

<pre class="lang:css decode:true ">/* Este es un comentario en CSS */</pre>

Los comentarios pueden ocupar varias lineas

<pre class="lang:css decode:true ">/* Este es un
   comentario CSS de varias
   lineas */</pre>

Una vez, tenemos localizados los comentarios podemos utilizarlos para entender mejor el código CSS que tenemos delante. Normalmente se utilizan para agrupar reglas CSS que estén relacionadas (las reglas CSS que definen los estilos de la home, los estilos de la página de contacto, los estilos de la cabecera, etc...)

Fijate en <a href="http://pixelovers.github.io/css-surferas/css-garden-210/210.css">este CSS </a>cómo el código está estructurado utilizando los comentarios

<h2>Los selectores</h2>

Cómo vimos en el post anterior <a href="http://pixelovers.com/css-para-surferas-i-que-es-css/#como-funciona">CSS funciona a base de reglas</a>, y en estas reglas lo primero que definimos es el elemento (o los elementos)

O sea que una regla CSS funciona asi:

<ol>
    <li>seleccionamos con <em>los selectores</em> el elemento o el grupo de elementos sobre los que queremos definir las propiedades para modificar el diseño</li>
    <li>le damos un <em>valor</em> personalizado a todas aquellas <em>propiedades de estilo </em>(colores, margenes, etc...) que queramos personalizar para estos elementos HTML que hemos seleccionado</li>
</ol>

<h3>¿Cómo seleccionamos los elementos?</h3>

Hay muchas <a href="http://code.tutsplus.com/es/tutorials/the-30-css-selectors-you-must-memorize--net-16048">maneras</a> de seleccionar elementos HTML pero las más comunes son:

<h4><em>X</em></h4>

Podemos seleccionar elementos HTML directamente indicando el <em>tag</em> que queremos modificar.

Por ejemplo, si quisiéramos cambiar el color de todos los enlaces de la pagina haríamos algo así:

<pre class="lang:css decode:true">a { color: red; }</pre>

<h4><em>#X</em></h4>

Los tags HTML pueden tener una propiedad <code>id</code> con un nombre personalizado. Este <code>id</code> deberia ser único, así que con la almohadilla <code>#</code> podemos seleccionar elementos HTML por su <code>id</code>

Para un HTML asi

<pre class="lang:xhtml decode:true">&lt;div id="container"&gt;&lt;/div&gt;</pre>

podríamos modificar sus estilos con una regla CSS como esta

<pre class="lang:css decode:true">#container {
    width: 960px;
    margin: auto;
}</pre>

<h4><em>.X</em></h4>

Los tags HTML también pueden tener otra propiedad <code>class</code> con un nombre de clase. Estos nombres de clase se utilizan para definir estilos <em>compartidos</em> por tanto pueden ser utilizados en varios tags HTML. Podemos seleccionar aquellos elementos que tengan una clase concreta utilizando el punto <code>.</code>

Para un HTML así

<pre class="lang:xhtml decode:true">    &lt;p class="error"&gt;Ha ocurrido un error....&lt;/div&gt;
    &lt;p class="error"&gt;Pero un error MU gordo!!&lt;/div&gt;</pre>

<p class="error">podríamos modificar los estilos de los 2 <code>p</code> al mismo tiempo con una regla CSS como esta</p>

<pre class="lang:css decode:true">.error {
    color: red;
}</pre>

<h4><em>X, Y</em></h4>

Podemos agrupar selectores separándolos por comas. De esta manera podemos customizar los estilos de varios elementos a la vez

Según este HTML

<pre class="lang:xhtml decode:true">    &lt;div id="container" class="remark"&gt;
        &lt;p class="info"&gt;Introduzca los datos requeridos....&lt;/p&gt;
        &lt;input class="remark" type="text" /&gt;
    &lt;/div&gt;</pre>

<p class="info">podríamos definir estilos de varios elementos a la vez de esta manera</p>

<pre class="lang:css decode:true">div, input { border:2px solid blue; }</pre>

Con esta regla CSS le decimos al navegador que a todos los elementos <code>div</code> y <code>input</code> que encuentre los coloque un borde azul con un grosor de 2px

<h4><em>X Y</em></h4>

Otro tipo de selección que encontraras con frecuencia es el llamado selector <em>descendiente</em>. Con este tipo de selectores especificamos el contenedor sobre el que estamos seleccionando

Según este HTML

<pre class="lang:xhtml decode:true">    &lt;p class="header"&gt;Formulario de contacto&lt;/p&gt;
    &lt;div id="container" class="remark"&gt;
        &lt;p class="info"&gt;Introduzca los datos requeridos....&lt;/p&gt;
        &lt;p class="emphasis"&gt;¡que los introduzcas!&lt;/p&gt;
        &lt;input class="remark" type="text" /&gt;
    &lt;/div&gt;</pre>

<div id="container" class="remark"></div>

podriamos definir los estilos sólo de los <code>p</code> que estan dentro del tag <code>div</code> de esta manera

<pre class="lang:css decode:true">div p { font-size:20px; }</pre>

<h2>Las propiedades CSS</h2>

Una vez seleccionados los elementos HTML, definimos los estilos que queremos que tengan en un <em>bloque de declaraciones</em>

Cada bloque de declaraciones consta de un par <em>propiedad-valor</em> como ya vimos en el <a href="http://pixelovers.com/css-para-surferas-i-que-es-css/#como-funciona">post anterior</a>

Hay un montón de propiedades CSS que podemos utilizar para definir nuestros estilos. Y cada propiedad podrá tomar unos valores concretos.

Por ejemplo según este HTML

<pre class="lang:xhtml decode:true ">    &lt;p class="header"&gt;Formulario de contacto&lt;/p&gt;
    &lt;div id="container" class="remark"&gt;
        &lt;p class="info"&gt;Introduzca los datos requeridos....&lt;/p&gt;
        &lt;p class="emphasis"&gt;¡que los introduzcas!&lt;/p&gt;
        &lt;input class="remark" type="text" /&gt;
    &lt;/div&gt;</pre>

<div id="container" class="remark"></div>

sin estilos se vería así

<img class="alignnone size-full wp-image-3469" src="http://pixelovers.com/app/uploads/sites/7/2015/05/CSS2-2.png" alt="HTML sin estilos CSS" width="260" height="161" />

Y con estos estilos

<pre class="lang:css decode:true">.header { font-size:30px; }
#container { padding:20px; }
div, input { border:2px solid blue; }
div p { font-weight:bold; }
.emphasis { background:yellow; }</pre>

Se vería así:

<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/CSS2-1.png"><img class="alignnone wp-image-3470 size-full" title="HTML con estilos CSS" src="http://pixelovers.com/app/uploads/sites/7/2015/05/CSS2-1.png" alt="HTML con estilos CSS" width="483" height="237" /></a>

La lista completa de propiedades CSS la puedes encontrar por internet.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Reference">Aquí</a> tienes una lista de todas las propiedades CSS listadas alfabéticamente. Y <a href="http://reference.sitepoint.com/css/propertyref">aquí</a> una lista de propiedades CSS ordenadas por categorías. <a href="http://www.blooberry.com/indexdot/css/propindex/all.htm">Otra lista</a> por aqui y <a href="http://meiert.com/en/indices/css-properties/">otra más</a> por aquí

Asi que cuando te encuentres un CSS puedes buscar en cualquiera de estas listas las propiedades que veas en el código para saber qué estilos están modificando y qué valores pueden tomar

<hr />

Y con esto terminamos este post. Después de leerlo deberías ser capaz de entender "a grosso modo" un CSS como <a href="http://pixelovers.github.io/css-surferas/css-garden-210/210.css">este</a> que es el que está definiendo los estilos de <a href="http://pixelovers.github.io/css-surferas/css-garden-210/index.html">esta pagina</a>

<a href="https://www.youtube.com/watch?v=6vMO3XmNXe4">Ya sabes kung-fu</a>!! ;)