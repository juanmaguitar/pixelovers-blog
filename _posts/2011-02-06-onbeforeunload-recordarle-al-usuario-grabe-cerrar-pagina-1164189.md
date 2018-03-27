---
ID: 2491
post_title: 'onBeforeUnload: Cómo recordarle al usuario que grabe antes de cerrar una pagina'
author: JuanMa Garrido
post_excerpt: |
  <p>
  Asi, para una captura de este evento de la siguiente manera:
  </p>
  <blockquote>
  <p>
  <em>window.onbeforeunload = confirmaSalida;&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>function</em> <em>confirmaSalida</em><em>()&nbsp;&nbsp;
  {&nbsp;&nbsp;&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; return "Vas a
  abandonar esta pagina. Si has hecho algun cambio sin grabar vas
  a perder todos los datos.";&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>}</em>
  </p>
  </blockquote>
  <p>
  Al cerrar la ventana nos apareceria el aviso. Este aviso tiene
  diferente formato según el navegador:
  </p>
  <p>
  En <em>Internet Explorer:</em>
  </p>
  <p>
  <em><img src=
  http://stc.obolog.net/multimedia/fotos/1165000/1164189/1164189-330241.jpg
  alt="" width="543" height="152"/></em>
  </p>
  <p>
  En <em>Firefox:</em>
  </p>
  <p>
  <em><img src=
  http://stc.obolog.net/multimedia/fotos/1165000/1164189/1164189-330242.jpg
  alt="" width="477" height="203"/></em>
  </p>
  <p>
  En <em>Chrome:</em>
  </p>
  <p>
  <em><img src=
  http://stc.obolog.net/multimedia/fotos/1165000/1164189/1164189-330243.jpg
  alt="" width="538" height="156"/></em>
  </p>
  <p>
  Si capturamos este evento deberiamos controlar cuando es
  necesario mostrar el mensaje (por ejemplo si el usuario no ha
  modificado ningun dato no deberia aparecer).
  </p>
  <p>
  Para esto podemos utilizar tranquilamente una variable que se
  ponga a TRUE cuando deba aparecer el mensaje:
  </p>
  <blockquote>
  <p>
  <em>window.onbeforeunload = confirmaSalida;&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>function</em> <em>confirmaSalida</em><em>()&nbsp;&nbsp;
  {&nbsp;&nbsp;&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if
  (datosModificadosSinGuardar) {</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; return "Vas a abandonar
  esta pagina. Si has hecho algun cambio sin grabar vas a perder
  todos los datos.";&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</em>
  </p>
  <p>
  <em>}</em>
  </p>
  </blockquote>
  <p>
  Si queremos utilizar jQuery, tendremos que modificar el atributo
  returnValue del objeto que representa al evento:
  </p>
  <blockquote>
  <p>
  <em>$(window).bind(“beforeunload”, function(eEvent)
  {&nbsp;&nbsp;&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if
  (datosModificadosSinGuardar) {</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; eEvent.returnValue "Vas a
  abandonar esta pagina. Si has hecho algun cambio sin grabar vas
  a perder todos los datos.";&nbsp;&nbsp;</em>
  </p>
  <p>
  <em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</em>
  </p>
  <p>
  <em>}</em>
  </p>
  </blockquote>
  <p>
  Asi que con <strong>onBeforeUnload</strong> podemos añadir un
  detalle extra de seguridad para nuestros usuarios.
  </p>
  <p>
  ¿Qué opinas de esta funcion? ¿La conocias?
  </p>
  <p>
  Esperamos vuestros comentarios
  </p>
layout: post
permalink: >
  https://pixelovers.com/onbeforeunload-recordarle-al-usuario-grabe-cerrar-pagina-1164189/
published: true
post_date: 2011-02-06 23:56:00
---
Hace poco me surgió para un proyecto la necesidad de interceptar el cierre de la pestaña del navegador. La idea era que si el usuario estaba editando los datos de un formulario y cerraba la pestaña sin haber guardado estos datos, se le avisara de que iba a perder los datos y se le diera la oportunidad de cancelar el cierre y guardar la información del formulario.

Asi que investigando un poco descubri el evento onBeforeUnload que se comporta de una forma peculiar.<!--more-->

<strong>onBeforeUnload</strong> se lanza antes de que se descargue el contenido de la pagina, y es una funcion que está integrada en la mayoria de los navegadores. En los navegadores
donde no esté definida simplemente se ignora la asignación de este evento.

El tema es que el manejador de este evento debe devolver una cadena que es la que se mostrará al usuario junto con los botones de “Abandonar la página” o “Permanecer en la página”

Asi, para una captura de este evento de la siguiente manera:
<pre class="lang:js decode:true">window.onbeforeunload = confirmaSalida;  

function confirmaSalida()  
{    

       return "Vas a
abandonar esta pagina. Si has hecho algun cambio sin grabar vas
a perder todos los datos.";  

}

</pre>
Al cerrar la ventana nos apareceria el aviso. Este aviso tiene diferente formato según el navegador:

En <em>Internet Explorer:</em>

<em><img src="http://stc.obolog.net/multimedia/fotos/1165000/1164189/1164189-330241.jpg" alt="" width="543" height="152" /></em>

En <em>Firefox:</em>

<em><img src="http://stc.obolog.net/multimedia/fotos/1165000/1164189/1164189-330242.jpg" alt="" width="477" height="203" /></em>

En <em>Chrome:</em>

<em><img src="http://stc.obolog.net/multimedia/fotos/1165000/1164189/1164189-330243.jpg" alt="" width="538" height="156" /></em>

Si capturamos este evento deberiamos controlar cuando es necesario mostrar el mensaje (por ejemplo si el usuario no ha modificado ningun dato no deberia aparecer).

Para esto podemos utilizar tranquilamente una variable que se ponga a <code>true</code> cuando deba aparecer el mensaje:
<pre class="lang:js decode:true">window.onbeforeunload = confirmaSalida;  

function confirmaSalida() {    
       if(datosModificadosSinGuardar) {
          return "Vas a abandonar esta pagina. Si has hecho algun cambio sin grabar vas a perdertodos los datos.";  
       }
}
</pre>
&nbsp;

Si queremos utilizar jQuery, tendremos que modificar el atributo <code>returnValue</code> del objeto que representa al evento:
<pre class="lang:js decode:true">$(window).bind(“beforeunload”, function(eEvent) {    
       if (datosModificadosSinGuardar) {
             eEvent.returnValue "Vas a abandonar esta pagina. Si has hecho algun cambio sin grabar vas a perder todos los datos.";  
       }
}
</pre>
&nbsp;

Asi que con <strong>onBeforeUnload</strong> podemos añadir un detalle extra de seguridad para nuestros usuarios.

¿Qué opinas de esta funcion? ¿La conocias?

Esperamos vuestros comentarios