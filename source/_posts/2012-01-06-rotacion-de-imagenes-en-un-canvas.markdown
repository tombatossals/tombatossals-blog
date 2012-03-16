---
layout: post
title: "Rotación de imágenes en un canvas"
date: 2012-01-06 20:47
comments: true
categories: canvas javascript
---
Veamos un ejemplo de desarrollo en un canvas HTML, en este caso trabajaremos
con una imagen a la cual le aplicaremos una animación consistente en rotar la
imagen.

Veamos la demo antes que nada (mejor visitar el enlace que os propongo abajo
para que os funcione el botón de fullscreen):

<iframe style="width: 720px; height: 500px;" src="http://dev.micronautas.com/demos/imgrotation/imgrotation.html"></iframe>
 * [http://dev.micronautas.com/demos/imgrotation/imgrotation.html](http://dev.micronautas.com/demos/imgrotation/imgrotation.html)

En esta demo podemos observar 3 novedades puestas en práctica:

 * Una animación realizada en base a la rotación una imagen de un sol a 60fps.
 * Un monitor que contabiliza el número de frames obtenidos en el
   renderizado, y los milisegundos necesarios para procesar cada nuevo frame.
 * Un botón que nos permite realizar un fullscreen de una zona de nuestra
   página.

Vayamos por partes, de fácil a difícil.

stats.js
--------
El monitor de frames lo podemos incorporar en cualquiera de nuestros proyectos
de una manera extremadamente fácil utilizando el código del proyecto 
[stats.js](https://github.com/mrdoob/stats.js).

Fullscreen API
--------------
Tal y como comenté en el [anterior post](http://www3.uji.es/~vrubert/blog/2011/12/24/api-fullscreen-para-navegadores/), la Fullscreen API nos permite focalizar la atención del usuario maximizando una zona de nuestra web a pantalla completa. La implementación que véis en este código funciona tanto en Chrome como en Firefox. A destacar el código CSS necesario para unificar la manera de maximizar de los dos navegadores.

Canvas Image Rotation
---------------------
Finalmente, comentar que en el código veremos en funcionamiento una de las utilidades incorporadas recientemente en los navegadores como es el control de frames mediante la función **requestAnimationFrame** (todavía en desarrollo en algunos navegadores), así como la manera de realizar una rotación de imagen sobre un canvas, se ilustra perfectamente en esta imagen:

![Image rotation on canvas](http://www3.uji.es/~vrubert/blog/images/posts/drawimage01.png)

El código fuente es sencillo y se explica por si mismo: [script.js](http://dev.micronautas.com/demos/imgrotation/script.js).

Referencias:

 * [Info sobre la Fullscreen API ](http://updates.html5rocks.com/2011/10/Let-Your-Content-Do-the-Talking-Fullscreen-API)
 * [WhatWG: el elemento canvas](http://www.whatwg.org/specs/web-apps/current-work/multipage/the-canvas-element.html#images)
 * [Safari Developer Library](http://developer.apple.com/library/safari/#documentation/AudioVideo/Conceptual/HTML-canvas-guide/Translation,Rotation,andScaling/Translation,Rotation,andScaling.html)
 * [Mozilla Hacks: requestAnimationFrame](http://hacks.mozilla.org/2011/08/animating-with-javascript-from-setinterval-to-requestanimationframe/)
