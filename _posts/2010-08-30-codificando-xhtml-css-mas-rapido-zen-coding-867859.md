---
ID: 2486
post_title: >
  Zen Coding, codificando XHTML y CSS a
  velocidad de crucero
author: JuanMa Garrido
post_excerpt: |
  <h2>
  Ejemplos
  </h2>
  <p>
  Veamos un ejemplo sencillo. Esta abreviación :
  </p>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #eaf5fc; margin: 8px;">
  
  <code>
  div#page&gt;div.logo+ul#navigation&gt;li*5&gt;a
  
  </code>
  </pre>
  <p>
  Nos generaria lo siguiente (con una combinación de teclas que
  depende del editor, pero normalmente CTRL + ,)
  </p>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #ecfcea; margin: 8px;">
  
  
  </pre>
  <p>
  Otro ejemplo mas completo. La siguiente abreviación:
  </p>
  <pre style=
  "color: #000000; font: normal normal normal 12px/1.5em 'Lucida Grande', Helvetica, Arial, sans-serif; background-color: #eaf5fc; margin: 8px;">
  
  <code>
  html:xs&gt;(div#header.header&gt;img.logo[src="http://www.google.es" title="logo" alt=
  "logo"])+(div#content.content&gt;h1+p*5)+(div#footer.footer&gt;ul&gt;li*5&gt;a[href="./"])
  
  </code>
  </pre>
  <p>
  Nos generaria el siguiente código:
  </p>
  <div id="header">
  <img class="logo" title="logo" src="http://www.google.es" alt=
  "logo"/>
  </div>
  <div id="content">
  &nbsp;
  </div>
  <div id="footer">
  &nbsp;
  </div>
  <p>
  Mola , eh?
  </p>
  <h2>
  Editores
  </h2>
  <p>
  Hay una serie de plugins oficiales (desarrollados por el equipo
  de Zen Coding y con todas las caracteristicas de Zen Coding)
  </p>
  <ul>
  <li>Aptana/Eclipse (crossplatform)
  </li>
  <li>TextMate (Mac).
  </li>
  <li>Coda (Mac)
  </li>
  <li>Espresso (Mac)
  </li>
  <li>Komodo Edit/IDE (crossplatform)
  </li>
  <li>Notepad++ (Windows)
  </li>
  <li>PSPad (Windows)
  </li>
  <li>
  <textarea>
  (browser-based)&lt;/li&gt;
  &lt;li&gt;editArea (browser-based)&lt;/li&gt;
  &lt;/ul&gt;
  &lt;p&gt;Pero ademas hay plugins desarrollados por terceros (en los que no se garantiza que esten disponibles todas las funcionalidades de Zen Coding) como pueden ser los de Dreamweaver o los de Vim&lt;/p&gt;
  &lt;p&gt;Puedes acceder a todos los plugins disponibles para los editores desde &lt;a href="http://code.google.com/p/zen-coding/downloads/list" target="_blank"&gt;aquí&lt;/a&gt; o desde &lt;a href="http://code.google.com/p/zen-coding/" target="_blank"&gt;aquí&lt;/a&gt; &lt;/p&gt;
  &lt;h2 style="font-size: 1.5em;"&gt;Enlaces y mas&lt;/h2&gt;
  &lt;ul&gt;
  &lt;li&gt;&lt;a href="http://www.smashingmagazine.com/2009/11/21/zen-coding-a-new-way-to-write-html-code/" target="_blank"&gt;Zen Coding: A Speedy Way To Write HTML/CSS Code&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="http://code.google.com/p/zen-coding/" target="_blank"&gt;Zen Coding — a new way of writing HTML and CSS code&lt;/a&gt; &lt;/li&gt;
  &lt;li&gt;&lt;a href="http://zen-coding.googlecode.com/files/ZenCodingCheatSheet.pdf" target="_blank"&gt;Zen Coding cheat sheet (PDF) &lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="http://zen-coding.ru/demo/" target="_blank"&gt;Zen Coding Demo&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
  &lt;p&gt;En definitiva, esta es una herramienta de las que dices “¿Dónde has estado toda mi vida?”. Se acostumbra uno muy rapido a utilizarla ya que te ahorra muuuuuucho tiempo a la hora de codificar HTML/XML/CSS. Dentro de poco os vereis haciendo "CTRL + ," en cualquier editor de textos  ;-) &lt;/p&gt;
  &lt;p&gt;¿Qué os parece esta herramienta? ¿La conocíais? ¿Conoceis alguna herramienta similar?&lt;/p&gt;
  &lt;p&gt;Esperamos vuestros comentarios.&lt;/p&gt;
  </textarea>
  </li>
  </ul>
layout: post
permalink: >
  https://pixelovers.com/codificando-xhtml-css-mas-rapido-zen-coding-867859/
published: true
post_date: 2010-08-30 09:00:00
---
<a href="http://pixelovers.com/app/uploads/sites/7/2010/08/512.png"><img class="alignnone  wp-image-2853" src="http://pixelovers.com/app/uploads/sites/7/2010/08/512-300x300.png" alt="512" width="224" height="200" /></a>

<strong>Zen Coding</strong> es un plugin que está disponible para casi todos los editores del mercado y con el que podras <strong>codificar HTML/XML/CSS a gran velocidad</strong>.

<!--more-->

Este plugin nos ofrece dos funcionalidades:

<ul>
    <li style="margin-top: 10px;">Expansión de abreviaciones: con unas <a href="http://code.google.com/p/zen-coding/wiki/ZenHTMLElementsEn" target="_blank">abreviaciones determinadas</a> (muy sencillas, ya que son muy parecidas a los selectores de CSS) podremos generar gran cantidad código HTML/XML/CSS con una simple combinación de teclas.</li>
    <li style="margin-top: 10px;">Selección de bloques (pares de tags): Pudiendo realizar <a href="http://code.google.com/p/zen-coding/wiki/Actions" target="_blank">una serie de acciones</a> como seleccionar pares de tags, ir a zonas editables de los tags, envolver (wrap) un bloque con otras abreviaciones, comentar/borrar bloques y más cosas.</li>
</ul>

Para que veais lo que se puede hacer con este plugin os dejo aquí un video.

<object data="http://vimeo.com/moogaloop.swf?clip_id=7405114&amp;server=vimeo.com&amp;show_title=1&amp;show_byline=1&amp;show_portrait=0&amp;color=00ADEF&amp;fullscreen=1" type="application/x-shockwave-flash" width="500" height="344"><param name="allowfullscreen" value="true" /><param name="allowscriptaccess" value="always" /><param name="src" value="http://vimeo.com/moogaloop.swf?clip_id=7405114&amp;server=vimeo.com&amp;show_title=1&amp;show_byline=1&amp;show_portrait=0&amp;color=00ADEF&amp;fullscreen=1" /></object>

También hay disponible una <a href="http://zen-coding.ru/demo/" target="_blank">demo online</a> desde la que podeis probar su funcionamiento via web

<h2>Ejemplos</h2>

Veamos un ejemplo sencillo. Esta abreviación :

<pre class="lang:xhtml decode:true"> div#page&gt;div.logo+ul#navigation&gt;li*5&gt;a
</pre>

Nos generaria lo siguiente (con una combinación de teclas que depende del editor, pero normalmente<code>CTRL + ,</code> )

<pre class="lang:xhtml decode:true">&lt;div id="page"&gt;
  &lt;div class="logo"&gt;&lt;/div&gt;
  &lt;ul id="navigation"&gt;
    &lt;li&gt;&lt;a&gt;&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a&gt;&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a&gt;&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a&gt;&lt;/a&gt;&lt;/li&gt;
    &lt;li&gt;&lt;a&gt;&lt;/a&gt;&lt;/li&gt;
  &lt;/ul&gt;
&lt;/div&gt;</pre>

Otro ejemplo mas completo. La siguiente abreviación:

<pre class="lang:xhtml decode:true"> html:xs&gt;(div#header.header&gt;img.logo[src="http://www.google.es" title="logo" alt="logo"])+(div#content.content&gt;h1+p*5)+(div#footer.footer&gt;ul&gt;li*5&gt;a[href="./"])</pre>

Nos generaria el siguiente código:

<pre class="lang:xhtml decode:true ">&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"&gt;
&lt;html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en"&gt;
&lt;head&gt;
    &lt;meta http-equiv="Content-Type" content="text/html;charset=UTF-8"&gt;
    &lt;title&gt;Document&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;div id="header" class="header"&gt;&lt;img src="http://www.google.es" alt="logo" class="logo" title="logo"&gt;&lt;/div&gt;
    &lt;div id="content" class="content"&gt;
        &lt;h1&gt;&lt;/h1&gt;
        &lt;p&gt;&lt;/p&gt;
        &lt;p&gt;&lt;/p&gt;
        &lt;p&gt;&lt;/p&gt;
        &lt;p&gt;&lt;/p&gt;
        &lt;p&gt;&lt;/p&gt;
    &lt;/div&gt;
    &lt;div id="footer" class="footer"&gt;
        &lt;ul&gt;
            &lt;li&gt;&lt;a href="./"&gt;&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href="./"&gt;&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href="./"&gt;&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href="./"&gt;&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href="./"&gt;&lt;/a&gt;&lt;/li&gt;
        &lt;/ul&gt;
    &lt;/div&gt;
&lt;/body&gt;
&lt;/html&gt;</pre>

Mola , eh?

<h2>Editores</h2>

Hay una serie de plugins oficiales (desarrollados por el equipo
de Zen Coding y con todas las caracteristicas de Zen Coding)

<ul>
    <li>Aptana/Eclipse (crossplatform)</li>
    <li>TextMate (Mac).</li>
    <li>Coda (Mac)</li>
    <li>Espresso (Mac)</li>
    <li>Komodo Edit/IDE (crossplatform)</li>
    <li>Notepad++ (Windows)</li>
    <li>PSPad (Windows)</li>
    <li>editArea (browser-based)</li>
</ul>

Pero ademas hay plugins desarrollados por terceros (en los que no se garantiza que esten disponibles todas las funcionalidades de Zen Coding) como pueden ser los de Dreamweaver o los de Vim

Puedes acceder a todos los plugins disponibles para los editores desde <a href="http://code.google.com/p/zen-coding/downloads/list" target="_blank">aquí</a> o desde <a href="http://code.google.com/p/zen-coding/" target="_blank">aquí</a>

<h2 style="font-size: 1.5em;">Enlaces y mas</h2>

<ul>
    <li><a href="http://www.smashingmagazine.com/2009/11/21/zen-coding-a-new-way-to-write-html-code/" target="_blank">Zen Coding: A Speedy Way To Write HTML/CSS Code</a></li>
    <li><a href="http://code.google.com/p/zen-coding/" target="_blank">Zen Coding — a new way of writing HTML and CSS code</a></li>
    <li><a href="http://zen-coding.googlecode.com/files/ZenCodingCheatSheet.pdf" target="_blank">Zen Coding cheat sheet (PDF) </a></li>
    <li><a href="http://zen-coding.ru/demo/" target="_blank">Zen Coding Demo</a></li>
</ul>

En definitiva, esta es una herramienta de las que dices “¿Dónde has estado toda mi vida?”. Se acostumbra uno muy rapido a utilizarla ya que te ahorra muuuuuucho tiempo a la hora de codificar HTML/XML/CSS. Dentro de poco os vereis haciendo "CTRL + ," en cualquier editor de textos ;-)

¿Qué os parece esta herramienta? ¿La conocíais? ¿Conoceis alguna herramienta similar?

Esperamos vuestros comentarios.

<h3><em>UPDATE 13/05/2015: This project has moved to <a href="http://emmet.io/">http://emmet.io/</a></em></h3>