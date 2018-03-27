---
ID: 3551
post_title: >
  Cómo ordenar aleatoriamente y agrupar
  (elegantemente) un array de elementos
author: JuanMa Garrido
post_excerpt: ""
layout: post
permalink: >
  https://pixelovers.com/como-crear-parejas-aleatorias-dado-un-array-de-elementos/
published: true
post_date: 2016-02-15 21:25:15
---
En el bootcamp en el que estoy dando clases en Irlanda (<a href="http://www.codeinstitute.net/" target="_blank">Code Institute</a>) hoy tocaba <a href="https://en.wikipedia.org/wiki/Test-driven_development">TDD</a> :)

Para practicar TDD les he propuesto unas <a href="https://github.com/juanmaguitar/exercises-katas-js" target="_blank">katas</a> y he pensado que la mejor manera de practicar esto era que hicieran <a href="https://en.wikipedia.org/wiki/Pair_programming" target="_blank">pair-programming</a> y que cada hora cambiaran de compañero. Para decidir las parejas he decidido crear un pequeño script que re-ordenara de forma aleatoria un array con los nombres de los alumnos y que además, los agrupara por parejas (o en grupos de 3, de 4 o de lo que hiciera falta en cada momento).

<!--more-->Como en mi opinión creo que  ha quedado un código interesante y útil al <em>ordenar</em> aleatoriamente pasandole una función (<a href="http://stackoverflow.com/a/18650169">bastante ingeniosa</a>) al metodo <a href="https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/sort" target="_blank">sort()</a>, y al <em>agrupar</em> utilizando el metodo <a href="https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/reduce" target="_blank">reduce()</a>, lo comparto aqui por si a alguien le puede ser de utilidad (aunque sólo sea desde el punto de vista didáctico)

Aqui teneis el codigo en ES2015

<pre class="lang:js decode:true" title="shuffleAndGroup ES2015">var shuffleAndGroup = ( students, sizeGroups=2 ) =&gt; {
    var shuffled = students.sort( () =&gt; (.5-Math.random()) )
    var grouped = shuffled.reduce( ( acc, current, index ) =&gt; {
        index%sizeGroups ? acc[acc.length-1].push(current) : acc.push([current]);
        return acc;
    },[])
    return grouped;
}</pre>

Y aqui el codigo en ES5 un poco más desarrollado y explicado

<pre class="lang:js decode:true " title="shuffleAndGroup ES5">function shuffleAndGroup ( students, sizeGroups ) {
    var sizeGroups = sizeGroups || 2;
    var shuffled = students.sort( function() { return .5 - Math.random(); })

    var grouped = shuffled.reduce( function( acc, current, index, array ) {
        
        if ( index%sizeGroups )  { 
            acc[acc.length-1].push(current) // add elements to the group
        }
        else { 
            acc.push([current]) // new group
        }
        return acc;
    },[])

    return grouped; // return an array of arrays (pairs)
}</pre>

Y aqui podeis ver el código en acción

<iframe width="100%" height="400" src="//jsfiddle.net/juanma/tvLff1rn/embedded/js,result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>