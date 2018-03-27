---
ID: 3174
post_title: Cómo utilizar los submodulos git
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/como-utilizar-los-submodulos-git/
published: true
post_date: 2015-04-30 03:00:50
---
<a href="http://pixelovers.com/app/uploads/sites/7/2015/04/submodules.jpg"><img class="alignnone size-full wp-image-3188" src="http://pixelovers.com/app/uploads/sites/7/2015/04/submodules.jpg" alt="submodules" width="592" height="137" /></a>

<strong>Los submodulos git son una manera de linkar un repositorio dentro de otro.</strong> Por ejemplo, si tu proyecto necesita utilizar un proyecto que está en Github, puedes utilizar un submodulo para enlazar este repositorio en vez de copiar y pegar todo el código dentro de tu proyecto

Para pixelovers por ejemplo, me interesa tener el proyecto <a href="http://ajk.fi/2013/wordpress-as-a-submodule/">Wordpress montado como submodulo</a>, asi tengo desacoplados los plugins, los themes y toda la parte "custom" de lo que es el "core" de wordpress. Esto me permite actualizar la version de Wordpress sin problemas y en mi repositorio tengo solo aquellos archivos que realmente son exclusivos de mi proyecto.

En este post vamos a explicar como:
<ul>
	<li>Cómo añadir un submodulo a tu proyecto</li>
	<li>Cómo clonar repositorios con submodulos</li>
	<li>Cómo actualizar submodulos git</li>
	<li>Cómo clonar repositorios con submodulos git que a su vez contienen otros submodulos git</li>
	<li>Cómo eliminar submodulos git</li>
</ul>
<!--more-->
<h2>Preparando el terreno</h2>
Desde tu cuenta de Github (si no tienes una <a href="https://github.com/join">¡a qué esperas!</a>) te tienes que crear un repositorio. Os recomiendo que os hagais un <code>fork</code> de uno que os tengo ya preparado para la ocasion: <code>https://github.com/pixelovers/working-with-submodules.git</code>

<a href="http://pixelovers.com/app/uploads/sites/7/2015/04/Captura-de-pantalla-2015-04-28-a-las-19.51.05.png"><img class="alignnone size-full wp-image-3184" src="http://pixelovers.com/app/uploads/sites/7/2015/04/Captura-de-pantalla-2015-04-28-a-las-19.51.05.png" alt="Captura de pantalla 2015-04-28 a las 19.51.05" width="383" height="90" /></a>

Asi una vez hecho el <code>fork</code> ya podeis trabajar desde vuestro repositorio y modificar (y hacer <code>push</code> lo que querais)

Despues del <code>fork</code> sustituye <code>#USERNAME#</code> por tu usuario de GitHub
<pre class="lang:sh decode:true">git clone https://github.com/#USERNAME#/working-with-submodules.git  project-with-submodules</pre>
<h2>Añadiendo un submodulo</h2>
En este proyecto recien creado (<strong>project-with-submodules</strong>) quiero añadir el codigo de otro repositorio llamado <strong>atomic-css-sass</strong> que contiene serie de clases ya definidas. Como <em>atomic-css-sass</em> es un proyecto que evoluciona por su lado me interesa añadirlo como submodulo al mio

Para ello utilizo <a href="http://git-scm.com/book/en/v2/Git-Tools-Submodules#Starting-with-Submodules"><code>git submodule add</code></a> de la siguiente manera
<pre class="lang:sh decode:true  ">$ cd project-with-submodules
$ git submodule add https://github.com/pixelovers/atomics-css-sass.git some-css
Cloning into 'some-css'...
remote: Counting objects: 25, done.
remote: Total 25 (delta 0), reused 0 (delta 0), pack-reused 25
Unpacking objects: 100% (25/25), done.
Checking connectivity... done.</pre>
Con esto registramos <code>atomics-css-sass</code> como submodulo de nuestro proyecto y clonamos los datos dentro del directorio <em>some-css</em>

El comando <code>git submodule status</code> nos dirá que el submodulo ha sido registrado y a qué commit está apuntando en la carpeta <em>some-css</em>
<pre class="lang:sh decode:true">$ git submodule status
 b53e87efc273b69a8c913bc345557ef93afad79e some-css (heads/master)</pre>
Ademas, para ver los cambios que han sido registrados en el repositorio padre (<em>project-with-submodules</em>) podemos
<pre class="lang:sh decode:true">$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD &lt;file&gt;..." to unstage)
    new file:   .gitmodules
    new file:   some-css</pre>
Esto nos indica que 2 archivos han sido modificados:
<ul>
	<li><code>.gitmodules</code> que contiene informacion sobre el repositorio del submodulo</li>
	<li><code>some-css</code> que es el propio submodulo</li>
</ul>
Git no trackea los archivos dentro del submodulo. Cuando estas en el repositorio padre ve el submodulo como un archivo.

Antes de continuar hacemos <code>commit</code> de nuestros cambios y hacemos <code>push</code> a nuestro repositorio remoto
<pre class="lang:sh decode:true">$ git commit -m 'Added some-css submodule'
[master 7bcc9a8] Added some-css submodule
 2 files changed, 4 insertions(+)
 create mode 100644 .gitmodules
 create mode 160000 some-css

$ git push
Counting objects: 4, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 448 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/pixelovers/working-with-submodules.git
   8f5f607..7bcc9a8  master -&gt; master</pre>
Una vez hecho esto, podemos fijarnos en nuestro repositorio remoto (Github) donde veremos un link al repositorio <code>atomics-css-sass</code> con el nombre <em>some_css</em>

<a href="http://pixelovers.com/app/uploads/sites/7/2015/04/Captura-de-pantalla-2015-04-28-a-las-20.16.53.png"><img class="alignnone size-full wp-image-3185" src="http://pixelovers.com/app/uploads/sites/7/2015/04/Captura-de-pantalla-2015-04-28-a-las-20.16.53.png" alt="Captura de pantalla 2015-04-28 a las 20.16.53" width="179" height="35" /></a>
<h2>Clonando un repositorio con submodulos</h2>
Vamos a clonar el repositorio con el que estamos trabajando en una carpeta diferente

Para ello hacemos (sustituye <code>#USERNAME#</code> por tu usuario de GitHub)
<pre class="lang:sh decode:true ">git clone https://github.com/#USERNAME#/working-with-submodules.git project-cloned-with-submodules</pre>
&nbsp;

Una vez clonado el proyecto, si nos vamos a la carpeta <em>project-cloned-with-submodules</em> veremos que está vacia.
<pre><code>$ cd project-cloned-with-submodules/some-css/
$ ls -la
total 0
</code></pre>
¿Que ha pasado? NOooooooo. <a href="https://www.youtube.com/watch?v=2OBZHB5I89A">Interneeeeeeerrrr</a> :)

Por defecto <code>git clone</code> no hace <code>pull</code> de los submodulos git a la vez que el repositorioi padre. Para "bajar" el codigo tendremos que:
<ul>
	<li>registrar el submodulo con <code>git submodule init</code></li>
	<li>hacer <code>pull</code> del codigo del submodulo con <code>git submodule update</code></li>
</ul>
<pre class="lang:sh decode:true">$ cd project-cloned-with-submodules/

$ git submodule init
Submodule 'some-css' (https://github.com/pixelovers/atomics-css-sass.git) registered for path 'some-css'

$ git submodule update
Cloning into 'some-css'...
remote: Counting objects: 25, done.
remote: Total 25 (delta 0), reused 0 (delta 0), pack-reused 25
Unpacking objects: 100% (25/25), done.
Checking connectivity... done.
Submodule path 'some-css': checked out 'b53e87efc273b69a8c913bc345557ef93afad79e</pre>
<h2>Actualizando un submodulo</h2>
Los submodulos son simplemente repositorios de git dentro de otros. Por tanto dentro del submodulo puedes utilizar todas las acciones git como <code>push</code>, <code>pull</code>, <code>status</code>, etc... Asi que si quieres asegurarte de que tu submodulo está actualizado a la última version de tu repositorio remoto pues hacer simplemente <code>git pull</code>
<pre class="lang:sh decode:true">$ git pull
You are not currently on a branch. Please specify which
branch you want to merge with. See git-pull(1) for details.
    git pull &lt;remote&gt; &lt;branch&gt;</pre>
Si obtenemos este error podemos hacer
<pre class="lang:sh decode:true">$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.</pre>
Y a partir de ahi ya funcionará bien
<pre class="lang:sh decode:true">$ git pull
Already up-to-date.</pre>
Si nuestro submodulo se baja algunos cambios al hacer el <code>pull</code> entonces el repositorio padre nos dirá que hay cambios pendientes de comitear. El submodulo apunta a un commit concreto, y si ese commit cambia el repositorio padre registra el cambio.

Si necesitamos que el submodulo esté en un commit concreto podemos utilizar <code>git reset</code>
<pre class="lang:sh decode:true">$ git reset --hard b53e87
HEAD is now at b53e87e intructions README.md</pre>
Una vez hecho podemos ir al repositorio padre y registrar este cambio
<pre class="lang:sh decode:true">cd ..
git commit -am 'Set submodule point to commit b53e87'</pre>
Cuando hagamos <code>push</code> de estos cambios al repositorio remoto el submodulo quedará asociado a este commit en particular.
<h2>Submodulos git que contienen otros submodulos git</h2>
Otra gran característica de los submodulos git es que pueden a su vez contener otro submodulos git

Por ejemplo, el repositorio <em>atomic-css-sass</em> contiene a su vez otro submodulo en la ruta <code>/src/scss/helpers</code>

En este punto, en hemos actualizado el repostorio <em>atomic-css-sass</em> en la carpeta <em>some_css</em> pero ninguno de sus submodulos han sido <em>pulled</em>

Si vamos al directorio <em>some_css</em> y hacemos <code>git submodule status</code>
<pre class="lang:sh decode:true">$ git submodule status
-5f76d83120eb49c2147a0f8ad930aff79c97e17d src/scss/helpers</pre>
Vemos que hay un submodulo para el repositorio <em>atomic-css-sass</em>. El signo <code>-</code> al principio de cada linea nos indica que el submodulo no ha sido descargado aun. Podriamos hacer <code>git init</code> y <code>git update</code> lo que clonaria todos los repositorios y los colocaria en su correspondiente lugar.

¿Pero tengo que hacer esto siempre que clone un repositorio con submodulos? ¿Que pasa si estos submodulos tienen a su vez submodulos? ¿Tengo que ir carpeta por carpeta con submodulo haciendo <code>init</code> y <code>update</code>?

Pues no :)

Podemos decirle a git que cuando clone un repositorio (<code>git clone</code>) con submodulos, automaticamente actualize todos los que encuentre (<code>--recursive</code>)

En nuestro ejemplo, si clonamos en otra carpeta seria
<pre class="lang:sh decode:true">git clone --recursive https://github.com/#USERNAME#/working-with-submodules.git project-cloned-with-submodules-well-done</pre>
<em>No olvides de sustituir #USERNAME# por tu nombre de usuario</em>
<h2>Eliminado submodulos git</h2>
Podemos decidir tambien que no queremos utilizar mas el submodulo porque hemos encontrado una manera mejor de manejar la dependencia o porque hay problemas con el submodulo y quieres borrarlo y empezar de nuevo.

Pero esto no es tan facil como hacer
<pre class="lang:sh decode:true">git rm -rf some_css</pre>
Si hacemos esto asi, git se quejará.

Para eliminar el modulo tenemos que:

1.- Eliminar las referencias al modulo en el archivo <em>.gitmodules</em> que está en la raiz del proyecto (si solo tenemos un submodulo podemos eliminar directamente este archivo)
<pre class="lang:sh decode:true  ">  [submodule "some-css"]
    path = some-css
    url = https://github.com/pixelovers/atomics-css-sass.git</pre>
Pero esto no es suficiente, hay un sitio más donde queda definido el submodulo.
<pre class="lang:sh decode:true">$ git submodule status
No submodule mapping found in .gitmodules for path 'some-css'</pre>
Los submodulos git tambien quedan registrados en el archivos <em>.git/config</em>
<pre class="lang:sh decode:true">[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
        precomposeunicode = true
[remote "origin"]
        url = https://github.com/pixelovers/working-with-submodules.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master
[submodule "some-css"]
        url = https://github.com/pixelovers/atomics-css-sass.git</pre>
2.- Asi que tambien tenemos que eliminar las lineas que referencian al submodulo que encontramos al final del archivo

3.- Y por ultimo, tenemos que eliminar la cache git del submodulo
<pre class="lang:sh decode:true">$ git rm --cached some-css
rm 'some-css'</pre>
Con esto ya tenemos el submodulo, completamente eliminado y ya podemos hacer <code>commit</code> y <code>push</code> para registrar los cambios
<pre class="lang:sh decode:true  ">$ git commit -m "submodule removed"
[master 61b4f31] submodule removed
 1 file changed, 1 deletion(-)
 delete mode 160000 some-css

$ git push</pre>
<h3>Enlaces y mas</h3>
<ul>
	<li><a href="http://git-scm.com/book/en/v2/Git-Tools-Submodules">http://git-scm.com/book/en/v2/Git-Tools-Submodules</a></li>
	<li><a href="http://davidwalsh.name/update-submodules-git">http://davidwalsh.name/update-submodules-git</a></li>
	<li><a href="https://medium.com/@porteneuve/mastering-git-submodules-34c65e940407">https://medium.com/@porteneuve/mastering-git-submodules-34c65e940407</a></li>
	<li><a href="https://chrisjean.com/git-submodules-adding-using-removing-and-updating/">https://chrisjean.com/git-submodules-adding-using-removing-and-updating/</a></li>
	<li><a href="http://blog.joncairns.com/2011/10/how-to-use-git-submodules/">http://blog.joncairns.com/2011/10/how-to-use-git-submodules/</a></li>
</ul>