---
ID: 3690
post_title: >
  Monta fácilmente una version de pruebas
  (staging) de tu sitio wordpress
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/monta-facilmente-una-version-pruebas-sitio-wordpress/
published: true
post_date: 2016-05-16 07:00:32
---
Conozco muchos usuarios de wordpress (sobre todo no-técnicos) que han sabido exprimir al máximo su sitio wordpress (la mayoría blogs) pero que siguen sin tener una manera fácil y segura de probar nuevas cosas para su sitio web.

Cuando quieren hacer pequeñas modificaciones de diseño, instalar un plugin o probar algún truco que han leído en algún blog terminan haciendo estos "experimentos" directamente en su sitio público de producción.

<strong>Hacer experimentos directamente en tu sitio de producción</strong> <strong>es una MUY mala práctica ya que nos podemos cargar nuestro sitio wordpress.</strong>

Para evitar probar cosas nuevas (de las que no tenemos muy claro el resultado final) directamente en producción, muchos proyectos tienen una "versión de pruebas" de su sitio wordpress para poder hacer estos "experimentos" sin peligro.

<!--more-->

Cuando tenemos un sitio web con wordpress que es público y que es accesible mediante nuestro dominio llamamos a este sitio <strong>producción.</strong>

Por ejemplo, la web que puedes ver en<a href="http://pixelovers.com"> http://pixelovers.com</a> es mi sitio de producción.

Así que lo que podemos hacer es crear una copia, a partir de este sitio de producción, para convertirla en nuestra  versión de pruebas. Este nuevo sitio tendrá su propia URL y ahí podremos hacer pruebas sin peligro de romper nada en el sitio que están visitando diariamente nuestros usuarios.

En este post vamos a ver cómo crear un sitio de pruebas:

<ul>
    <li>manualmente (varios pasos)</li>
    <li>sólo pulsando un botón :)</li>
</ul>

<h2>Crear una version de pruebas ( staging) de mi sitio web manualmente</h2>

La solución más general es crear a mano una copia de nuestro sitio en nuestro propio servidor de hosting. En la mayoría de planes de hosting gestionados por <a href="http://cpanel.com/">cPanel</a> podemos crear subdominios asociados a nuestro dominio y poner ahí una copia de nuestro sitio wordpress.

Por ejemplo, para <a href="http://pixelovers.com">http://pixelovers.com</a> me puedo crear otro site para hacer pruebas que sea una copia exacta de mi actual sitio en producción. Esta versión de pruebas se suele llamar <em><strong>staging, </strong></em>así que me puedo crear un subdominio llamado <a href="http://staging.pixelovers.com">http://staging.pixelovers.com</a> y crear ahí la copia de mi site.

Si tu hosting utiliza cPanel, los pasos para crear esta versión staging de tu site serían <em>a grosso modo:</em>

<h5>1.- Creamos un subdominio</h5>

Creamos un subdominio (normalmente "staging") asociado a nuestro dominio: <em>staging.midominio.com</em>

[caption id="attachment_3693" align="alignnone" width="300"]<a href="http://pixelovers.com/app/uploads/sites/7/2016/05/crear-subdominio.png"><img class="size-medium wp-image-3693" src="http://pixelovers.com/app/uploads/sites/7/2016/05/crear-subdominio-300x87.png" alt="Crear subdominio con cPanel" width="300" height="87" /></a> Crear subdominio con cPanel[/caption]

Cuando esté creado se nos asocia un espacio en nuestro servidor asociado a este subdominio

[caption id="attachment_3694" align="alignnone" width="846"]<img class="wp-image-3694 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/subdominio-creado.png" alt="subdominio-creado" width="846" height="86" /> Subdominio creado en cPanel[/caption]

Y podemos chequear que nuestro subdominio se ha creado correctamente

[caption id="attachment_3696" align="alignnone" width="433"]<img class="wp-image-3696 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/staging-pixelovers.png" alt="staging-pixelovers" width="433" height="248" /> contenido subdominio recien creado[/caption]

<h5>2.- Copia de archivos vía FTP</h5>

Vía FTP nos bajamos una copia de todos los archivos de nuestro site (de producción).

Cuando tengamos todos los archivos de nuestros site de producción los subimos via FTP subimos a nuestro recién creado sitio <em>staging</em> (en nuestro caso bajo la ruta <code>/public_html/staging</code>)

[caption id="attachment_3697" align="alignnone" width="1012"]<img class="wp-image-3697 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/upload-files-staging.png" alt="upload-files-staging" width="1012" height="894" /> Subida archivos via FTP al espacio asociado a nuestro subdominio[/caption]

<h5>3- Copiar la BD en otra BD</h5>

Nos conectamos a nuestro <a href="https://www.phpmyadmin.net/">phpMyAdmin</a> y hacemos una copia de nuestra BD en otra BD para nuestro sitio <em>staging</em>. En mi ejemplo copiamos la BD llamada <code>pixelove_wp369</code> en otra BD llamada <code>pixelove_wp360_staging</code>

[caption id="attachment_3698" align="alignnone" width="759"]<img class="wp-image-3698 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/copy-to-DB.png" alt="copy-to-DB" width="759" height="674" /> Copia de la BD a otra BD[/caption]

Cuando terminemos este proceso de copia veremos que tenemos las 2 BD creadas.

[caption id="attachment_3699" align="alignnone" width="360"]<img class="wp-image-3699 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/new-DB-staging.png" alt="new-DB-staging" width="360" height="715" /> Nueva BD datos (staging) creada[/caption]

<h5>4- Actualización de valores en la nueva BD</h5>

<blockquote>Nota: Las bases de datos del tipo <a href="https://www.mysql.com/">mySQL</a> se pueden gestionar mediante  <a href="https://www.phpmyadmin.net/">phpMyAdmin</a>. Con phpMyAdmin podemos gestionar la BD (modificar valores, añadir tablas, etc...) de una forma visual o a través de sentencias SQL <em>(que es como el lenguaje de programacion de las Bases de Datos)</em></blockquote>

Ejecutamos un SQL en la nueva BD (<code>pixelove_wp360_staging</code>) para que la nueva BD referencie a la URL adecuada <code>staging.pixelovers-test.com</code>

<pre class="lang:tsql decode:true">UPDATE wp_options SET option_value = REPLACE(option_value, 'ORIGINAL_URL', 'NEW_URL');
UPDATE wp_postmeta SET meta_value = REPLACE(meta_value, 'ORIGINAL_URL', 'NEW_URL');
UPDATE wp_posts SET guid = REPLACE(guid, 'ORIGINAL_URL', 'NEW_URL');
UPDATE wp_posts SET post_content = REPLACE(post_content, 'ORIGINAL_URL', 'NEW_URL');
</pre>

En nuestro caso seria:

<ul>
    <li><em>ORIGINAL_URL = pixelovers-test.com</em></li>
    <li><em>NEW_URL = staging.pixelovers-test.com</em></li>
</ul>

Así que tendríamos que ejecutar:

<pre class="lang:tsql decode:true">UPDATE wp_options SET option_value = REPLACE(option_value, 'pixelovers-test.com', 'staging.pixelovers-test.com');
UPDATE wp_postmeta SET meta_value = REPLACE(meta_value, 'pixelovers-test.com', 'staging.pixelovers-test.com');
UPDATE wp_posts SET guid = REPLACE(guid, 'pixelovers-test.com', 'staging.pixelovers-test.com');
UPDATE wp_posts SET post_content = REPLACE(post_content, 'pixelovers-test.com', 'staging.pixelovers-test.com');</pre>

[caption id="attachment_3704" align="alignnone" width="1308"]<img class="wp-image-3704 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/sql-execute.png" alt="sql-execute" width="1308" height="456" /> Ejecución de SQL para actualizar valores en nueva BD[/caption]

[caption id="attachment_3706" align="alignnone" width="1309"]<img class="wp-image-3706 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/execution-sql.png" alt="execution-sql" width="1309" height="341" /> Resultado de Ejecución de SQL[/caption]

<h5>4- Actualización de valores en <em>wp-config.php</em></h5>

Hacemos los cambios pertinentes en <em>wp-config.php</em> para que nuestra nueva instalación de Wordpress acceda a la BD recién creada con el usuario adecuado.

<a href="http://pixelovers.com/app/uploads/sites/7/2016/05/wp-config-2.png"><img class="alignnone size-full wp-image-3709" src="http://pixelovers.com/app/uploads/sites/7/2016/05/wp-config-2.png" alt="wp-config" width="657" height="368" /></a>

Puede que el usuario DB_USER (para acceder a la BD nueva) "heredado" del site original no tenga permisos a nuestra nueva BD, así que desde cPanel, nos aseguramos que el usuario que utilizamos para conectar a la BD tenga permisos para acceder a la nueva BD.

[caption id="attachment_3710" align="alignnone" width="873"]<img class="wp-image-3710 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/add-user-bd.png" alt="add-user-bd" width="873" height="536" /> Dándole permisos al usuario en wp_config para gestionar la nueva BD[/caption]

[caption id="attachment_3711" align="alignnone" width="861"]<img class="wp-image-3711 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/check-user-db.png" alt="check-user-db" width="861" height="174" /> Bases de Datos en nuestro sistema y usuarios con acceso[/caption]

<h5>5-  Y <em>voilá</em></h5>

Ya podemos acceder a nuestro sitio en nuestra URL

[caption id="attachment_3712" align="alignnone" width="369"]<img class="wp-image-3712 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/staging-blog.png" alt="staging-blog" width="369" height="521" /> Copia staging funcionando[/caption]

Ya tienes tu nueva copia idéntica a la de producción totalmente independiente. Tus datos de acceso (login al panel de administración) son los mismos que los del site original.

Ya eres libre de cambiar configuraciones, instalar nuevos plugins, editar archivos de tu <em>theme</em>, y hacer lo que quieras sin temor a romper nada de tu sitio en producción. :)

<h2>Crear una version de pruebas ( staging) de mi sitio web... pulsando un botón</h2>

¿Te parece MUY complicado todo esto y quieres simplificar el proceso de crear tu copia <em>staging</em>?

Pues hay algunos hosting que simplifican mucho el proceso de crear una copia staging de tu site:

<ol>
    <li>Pudiendo crear copias exactas de nuestro sitio en producción en cualquier momento y ofreciéndonos al final del proceso una URL donde hacer nuestras pruebas</li>
    <li>Dándonos la oportunidad de aprovechar estas pruebas y si los cambios realizados son correctos, nos permiten volcar nuestra versión de pruebas a nuestro sitio en producción</li>
</ol>

El <a href="http://siteground.es">hosting de SiteGround</a> es uno de estos sitios. Bajo la opción "Ensayos" en Herramientas de Wordpress tenemos el panel que nos permitirá crear rápidamente una versión staging de nuestro site.

[caption id="attachment_3730" align="alignnone" width="648"]<a href="http://pixelovers.com/app/uploads/sites/7/2016/05/ensayos-wp.png"><img class="wp-image-3730 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/ensayos-wp.png" alt="ensayos wp en siteground" width="648" height="238" /></a> ensayos wp en siteground[/caption]

Pulsando el botón <em><strong>Crear copia de pruebas</strong></em> se nos creará automaticamente nuestro sitio <em>staging</em> que será copia exacta del estado actual de nuestro sitio principal

[caption id="attachment_3732" align="alignnone" width="858"]<img class="wp-image-3732 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/crear-copia-pruebas-1.png" alt="crear copia de pruebas" width="858" height="565" /> crear copia de pruebas[/caption]

Cuando termine el proceso, tendremos acceso al panel de la copia de pruebas donde podremos hacer varias cosas:

<ul>
    <li>Ir al sitio de prueba</li>
    <li>Ir al panel de administraciòn WP del sitio de pruebas</li>
    <li>Volcar el contenido de este sitio de pruebas a nuestro sitio de producción</li>
    <li>Eliminar el sitio de pruebas</li>
    <li>Proteger con contraseña el sitio de pruebas</li>
</ul>

[caption id="attachment_3735" align="alignnone" width="1016"]<a href="http://pixelovers.com/app/uploads/sites/7/2016/05/copia-sitio-pruebas-panel.png"><img class="wp-image-3735 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/copia-sitio-pruebas-panel.png" alt="panel sitio de pruebas" width="1016" height="545" /></a> panel sitio de pruebas[/caption]

Si le damos al link "previsualización" accederemos fácilmente a nuestro nuevo sitio de pruebas:

[caption id="attachment_3734" align="alignnone" width="296"]<img class="wp-image-3734 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2016/05/staging1-296x300.png" alt="staging1" width="296" height="300" /> Sitio de pruebas "staging"[/caption]

Podemos gestionar los archivos de esta copia via FTP. A cada copia se le asigna un numero (1 para <em>staging1.pixelovers-test.com</em>) y se crea una carpeta con ese numero en la ruta <code>/staging</code>

[caption id="attachment_3742" align="alignnone" width="532"]<a href="http://pixelovers.com/app/uploads/sites/7/2016/05/staging-1.png"><img class="wp-image-3742 size-full" src="http://pixelovers.com/app/uploads/sites/7/2016/05/staging-1.png" alt="staging 1" width="532" height="364" /></a> staging 1[/caption]

¿Qué te ha parecido este artículo? ¿Te animas a montar tu sitio de pruebas? ¿Tienes ya algún sistema montado? ¿Cual es tu experiencia?

Esperamos vuestros comentarios