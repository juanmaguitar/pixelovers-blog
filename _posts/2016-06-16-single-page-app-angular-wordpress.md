---
ID: 3750
post_title: >
  Monta tu (Single Page) App con Angular y
  WordPress
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/single-page-app-angular-wordpress/
published: true
post_date: 2016-06-16 09:48:55
---
&nbsp;

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/1.png"><img class="aligncenter wp-image-3755 size-large" src="http://pixelovers.com/app/uploads/sites/7/2016/06/1-1024x768.png" alt="1" width="700" height="525" /></a>

<a href="https://es.wordpress.org/">Wordpress</a> es una herramienta super potente, y más aun desde que tenemos la posibilidad de <a href="http://v2.wp-api.org/">servir sus datos a traves de una API</a>. Esto nos abre un mundo de posibilidades como por ejemplo aprovechar la potencia de Wordpress como CMS (Content Management System) para la gestion de usuarios y creación de contenidos y utilizar estos datos desde una aplicación movil o web.

<a href="https://angularjs.org/">Angular.js </a>es uno de los frameworks Javascript de moda que nos permite crear aplicaciones web estructuradas que se comuniquen con el servidor a través de una API.

En este post vamos a explicar cómo utilizar nuestra instalación Wordpress para:

<ul>
    <li>Servir una aplicación web hecha con angular.js</li>
    <li>Gestionar nuestros usuarios y contenidos desde Wordpress</li>
    <li>Servir los contenidos de Wordpress a través de una API</li>
    <li>Mostrar los contenidos servidos por la API en nuestra app angular</li>
</ul>

Muchas cosas, eh? Pues empezamosssss... ya! ;)

<!--more-->

<h2>Preparando el terreno</h2>

Para crear esta app vamos a empezar creando una instalación nueva de Wordpress. Para ellos vamos a utilizar el <a href="https://www.siteground.es/">Hosting de SiteGround</a> para crear una nueva instalación de Wordpress en un subdominio rápidamente y empezar a montar nuestra app.

Nos vamos a cPanel y creamos un nuevo subdominio

<a href="http://pixelovers.com/?attachment_id=3762"><img class="alignnone wp-image-3762 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2016/06/subdominio-siteground-300x84.png" alt="subdominio-siteground" width="300" height="84" /></a>

Una vez creado comprobamos la ruta donde estarán los archivos de nuestra nueva instalación (<code>public_html/api-server</code>en nuestro caso)

<h2><a href="http://pixelovers.com/?attachment_id=3761"><img class="alignnone wp-image-3761 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2016/06/gestion-subdominio-300x94.png" alt="gestion-subdominio" width="300" height="94" /></a></h2>

Con esto nos vamos a las instalaciones automáticas y elegimos Wordpress

<a href="http://pixelovers.com/?attachment_id=3765"><img class="alignnone wp-image-3765 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2016/06/automatic-wordpress-300x131.png" alt="automatic-wordpress" width="300" height="131" /></a>

Lanzamos la instalación...

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/install-now.png"><img class="alignnone size-medium wp-image-3767" src="http://pixelovers.com/app/uploads/sites/7/2016/06/install-now-300x259.png" alt="install-now" width="300" height="259" /></a>

dejamos que haga su magia...

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/in-progress.png"><img class="alignnone size-medium wp-image-3769" src="http://pixelovers.com/app/uploads/sites/7/2016/06/in-progress-300x181.png" alt="in-progress" width="300" height="181" /></a>

Y ya está!! Cuando termine ya tendremos disponible nuestro sitio en el subdominio elegido (<code>http://api-server.pixelovers-test.com/</code> en nuestro caso)

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/site-on-line.png"><img class="alignnone size-medium wp-image-3771" src="http://pixelovers.com/app/uploads/sites/7/2016/06/site-on-line-300x198.png" alt="site-on-line" width="300" height="198" /></a>

<h2>Sirviendo una app angular desde Wordpress</h2>

Para servir nuestra app tenemos que crear un <a href="https://codex.wordpress.org/Child_Themes">child theme</a> y utilizarlo para servir nuestros archivos.

Para ello, nos conectamos via FTP a nuestro host y localizamos la carpeta <em>themes</em> de nuestra instalación Wordpress. Una vez localizada subimos una carpeta nueva (<code>theme-angular-app</code> en nuestro caso) con dos archivos: <code>index.php</code> y <code>style.css</code>

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/theme-angular-app.png"><img class="alignnone size-medium wp-image-3774" src="http://pixelovers.com/app/uploads/sites/7/2016/06/theme-angular-app-228x300.png" alt="theme-angular-app" width="228" height="300" /></a>

<pre class="lang:css decode:true " title="style.css">/*
 Theme Name:   Angular App Theme
 Theme URI:    http://api-server.pixelovers-test.com
 Description:  Angular App  child theme, based on twentysixteen
 Author:       JuanMa Garrido
 Author URI:   http://pixelovers.com
 Template:     twentysixteen
 Version:      1.0.0
*/</pre>

<pre class="lang:xhtml decode:true" title="index.php">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;title&gt;AngularJS Demo Theme&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;h1&gt;Hello from Wordpress!!&lt;/h1&gt;
&lt;/body&gt;
&lt;/html&gt;</pre>

Con estos archivos en el servidor, deberiamos ser capaces de seleccionar el theme <code>Angular App Theme</code> desde el panel de Administración de Wordpress.

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/angular-app-theme.png"><img class="alignnone size-medium wp-image-3777" src="http://pixelovers.com/app/uploads/sites/7/2016/06/angular-app-theme-300x152.png" alt="angular-app-theme" width="300" height="152" /></a>

Este nuevo theme servirá nuestro archivo index.php

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/hello-wordpress.png"><img class="alignnone size-medium wp-image-3778" src="http://pixelovers.com/app/uploads/sites/7/2016/06/hello-wordpress-300x145.png" alt="hello-wordpress" width="300" height="145" /></a>

Ahora vamos a servir un <code>index.php</code> que contenga una mini app de angular. Para ello añadimos un <code>functions.php</code> en el configuraremos nuestros wordpress para que desde el <code>index.php</code> podamos servir estas librerias (y las que necesitemos)

<pre class="lang:php decode:true" title="functions.php">&lt;?php
function my_scripts() {
 
 wp_enqueue_script(
 'angularjs','https://ajax.googleapis.com/ajax/libs/angularjs/1.5.6/angular.min.js'
 );
 wp_enqueue_script(
 'angularjs-route','https://ajax.googleapis.com/ajax/libs/angularjs/1.5.6/angular-route.js'
 );
}
add_action( 'wp_enqueue_scripts', 'my_scripts' );
</pre>

<pre class="lang:php decode:true " title="index.php">&lt;!DOCTYPE html&gt;
&lt;html ng-app&gt;
&lt;head&gt;
    &lt;base href="/jsonapi/"&gt;
    &lt;title&gt;AngularJS Demo Theme&lt;/title&gt;
    &lt;?php wp_head(); ?&gt;
&lt;/head&gt;
&lt;body&gt;

    &lt;header&gt;
        &lt;h1&gt;
            &lt;a href="&lt;?php echo site_url(); ?&gt;"&gt;AngularJS Demo Theme&lt;/a&gt;
        &lt;/h1&gt;
    &lt;/header&gt;

    &lt;div&gt;
        &lt;input type="text" ng-model="name"&gt;

        &lt;p&gt;Hello, {{name}}!&lt;/p&gt;
    &lt;/div&gt;

    &lt;footer&gt;
        &amp;copy; &lt;?php echo date( 'Y' ); ?&gt;
    &lt;/footer&gt;

&lt;/body&gt;
&lt;/html&gt;</pre>

Con esto ya podemos servir nuestra primera angular app desde wordpress

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/mini-angular-app.gif"><img class="alignnone size-medium wp-image-3783" src="http://pixelovers.com/app/uploads/sites/7/2016/06/mini-angular-app-300x181.gif" alt="mini-angular-app" width="300" height="181" /></a>

<h2>Mostrando datos de Wordpress en nuestra app angular</h2>

Para acceder a los datos de Wordpress desde nuestra app angular necesitamos servir estos datos a traves de una API. Para ello instalamos el plugin <a href="http://v2.wp-api.org/">WordPress REST API (Version 2).</a> Con este plugin activo podremos acceder a los datos de nuestro Wordpress desde su <a href="http://v2.wp-api.org/reference/">API</a>

Por ejemplo desde <code>/wp-json/wp/v2/posts</code> recibimos un JSON con la lista de los posts publicados

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/json-wordpress.png"><img class="alignnone size-medium wp-image-3785" src="http://pixelovers.com/app/uploads/sites/7/2016/06/json-wordpress-300x141.png" alt="json-wordpress" width="300" height="141" /></a>

Asi que con esto, ya podemos mejorar nuestra app angular para que acceda y muestra los datos de nuestro wordpress.

Creamos un <code>js/scripts.js</code> con el siguiente contenido

<pre class="lang:js decode:true" title="js/scripts.js">angular.module('app', ['ngRoute'])
.config(function($routeProvider, $locationProvider) {
    $locationProvider.html5Mode(true);

    $routeProvider
    .when('/', {
        templateUrl: myLocalized.partials + 'main.html',
        controller: 'Main'
    });
})
.controller('Main', function($scope, $http, $routeParams) {
    $http.get('/wp-json/wp/v2/posts/').success(function(res){
        $scope.posts = res;
    });
});
</pre>

Creamos un template en <code>partials/main.html</code> para mostrar el listado de posts

<pre class="lang:xhtml decode:true" title="partials/main.html">&lt;ul&gt;
   &lt;li ng-repeat="post in posts"&gt;
     &lt;a href="{{ post.id }}"&gt;
       &lt;h2&gt;{{ post.title.rendered }}&lt;/h2&gt;
     &lt;/a&gt;
   &lt;/li&gt;
&lt;/ul&gt;</pre>

Mejoramos el <code>functions.php</code> para que nuestro <code>index.php</code> incluya este nuevo archivo <code>js/scripts.js</code> y para crear un objeto global <code>myLocalized</code> (que podrá ser accedido desde angular ) donde guardaremos la ruta de los templates

<pre class="lang:php decode:true" title="functions.php">&lt;?php
function my_scripts() {

    wp_enqueue_script(
        'angularjs','https://ajax.googleapis.com/ajax/libs/angularjs/1.5.6/angular.min.js'
    );
    wp_enqueue_script(
        'angularjs-route','https://ajax.googleapis.com/ajax/libs/angularjs/1.5.6/angular-route.js'
    );

    wp_enqueue_script(
        'my-scripts',
        get_stylesheet_directory_uri() . '/js/scripts.js',
        array( 'angularjs', 'angularjs-route'),
        mt_rand()
    );

    wp_localize_script(
        'my-scripts',
        'myLocalized',
        array(
            'partials' =&gt; trailingslashit( get_stylesheet_directory_uri() ) . 'partials/'
            )
    );

}

add_action( 'wp_enqueue_scripts', 'my_scripts' );</pre>

Y voilá! Ya tenemos nuestra primera app angular mostrando datos de Wordpress (listado de posts)

<a href="http://pixelovers.com/app/uploads/sites/7/2016/06/angular-app-wordpress-api.png"><img class="alignnone size-medium wp-image-3790" src="http://pixelovers.com/app/uploads/sites/7/2016/06/angular-app-wordpress-api-300x251.png" alt="angular-app-wordpress-api" width="300" height="251" /></a>

A partir de aqui podemos:

<ul>
    <li>Añadir rutas a nuestra app angular para mostrar por ejemplo los detalles del post</li>
    <li>Añadir campos customizados (con el plugin <a href="https://www.advancedcustomfields.com/">Advanced Custom Fields</a>) y mostrarlos tambien en nuestra API (con el plugin <a href="https://wordpress.org/plugins/acf-to-rest-api/">ACF to REST API</a>)</li>
</ul>

<hr />

¿Qué os ha parecido este post? ¿Cual es vuestra experiencia trabajando con angular y Wordpress?

Esperamos vuestros comentarios