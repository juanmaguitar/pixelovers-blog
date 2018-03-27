---
ID: 2493
post_title: >
  Git y GitHub, el sistema de control de
  versiones de moda y su hosting gratuito
author: JuanMa Garrido
post_excerpt: |
  <p>
  Las caracteristicas principales de Git son:
  </p>
  <ul>
  <li>MUY rapido y fácil
  </li>
  <li>Es un sistema distribuido de control de versiones, es decir
  que no requiere de un repositorio central (como por ejemplo
  SVN).&nbsp;
  </li>
  <li>Cada copia (clone) que hagamos en nuestra maquina
  (repositorio local completo) es autosuficiente (commits offline).
  </li>
  <li>Está optimizado para el trabajo con ramas (branches)
  </li>
  </ul>
  <h2>
  ¿Qué es GitHub?
  </h2>
  <p>
  Por otro lado tenemos&nbsp;<strong><a href="https://github.com/"
  target="_blank">GitHub</a></strong> que es el hosting más grande
  (y más popular) que hay en la red de repositorios Git (cerca de 1
  millon de respositorios públicos).
  </p>
  <p>
  <img style="border-style: initial; border-color: initial;" title=
  "gitHub, Hosting de repositorios Git" src=
  "http://stc.obolog.net/photos/4e4f/4e4fd3962a0cas4583.jpg" alt=
  GitHub es el servicio de hospedaje de repositorios Git más popular - 
  align="right"/>
  </p>
  <p>
  Ofrece hosting&nbsp;gratuito para proyectos públicos y hosting de
  pago para proyectos privados.
  </p>
  <p>
  Algunos <a href="https://github.com/popular/forked" target=
  "_blank">proyectos públicos interesantes</a> que puedes encontrar
  en GitHub son&nbsp;<a href="https://github.com/rails/rails"
  target="_blank">Ruby on Rails</a>,&nbsp;<a href=
  "https://github.com/joyent/node" target=
  "_blank">Node.js</a>,&nbsp;<a href=
  "https://github.com/jquery/jquery" target="_blank">jQuery</a>,
  <a href="https://github.com/jquery/jquery-ui" target=
  "_blank">jQuery UI</a>,&nbsp;<a href=
  "https://github.com/diaspora/diaspora" target=
  "_blank">Diaspora</a>,&nbsp;<a href=
  "https://github.com/django/django" target=
  "_blank">Django</a>&nbsp;y&nbsp;<a href=
  "https://github.com/cakephp/cakephp" target="_blank">Cake
  PHP</a>&nbsp;
  </p>
  <h2>
  Primeros pasos: Haciendo "Clone" de un Proyecto
  </h2>
  <p>
  El principal motivo por el que habrás oido hablar de Git o de
  GitHub es por que algun proyecto que te interese estará alojado
  en GitHub, y quieres bajartelo y trabajar con él en local.&nbsp;
  </p>
  <p>
  Para hacer esto, lo primero que tendremos que hacer es instalar
  Git en nuestra maquina y configurarlo para que se entienda con
  GitHub (nuestro repositorio remoto)
  </p>
  <ul>
  <li>Bajamos e instalamos la <a href="http://git-scm.com/"
  target="_blank">última version de Git</a>
  </li>
  <li>Generamos una clave SSH y la configuramos en GitHub
  </li>
  <li>Configuramos nuestra info para que quede reflejada en
  nuestros commits
  </li>
  </ul>
  <div>
  En la documentacion de GitHub hay unas guias para hacer todo esto
  en <a href="http://help.github.com/mac-set-up-git/" target=
  _blank">Mac</a>, <a href="http://help.github.com/win-set-up-git
  target="_blank">Windows</a> y <a href=
  "http://help.github.com/linux-set-up-git" target=
  "_blank">Linux</a>
  </div>
  <div>
  &nbsp;
  </div>
  <div>
  Una vez hecho esto ya podemos hacer "clone" de un proyecto.&nbsp;
  </div>
  <pre style=
  "margin-top: 20px; background-color: #efefef; padding: 1em 0.5em; font-family: monospace;">
  
  $ git clone https://github.com/octocat/Spoon-Knife.git
  Cloning into Spoon-Knife...
  remote: Counting objects: 24, done.
  remote: Compressing objects: 100% (21/21), done.
  remote: Total 24 (delta 7), reused 17 (delta 1)
  Unpacking objects: 100% (24/24), done.
  </pre>
  <p>
  Otra cosa que podemos hacer es lo que se llama hacer
  <strong>"Fork"</strong> de un proyecto que consiste en crear otra
  copia remota a partir de la cual trabajar sin afectar al
  repositorio original. De esta forma puedes crear un proyecto
  nuevo basado en otro ya existente o trabajar en una nueva feature
  de un proyecto.
  </p>
  <p>
  <img title="" src=
  "http://help.github.com/images/bootcamp/bootcamp_3_fork.jpg" alt=
  " TAGS:" align="center"/>
  </p>
  <p>
  Una vez hecho el Fork, tendremos que hacer clone de nuestra copia
  particular
  </p>
  <pre style=
  "margin-top: 20px; background-color: #efefef; padding: 1em 0.5em; font-family: monospace;">
  
  $ git clone git@github.com:username/Spoon-Knife.git
  </pre>
  <h2>
  Enlaces y más
  </h2>
  <ul>
  <li>
  <a href="http://progit.org/book/" target="_blank">ProGit
  Book</a>
  </li>
  <li>
  <a href="http://gitimmersion.com/" target="_blank">Git
  Immersion</a>
  </li>
  <li>
  <a href="http://git-scm.com/documentation" target=
  "_blank">Documentacion Oficial de Git</a>
  </li>
  <li>
  <a href="http://help.github.com/git-cheat-sheets/" target=
  "_blank">CheatSheets de Git</a>
  </li>
  <li>
  <a href=
  http://www.genbetadev.com/sistemas-de-control-de-versiones/conociendo-github-el-servicio-donde-alojar-tus-repositorios-git-como-el-nuestro
  target="_blank">Conociendo GitHub</a>
  </li>
  <li>
  <a href="http://help.github.com/" target="_blank">Documentacion
  oficial de GitHub</a>
  </li>
  </ul>
  <p>
  Y tu... ¿Que opinas de Git? ¿Y de GitHub? ¿Lo conocias? ¿Cual es
  tu experiencia con él? ¿Y respecto a otros sistemas de control de
  versiones como Subversion?
  </p>
  <p>
  Esperamos vuestros comentarios...
  </p>
layout: post
permalink: >
  https://pixelovers.com/git-y-github-sistema-control-versiones-moda-hosting-gratuito-1262077/
published: true
post_date: 2011-08-20 12:50:00
---
<a href="http://pixelovers.com/app/uploads/sites/7/2011/08/Github2.png"><img class="alignnone size-full wp-image-3428" src="http://pixelovers.com/app/uploads/sites/7/2011/08/Github2.png" alt="Github2" width="500" height="236" /></a>

Git y GitHub son dos conceptos que suenan mucho en el mundo de los desarrolladores. En este post os vamos a explicar qué es cada cosa, y cómo empezar a trabajar con ellos.

<h2>¿Qué es Git?</h2>

<strong><a href="http://git-scm.com/" target="_blank">Git</a></strong> es un <a href="http://es.wikipedia.org/wiki/Control_de_versiones" target="_blank">sistema de control de versiones</a> distribuido, gratuito y de código abierto que se ha hecho muy popular en los ultimos tiempos.

<a href="http://pixelovers.com/app/uploads/sites/7/2011/08/Git.png"><img class="alignnone wp-image-3425 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2011/08/Git-300x125.png" alt="Git" width="300" height="125" /></a>

Fue diseñado por <a href="http://es.wikipedia.org/wiki/Linus_Torvalds" target="_blank">Linus Torvalds</a> (creador de Linux) y se ha hecho popular sobre todo por ser el sistema utilizado para el control de versiones del kernel de Linux.

<!--more-->Algunos proyectos que se estan desarrollando a traves de Git son el propio <a href="http://git.kernel.org/?p=git/git.git;a=summary" target="_blank">Git</a>, <a href="http://git.kernel.org/?p=linux/kernel/git/torvalds/linux-2.6.git;a=summary" target="_blank">Linux Kernel</a>, <a href="http://perl5.git.perl.org/perl.git" target="_blank">Perl</a>, <a href="http://git.eclipse.org/" target="_blank">Eclipse</a>, <a href="http://git.gnome.org/cgit/" target="_blank">Gnome</a>, <a href="http://gitweb.kde.org/" target="_blank">KDE</a> y <a href="http://android.git.kernel.org/" target="_blank">Android</a>

Las caracteristicas principales de Git son:

<ul>
    <li>MUY rapido y fácil</li>
    <li>Es un sistema distribuido de control de versiones, es decir que no requiere de un repositorio central (como por ejemplo SVN).</li>
    <li>Cada copia (clone) que hagamos en nuestra maquina (repositorio local completo) es autosuficiente (commits offline).</li>
    <li>Está optimizado para el trabajo con ramas (branches)</li>
</ul>

<h2>¿Qué es GitHub?</h2>

Por otro lado tenemos <strong><a href="https://github.com/" target="_blank">GitHub</a></strong> que es el hosting más grande (y más popular) que hay en la red de repositorios remotos Git (cerca de 1 millon de respositorios públicos).

<a href="http://pixelovers.com/app/uploads/sites/7/2011/08/GitHub.jpg"><img class="alignnone wp-image-3426 size-medium" src="http://pixelovers.com/app/uploads/sites/7/2011/08/GitHub-300x116.jpg" alt="GitHub" width="300" height="116" /></a>

Ofrece hosting gratuito para proyectos públicos y hosting de pago para proyectos privados.

Algunos <a href="https://github.com/popular/forked" target="_blank">proyectos públicos interesantes</a> que puedes encontrar en GitHub son <a href="https://github.com/rails/rails" target="_blank">Ruby on Rails</a>, <a href="https://github.com/joyent/node" target="_blank">Node.js</a>, <a href="https://github.com/jquery/jquery" target="_blank">jQuery</a>, <a href="https://github.com/jquery/jquery-ui" target="_blank">jQuery UI</a>, <a href="https://github.com/diaspora/diaspora" target="_blank">Diaspora</a>, <a href="https://github.com/django/django" target="_blank">Django</a> y <a href="https://github.com/cakephp/cakephp" target="_blank">Cake PHP</a>

<h2>Primeros pasos: Haciendo "Clone" de un Proyecto</h2>

El principal motivo por el que habrás oido hablar de Git o de GitHub es por que algun proyecto que te interese estará alojado en GitHub, y quieres bajartelo y trabajar con él en local.

Para hacer esto, lo primero que tendremos que hacer es instalar Git en nuestra maquina y configurarlo para que se entienda con GitHub (nuestro repositorio remoto)

<ul>
    <li>Bajamos e instalamos la <a href="http://git-scm.com/" target="_blank">última version de Git</a></li>
    <li>Generamos una clave SSH y la configuramos en GitHub</li>
    <li>Configuramos nuestra info para que quede reflejada en nuestros commits</li>
</ul>

<div>En la documentacion de GitHub hay unas guias para hacer todo esto en <a href="http://help.github.com/mac-set-up-git/" target="_blank">Mac</a>, <a href="http://help.github.com/win-set-up-git" target="_blank">Windows</a> y <a href="http://help.github.com/linux-set-up-git" target="_blank">Linux</a></div>

<div></div>

<div>Una vez hecho esto ya podemos hacer "clone" de un proyecto.</div>

<pre style="margin-top: 20px; background-color: #efefef; padding: 1em 0.5em; font-family: monospace;" class="">$ git clone https://github.com/octocat/Spoon-Knife.git
Cloning into Spoon-Knife...
remote: Counting objects: 24, done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 24 (delta 7), reused 17 (delta 1)
Unpacking objects: 100% (24/24), done.
</pre>

Otra cosa que podemos hacer es lo que se llama hacer <strong>"Fork"</strong> de un proyecto que consiste en crear otra copia remota a partir de la cual trabajar sin afectar al repositorio original. De esta forma puedes crear un proyecto nuevo basado en otro ya existente o trabajar en una nueva feature de un proyecto.

<a href="http://pixelovers.com/app/uploads/sites/7/2011/08/fork_button.jpg"><img class="alignnone size-medium wp-image-2822" src="http://pixelovers.com/app/uploads/sites/7/2011/08/fork_button-300x44.jpg" alt="fork_button" width="300" height="44" /></a>

Una vez hecho el Fork, tendremos que hacer clone de nuestra copia particular

<pre style="margin-top: 20px; background-color: #efefef; padding: 1em 0.5em; font-family: monospace;">$ git clone git@github.com:username/Spoon-Knife.git
</pre>

<h2>Enlaces y más</h2>

<ul>
    <li><a href="http://progit.org/book/" target="_blank">ProGit Book</a></li>
    <li><a href="http://gitimmersion.com/" target="_blank">Git Immersion</a></li>
    <li><a href="http://git-scm.com/documentation" target="_blank">Documentacion Oficial de Git</a></li>
    <li><a href="http://help.github.com/git-cheat-sheets/" target="_blank">CheatSheets de Git</a></li>
    <li><a href="http://www.genbetadev.com/sistemas-de-control-de-versiones/conociendo-github-el-servicio-donde-alojar-tus-repositorios-git-como-el-nuestro" target="_blank">Conociendo GitHub</a></li>
    <li><a href="http://help.github.com/" target="_blank">Documentacion oficial de GitHub</a></li>
</ul>

Y tu... ¿Que opinas de Git? ¿Y de GitHub? ¿Lo conocias? ¿Cual es tu experiencia con él? ¿Y respecto a otros sistemas de control de versiones como Subversion?

Esperamos vuestros comentarios...