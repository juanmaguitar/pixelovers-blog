---
ID: 3248
post_title: >
  Vagrant, o cómo manejar máquinas
  virtuales de forma sencilla
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/utiliza-vagrant-y-haz-portable-tu-entorno-de-desarrollo/
published: true
post_date: 2015-05-08 13:27:47
---
<a href="https://www.vagrantup.com/"><img class="ma-l alignnone size-full wp-image-3254" src="http://pixelovers.com/app/uploads/sites/7/2015/05/vagrant-logo.png" alt="vagrant-logo" width="600" /></a>

<a href="https://www.vagrantup.com/">Vagrant</a> ha sido una de mis mayores revelaciones técnicas de los últimos años. Con <a href="http://docs.vagrantup.com/v2/why-vagrant/">Vagrant</a> se soluciona (de forma definitiva diría yo) uno de los problemas más grandes que hemos tenido siempre los desarrolladores: <em>preparar/compartir el entorno de trabajo en el que estamos trabajando un proyecto.</em>

Incorporando Vagrant a nuestro flujo de trabajo podemos solucionar las inconsistencias entre entornos (cosas que funcionan en local y que se rompen en producción) ya que podemos emular en una <em>box</em> vagrant las mismas características que tenemos en producción.

Y una configurado, cualquier persona, será capaz de descargar y lanzar ese entorno desde cualquier maquina en unos instantes.

<blockquote>Say goodbye to "works on my machine" bugs.</blockquote>

<!--more-->

<strong>Vagrant nos proporciona una manera sencilla de configurar, lanzar y compartir entornos de trabajo construidos sobre maquinas virtuales.</strong>

<blockquote>Vagrant is a developer friendly interface for VirtualBox</blockquote>

<em>Asi que en muchos casos no tendremos que perder tiempo preparando nuestro entorno de trabajo sino que podemos utilizar uno de los ya existentes (e incluso añadirlo a nuestro proyecto)</em>

<h2>¿Qué necesito para poder utilizar Vagrant?</h2>

Para poder utilizar Vagrant necesitamos tener instaladas 2 cosas :

<ul>
    <li><strong><a href="https://www.virtualbox.org/wiki/Downloads">Virtual Box</a></strong>: El <em>provider</em> más popular (sobre todo por que es gratuito)</li>
    <li><strong><a href="https://www.vagrantup.com/downloads.html">Vagrant</a></strong>: Con esto tendremos disponibles los comandos con los que podremos lanzar, parar y eliminar las maquinas virtuales de VirtualBox.</li>
</ul>

<h2>Creando mi primer proyecto vagrant</h2>

Para configurar una maquina vagrant utilizamos un archivo llamado <code>Vagrantfile</code> cuya misión es:

<ul>
    <li><em>Fijar el directorio raíz</em> de tu proyecto</li>
    <li><em>Describir el tipo de maquina y los recursos</em> que necesitas para tu maquina virtual. También puedes definir aquí qué software instalar y de qué manera.</li>
</ul>

Con vagrant instalado tenemos disponible el comando <code>vagrant init</code> que nos inicializa un proyecto vagrant creando un <code>Vagrantfile</code> donde lo hayamos lanzado

<pre class="lang:sh decode:true ">$ vagrant init
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.</pre>

Este <code>Vagrantfile</code> es un modelo que está lleno de ejemplos y comentarios asi que lo podemos utilizar para investigar cómo funciona este archivo. Quitando la "paja" podemos dejar un <code>Vagrantfile</code> super-sencillo asi

<pre class="lang:ruby decode:true" title="Vagrantfile">VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise32"
end</pre>

Con cada <code>Vagrantfile</code> definimos lo que se llama una <code>box</code> (o proyecto vagrant) que es un conjunto de SO y aplicaciones preparadas ya para ser utilizadas

En <a href="http://www.vagrantbox.es/">vagrantbox.es</a> tienes una lista bastante amplia de <em>boxes</em> que puedes empezar a utilizar desde ya

<h2>Lanzando <em>boxes</em> Vagrant</h2>

La manera más rápida de empezar con Vagrant es descargar un <code>Vagrantfile</code> de alguna de las boxes ya existentes (y públicas)

<pre class="lang:sh decode:true">mkdir test-first-vagrant &amp;&amp; cd test-first-vagrant
vagrant init hashicorp/precise32</pre>

Con este comando nos descargamos el <code>Vagrantfile</code> y para lanzarla tenemos que hacer

<pre class="lang:sh decode:true ">vagrant up</pre>

Una vez "levantada" sólo queda conectarnos por <code>ssh</code> con

<pre class="lang:sh decode:true">vagrant ssh</pre>

Y ya estas dentro de la maquina virtual (que en este ejemplo es una maquina linux Ubuntu 12.04 LTS 32-bit). Ya puedes trabajar y probar lo que quieras como si estuvieras en una maquina Linux

Si quieres probar una <em>box</em> diferente puedes mirar en <a href="http://www.vagrantbox.es/">vagrantbox.es</a> la que te interese y añadirla haciendo

<pre class="lang:sh decode:true">mkdir test-box-vagrant &amp;&amp; cd test-box-vagrant
vagrant box add my_centos_lamp_stack http://devopera.com/node/63/download/centos6/doco6-lamp-vagrant.box
vagrant box init my_centos_lamp_stack</pre>

Con esto ya podemos hacer

<pre class="lang:sh decode:true  ">vagrant up &amp;&amp; vagrant ssh</pre>

para levantar la maquina y conectarnos a ella

<h2>¿Cómo funciona Vagrant?</h2>

Para explicarlo utilizaremos este gráfico de la gente de <a href="http://www.digitalforreallife.com/2012/11/boosting-teamwork-with-vagrant/">digitalforreallife.com</a>

<a href="http://pixelovers.com/app/uploads/sites/7/2015/05/django.png"><img class="ma-l alignnone size-full wp-image-3256" src="http://pixelovers.com/app/uploads/sites/7/2015/05/django.png" alt="django" width="600" /></a>

<ul>
    <li>Con Vagrant, interactuamos a través de unos sencillos comandos. El comando principal es <code>vagrant up</code> (1) que <em>arranca la maquina virtual</em> (el equivalente a pulsar el botón de encendido de cualquier computadora)</li>
    <li>Tambien tenemos el archivo <code>Vagrantfile</code> (2) que contiene las <em>directivas con las que especificamos las características de la maquina virtual</em> (virtual machine, VM) que estamos lanzando.</li>
    <li>Una vez lanzado <code>vagrant up</code>, Vagrant hablará con VirtualBox (2) y le indicará qué VM (3) tiene que arrancar (previa descarga si es necesario)</li>
    <li>Vagrant tambien hablará con los <em>provisioners</em> (4) que son los encargados de aprovisionar la VM, es decir, de instalar y configurar el software requerido para nuestro proyecto (5)</li>
    <li>Una vez que la maquina ha sido creada, arrancada y aprovisionada, <em>podemos conectar con ella via SSH</em> (6), de la misma manera que conectariamos con cualquier servidor remoto (excepto que en este caso el servidor está en una VM local dentro de nuestra maquina)</li>
</ul>

<h2>Resumiendo</h2>

<h3>Comandos básicos de Vagrant</h3>

<ul>
    <li><code>$ vagrant ssh</code> Conexion SSH a la maquina virtual (virtual machine, VM)</li>
    <li><code>$ vagrant up</code> Arranca/reanuda la VM</li>
    <li><code>$ vagrant halt</code> Suspende la VM. Podemos reanudarla de nuevo con <code>vagrant up</code></li>
    <li><code>$ vagrant destroy</code> Elimina la VM. La podremos arrancar/crear otra vez con <code>vagrant up</code></li>
    <li><code>$ vagrant provision</code> Reconfigura (reaprovisiona) la VM después de algún cambio en el código fuente.</li>
    <li><code>$ vagrant reload</code> Recarga (relanza) la VM (útil si hemos hecho cambios en la red o las carpetas compartidas).</li>
</ul>

<h3>Terminología Vagrant</h3>

<h4><em>Boxes</em></h4>

Una <em>box</em> es un paquete que contiene un sistema operativo para un provider específico (<em>Virtual Box</em> normalmente). Vagrant replicará esta imagen básica en tu maquina virtual. En el <code>Vagrantfile</code> especificamos que <em>box</em> base queremos utilizar. Esta <em>box</em> será descargada e instalada cuando la utilicemos por primera vez

<h3><em>Host</em> / <em>Guest</em></h3>

La maquina/SO <em>Host</em> es la maquina desde la que iniciamos Vagrant.
La maquina/SO <em>Guest</em> es la maquina virtual que arrancados desde el <em>Host</em>.

<h3><a href="http://docs.vagrantup.com/v2/providers/"><em>Provider</em></a></h3>

Vendria a ser el <em>target</em> de nuestra instalación. La maquina donde vamos a volcar toda nuestra configuración. En el 99% de los casos será una maquina virtual con VirtualBox aunque vagrant está preparado para utilizar <a href="https://www.digitalocean.com/community/tutorials/how-to-use-digitalocean-as-your-provider-in-vagrant-on-an-ubuntu-12-10-vps">otros providers</a>

<h3><a href="http://docs.vagrantup.com/v2/plugins/provisioners.html"><em>Provisioners</em></a></h3>

Son los métodos que utilizamos para instalar automáticamente software, modificar configuraciones y demas en la maquina virtual cuando la lanzamos.
El método más sencillo es utilizar un <a href="https://github.com/pixelovers/node-frontend-vagrant/tree/master/vagrant"><em>script shell</em></a> como provisioner. Otros sistemas de provisioning que podemos utilizar son <a href="http://docs.vagrantup.com/v2/provisioning/ansible.html">Ansible</a>, <a href="http://jesuslc.com/2014/05/07/primeros-pasos-con-chef-solo-y-vagrant/">Chef</a> o <a href="http://jarroba.com/como-crear-entornos-de-desarrollo-con-vagrant-y-puppet/">Puppet</a>

<h2>Enlaces y más</h2>

<ul>
    <li><a href="https://www.vagrantup.com/">https://www.vagrantup.com/</a></li>
    <li><a href="http://www.vagrantbox.es/">http://www.vagrantbox.es/</a></li>
    <li><a href="http://www.digitalforreallife.com/2012/11/boosting-teamwork-with-vagrant/">http://www.digitalforreallife.com/2012/11/boosting-teamwork-with-vagrant/</a></li>
</ul>