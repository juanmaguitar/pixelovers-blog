---
ID: 3811
post_title: >
  Crea gráficas sencillas con C3.js en 5
  minutos
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/crea-graficas-sencillas-c3-js-5-minutos/
published: true
post_date: 2017-03-08 13:22:05
---
<img class="alignnone size-large wp-image-3833" src="https://juanmaguitar.com/app/uploads/sites/7/2017/03/crear-graficas-c3-sencillas-1024x512.png" alt="" width="700" height="350" />

A la hora de mostrar gráficas de nuestros datos la librería más popular es <a href="https://d3js.org/">D3.js</a>. Esta librería es MUY versátil y con ella podremos hacer casi todas los <a href="https://github.com/d3/d3/wiki/Gallery">tipos de gráficas</a> que queramos.

Pero D3.js tiene también una curva de aprendizaje muy pronunciada. Para hacer una gráfica sencilla tienes que manejar de entrada muchos conceptos (y escribir mucho código). Para estos casos D3.js se presenta como una solución demasiado completa (y compleja)

Así que si lo que queremos es <strong>añadir una gráfica sencilla a nuestro proyecto de manera rápida</strong> tenemos una opción mejor: <a href="http://c3js.org/"><strong>C3.js</strong></a>.

<!--more-->

C3.js es una librería construida sobre D3.js que ofrece una API muy sencilla de utilizar y con la que podremos mostrar nuestras gráficas con pocas líneas de código

En mi opinión C3 es la mejor manera de empezar a trabajar con gráficas, dejando D3 como herramienta avanzada.
<h2><a id="user-content-qué-necesitamos-para-empezar-a-trabajar-con-c3" class="anchor" href="#qu%C3%A9-necesitamos-para-empezar-a-trabajar-con-c3"></a>¿Qué necesitamos para empezar a trabajar con C3?</h2>
Para utilizar C3.js en nuestro proyecto necesitamos cargar 3 cosas:
<ul>
 	<li>El archivo .js de D3</li>
 	<li>El archivo .js de C3</li>
 	<li>El archivo .css de C3</li>
</ul>
Los podemos descargar desde sus sitios oficiales (<a href="http://c3js.org/">C3</a>,<a href="http://d3js.org/">D3</a>), a nuestro proyecto y cargarlos en nuestro HTML desde su ubicación

También podemos instalar estos archivos con bower
<pre><code>bower install c3
</code></pre>
...y luego cargarlos desde <code>bower_components</code>

O los podemos cargar directamente desde un CDN
<pre class="lang:xhtml decode:true  ">&lt;!-- These belongs to the HTML file where you want C3 to work - put these lines into your &lt;head&gt; tag --&gt;
&lt;script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.4.11/d3.js"&gt;&lt;/script&gt;
&lt;script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/c3/0.4.11/c3.js"&gt;&lt;/script&gt;
&lt;link href="https://cdnjs.cloudflare.com/ajax/libs/c3/0.4.11/c3.css" rel="stylesheet" type="text/css"&gt;
</pre>
La última version a la hora de escribir este articulo y con la que están hechos los ejemplos es la v.0.4.11
<h2><a id="user-content-creando-nuestra-primera-gráfica-con-c3" class="anchor" href="#creando-nuestra-primera-gr%C3%A1fica-con-c3"></a>Creando nuestra primera gráfica con C3</h2>
Al llamar al método <code>generate</code> de C3.js, pasándole un objeto de configuración con propiedades como <code>bindto</code> y <code>data</code>, se generará la gráfica en el elemento especificado como selector en la propiedad <code>bindto</code> de este objeto

Es decir, teniendo un <code>&lt;div id="chart"&gt;&lt;/div&gt;</code> en el marcado, con este código
<pre class="lang:js decode:true">var chart = c3.generate({
    bindto: '#chart',
    data: {
      columns: [
        ['data1', 30, 200, 100, 400, 150, 250],
        ['data2', 50, 20, 10, 40, 15, 25]
      ]
    }
});</pre>
generamos esta grafica

<script async src="https://jsfiddle.net/juanma/wmvejjm1/embed/result,js,html,css/"></script>

Mola, ¿no? :)
<h2><a id="user-content-más-ejemplos-con-c3" class="anchor" href="#m%C3%A1s-ejemplos-con-c3"></a>Más ejemplos con C3</h2>
<h5>Donut</h5>
Para hacer otros tipos de gráficas podemos especificar la propiedad <code>type</code> dentro de <code>data</code>. Por ejemplo, con <code>type: 'donut'</code> y con los datos adecuados en <code>columns</code>
<pre class="lang:js decode:true ">const type = 'donut'
const title = '# Kittens Love #'

var chart = c3.generate({
    data: {
        columns: [
            ['Yoko', 50],
            ['Linda', 50],
        ],
        type
    },
    donut: { title }
});</pre>
podemos generar una gráfica como esta

<script async src="https://jsfiddle.net/juanma/Lbrjnfad/embed/result,js,html,css/"></script>
<h5>Gráfica combinada (lineas y barras)</h5>
Podemos combinar tipos de gráficas, añadir labels y especificar el formato de los datos en las "axis"
<pre class="lang:js decode:true">var chart = c3.generate({
    bindto: '#chart',
    data: {
      columns: [
        ['data1', 30, 200, 100, 400, 150, 250],
        ['data2', 50, 20, 10, 40, 15, 25]
      ],
      types: {
        data2: 'bar'
      }
    },
    axis: {
      y: {
        label: {
          text: 'Y Label',
          position: 'outer-middle'
        },
        tick: {
          format: d3.format("$,") // ADD
        }
      }
    }
});</pre>
<script async src="https://jsfiddle.net/juanma/brLdsw1p/embed/result,js,html,css/"></script>
<h5>Carga asíncrona de datos</h5>
Con el método <code>load</code> podemos cargar datos en la gráfica asíncronamente (por ejemplo como resultado de una llamada a una API). También podemos descargar datos de la gráfica con el método <code>unload</code>
<pre class="lang:js decode:true">let chart = c3.generate({
    bindto: '#chart',
    data: {
      columns: [ ['data1'], ['data2'] ],
    }
});

const load = document.getElementById('load')
const unLoad = document.getElementById('unload')

load.querySelector('button').addEventListener('click', () =&gt; {
	displayButtons()
  chart.load({
    columns: [
      ['data1', 300, 100, 250, 150, 300, 150 ],
      ['data2', 100, 200, 150, 50, 100, 250 ]
    ]
  });
})

unload.querySelector('button').addEventListener('click', () =&gt; {
	chart.unload('data1');
})

function displayButtons() {
	load.className = 'hidden'
  unload.className = ''
}</pre>
&nbsp;

<iframe width="100%" height="450" src="https://jsfiddle.net/juanma/22w5whoL/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
<h5>Streaming de datos</h5>
Con el método <code>flow</code> podemos añadir nuevos puntos a la gráfica y desplazar la grafica. Perfecto para representar datos en streaming
<pre class="lang:js decode:true ">
const MAX = 100
const LENGTH = 20

let data1 = ['data1']
let x = ['x']

let interval
let chart = c3.generate({
    bindto: '#chart',
    data: {
      x: 'x',
      columns: [ x, data1 ]
    },
    axis: {
     x: {
       type: 'timeseries',
       tick: { format: '%H:%M:%S' }
     }
    }
});

const oStart = document.getElementById('start')
const oStop = document.getElementById('stop')

oStart.querySelector('button').addEventListener('click', () => {
  displayButtons()
  interval = setInterval(() => {
    data1.push( getRandomNumber( MAX ) )
    x.push( +new Date() )
    if (data1.length < LENGTH) {
      chart.load({ 
        columns: [ x, data1 ]
      });
    }
    else {
      chart.flow({ 
        columns: [ 
          [ 'x',  +new Date() ],
          [ 'data1',  getRandomNumber( MAX ) ] 
        ]
      });
    }
    
  },1000)
})

oStop.querySelector('button').addEventListener('click', () => {
  clearInterval(interval)
})

function getRandomNumber( max ) {
  return Math.round( Math.random()*max )
}

function displayButtons() {
  oStart.className = 'hidden'
  oStop.className = ''
}
</pre>
&nbsp;

<iframe width="100%" height="450" src="//jsfiddle.net/juanma/18yk5zun/embedded/result,js,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

¿Qué te ha parecido este articulo? ¿Alguna otra librería de gráficos que nos quieras recomendar?

Esperamos vuestros comentarios