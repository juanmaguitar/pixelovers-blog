---
ID: 3149
post_title: >
  Cómo empezar a automatizar tus tareas
  Grunt
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/empezar-automatizar-tareas-grunt/
published: true
post_date: 2015-04-28 09:29:49
---
<strong><a href="http://gruntjs.com/">Grunt</a></strong> es una herramienta que ser ha vuelto MUY popular en los ultimos tiempos ya que nos permite automatizar todo tipo de tareas en el cliente y como consecuencia mejorar nuestra productivadad en un 500%.

Estas automatizaciones se hacen imprescindibles cuando trabajamos con transcompiladores, o lenguajes que compilan a otros lenguajes (Coffeescript, SASS,...). Tambien si aplicamos metodologias TDD y queremos ser eficientes, necesitamos sistemas que nos permitan lanzar los tests de una manera rapida y sencilla.

Pues todo esto y mas cosas podemos hacer con Grunt.

<a href="http://pixelovers.com/app/uploads/sites/7/2015/04/features-grunt-big.png"><img class=" wp-image-3415  aligncenter" src="http://pixelovers.com/app/uploads/sites/7/2015/04/features-grunt-big-268x300.png" alt="features-grunt-big" width="383" height="452" /></a>

<!--more-->

<h2>¿Que es Grunt?</h2>

Esta herramienta fue lanzada en <a href="http://bocoup.com/weblog/introducing-grunt/">Marzo de 2012</a> por <a href="http://twitter.com/cowboy">Ben Allman</a>

Su autor la definió <a href="http://bocoup.com/weblog/introducing-grunt/">originalmente</a> asi:

<blockquote>Grunt is a task-based command line build tool for JavaScript projects.</blockquote>

Que vendria a ser algo asi como:

<blockquote>Es una herramienta de build para proyectos Javascript que se ejecuta en modo comando en la consola y cuyo funcionamiento se basa en la definicion de tareas</blockquote>

O simplificando:

<blockquote>Es un ejecutador de tareas</blockquote>

Con la particularidad de que las tareas grunt se definen en Javascript, y de que podemos lanzarlas en modo comando desde la consola

<h2>Primeros pasos</h2>

Lo mas destacable de Grunt es la gran cantidad de <a href="http://gruntjs.com/plugins">plugins</a> que tiene disponibles. Con ellos podremos crear tareas grunt para casi todo lo que necesitemos (minificar, chequeo de codigo, testing, concatenacion de archivos, uglify, transcompilacion, deploy...)

Tanto Grunt como sus plugins son paquetes que se instalan via <a href="https://npmjs.org/">npm</a>, el gestor de paquetes de <a href="http://nodejs.org/">Node.js</a>. NPM viene de "serie" con Node.js, si no los tienes instalados aún, puedes intalarlos facilmente desde <a href="https://nodejs.org/download/">aqui</a>

<strong>Lo primero</strong> que hay que hacer para poder utilizar este <em>ejecutador</em> de tareas es instalar globalmente el paquete llamado <a href="http://gruntjs.com/using-the-cli">Grunt's CLI</a> (Command Line Interface)

<pre><code>npm install -g grunt-cli
</code></pre>

Con esto ya podemos empezar a utilizarlo tanto en proyectos nuevos como en proyectos existentes.

<h2>Archivos principales</h2>

<h3><code>package.json</code></h3>

El "Grunt runner" y todos los plugins que utilizemos en el proyecto se definen como dependencias en este archivo

<pre><code>{
  "name": "my-project-name",
  "version": "0.1.0",
  "devDependencies": {
    "grunt": "~0.4.5",
    "grunt-contrib-jshint": "~0.10.0",
    "grunt-contrib-nodeunit": "~0.4.1",
    "grunt-contrib-uglify": "~0.5.0"
  }
}
</code></pre>

<h3><code>Gruntfile.js</code></h3>

Las tareas grunt se definen/configuran y los plugins se cargan en este archivo javascript. Fijate que el formato es el de un <a href="http://pixelovers.com/ventajas-utilizar-nodejs-1953900/">modulo Node.js</a>

<pre><code>module.exports = function(grunt) {
  grunt.initConfig({
    jshint: {
      files: ['Gruntfile.js', 'src/**/*.js', 'test/**/*.js'],
      options: {
        globals: {
          jQuery: true
        }
      }
    },
    watch: {
      files: ['&lt;%= jshint.files %&gt;'],
      tasks: ['jshint']
    }
  });
  grunt.loadNpmTasks('grunt-contrib-jshint');
  grunt.loadNpmTasks('grunt-contrib-watch');
  grunt.registerTask('default', ['jshint']);
};
</code></pre>

<h2>Empezar a utilizar tareas Grunt</h2>

<h3> En Proyectos existentes</h3>

Estos proyectos existentes ya dispondremos de un <code>package.json</code> donde estarán definidas todas las dependencias, asi que para instalarlas simplemente tendremoa que hacer

<pre><code>npm install
</code></pre>

Por tanto, clonar un proyecto <code>git</code> en nuestro ordenador, instalar las dependencias (grunt inclusive) y lanzar las tareas definidas vendria a ser algo asi:

<pre><code>$ git --version
$ node -v
$ npm -v
$ npm install -g grunt-cli
$ git clone https://github.com/juanmaguitar/grunt-workshop.git
$ cd grunt-workshop
$ npm install
$ grunt --version
$ grunt -h
$ grunt tasks
$ grunt compass
$ grunt shower
$ grunt serve
</code></pre>

<iframe width="700" height="380" src="http://showterm.io/5dbd18bd9b0a2c10caf7c"></iframe>

<h3> En Proyectos nuevos</h3>

En proyectos nuevos tenemos que instalar tanto grunt como los plugins que queramos y añadirlos como dependencias del proyecto (en <code>package.json</code>). Podemos hacer todo esto de golpe con:

<pre><code>npm install --save-dev grunt grunt-contrib-jshint
</code></pre>

Fijate que despues de ejecutar este comando tendremos una carpeta <code>node_modules</code> con los modulos instalados y las dependencias añadidas en el <code>package.json</code>

Por ejemplo, crear un proyecto nuevo (con su <code>package.json</code> y su <code>Gruntfile.js</code>), instalar las correspondientes dependencias, definir nuestra primera tarea y lanzarla, vendria a ser algo asi:

<pre><code>$ mkdir project
$ cd project/
$ mkdir src
$ npm init
$ npm install --save-dev grunt
$ vi Gruntfile.js
    module.exports = function(grunt) {
        grunt.registerTask('foo', function() {
               grunt.log.writeln('foo is running...');
        });
    };
$ grunt foo
</code></pre>

<iframe width="700" height="380" src="http://showterm.io/a177bf1bdcc8033709a69"></iframe>