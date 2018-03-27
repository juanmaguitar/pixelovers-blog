---
ID: 2465
post_title: RMSForms, framework CSS para formularios
author: Jorge del Casar
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/rmsforms-framework-css-formularios-478263/
published: true
post_date: 2010-01-07 09:21:00
---
<img style="float: right;" title="Robert M. Sandy Jr." src="/app/uploads/sites/7/2010/01/478263-210167.jpg" alt="Robert M. Sandy Jr." width="65" height="65" />Si eres desarrollador web, seguro que alguna vez has maldecido cuando te ha tocado maquetar formularios. Y es totalmente normal, a veces se convierte en un quebradero de cabeza suplicio. <a lang="en_EN" title="Robert M. Sandy Jr. website" href="http://www.rmsjr.com/" target="_blank" hreflang="en_EN">Robert M. Sandy Jr.</a> ha pensado en ello y por eso a desarrollado <a lang="en_EN" title="Read more about RMSForms" href="http://www.rmsjr.com/blog/web-design/rmsforms-a-flexible-tableless-css-forms-framework/" target="_blank" hreflang="en_EN">RMSForms</a>, un framework CSS para ayudar a dar estilo a los molestos formularios. No solo se centra en las incoherencias de los navegadores, si no también en conseguir una disposición correcta tanto visualmente como semánticamente. Así que si tienes que hacer una web con muchos formularios, puedes plantearte utilizar esta hoja de estilo de menos de 100 líneas, sin comentarios, y un tamaño de 8Kb.<!--more-->

Está basado en una estructura HTML muy simple:
<pre class="lang:xhtml decode:true ">&lt;fieldset&gt;
  &lt;legend&gt;&lt;/legend&gt;
  &lt;ul class="form [modifier]"&gt;
    &lt;li&gt;&lt;label class="[label modifier]"&gt;&lt;/label&gt;&lt;input/&gt;&lt;/li&gt;
  &lt;/ul&gt; 
 &lt;/fieldset&gt;</pre>
Donde los modificadores están compuestos por 3 letras:
<ul>
	<li><strong>H</strong> = Bloque Horizonal</li>
	<li><strong>V</strong> = Bloque Vertical</li>
	<li><strong>I</strong> = Inline</li>
</ul>
Y se pueden generar los siguientes:
<ul>
	<li><strong>vvv</strong> – Vertical &lt;li&gt;, Vertical &lt;label&gt;, Vertical campos de formulario</li>
	<li><strong>hvv</strong> – Horizontal &lt;li&gt;, Vertical &lt;label&gt;, Vertical campos de formulario</li>
	<li><strong>hii</strong> – Horizontal &lt;li&gt;, Inline &lt;label&gt;, Inline campos de formulario</li>
	<li><strong>hhh</strong> – Horizontal &lt;li&gt;, Horizontal &lt;label&gt;, Horizontal campos de formulario</li>
	<li><strong>vii</strong> – Vertical &lt;li&gt;, Inline &lt;label&gt;, Inline campos de formulario</li>
	<li><strong>vhh</strong> – Vertical &lt;li&gt;, Horizontal &lt;label&gt;, Horizontal campos de formulario</li>
</ul>
Si queréis ver el resultado, aquí tenéis un <a title="Demo RMSForm" href="http://www.rmsjr.com/RMSforms/RMSforms-v0.5.html" target="_blank">ejemplo de RMSForm</a>.