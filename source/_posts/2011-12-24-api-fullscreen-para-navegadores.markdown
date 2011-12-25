---
layout: post
title: "API Fullscreen para navegadores"
date: 2011-12-24 18:43
comments: true
categories: canvas html5 javascript
---
La API fullscreen para navegadores es una característica (todavía en fase
experimental) que ya implementan las nuevas versiones de Chrome. En Firefox 9
viene implementada pero no está habilitada, a partir de la versión 10 ya vendrá
activada por defecto.

El uso de la API es muy simple, se resume en lo siguiente: Podemos coger un
bloque multimedia de la web que estamos desarrollando (un video, una imagen, 
un canvas) y ampliarlo a pantalla completa para enfocar la atención del 
usuario a esa zona de nuestra web, consiguiendo así que el visitante 
se concentre y visualice mejor ese elemento.

Las llamadas a la API son muy concretas. Para pasar a pantalla completa un 
elemento, llamamos (vía javascript) a la función **RequestFullScreen** desde el
propio elemento. Y para volver al modo normal, llamamos a la función
**CancelFullScreen** desde el elemento **document**.
```
div.RequestFullScreen(); // Solicita la activación de pantalla completa 
                         // sobre el elemento div que queramos

document.CancelFullScreen(); // Cancela la pantalla completa y vuelve al modo
                             // de visualización normal
```

Dispondremos también del evento **fullscreenchange** que se dispara cuando se detecta 
el paso al modo pantalla completa. Ejemplo:
```
document.addEventListener('fullscreenchange', on_fullscreen_change);
```

Finalmente, tenemos una propiedad de sólo lectura que nos informa si el
navegador está en modo fullscreen.
```
document.FullScreen // tendrá un valor true o false
```

Para terminar, simplemente comentar que mientras se estandariza la API, cada
navegador la implementa por su cuenta, y como viene siendo habitual,
necesitaremos llamar a estas funciones de manera diferente según el navegador
(mozRequestFullScreen, webkitCancelFullScreen, etc.). 

Podéis ver mejor todo esto en la demo siguiente:
[http://dev.micronautas.com/demos/fullscreen/fullscreen.html](http://dev.micronautas.com/demos/fullscreen/fullscreen.html)

Enlaces de interes:

* [Mozilla: Using full-screen mode](https://developer.mozilla.org/en/DOM/Using_full-screen_mode)
* [HTML5Rocks: Fullscreen API](http://updates.html5rocks.com/2011/10/Let-Your-Content-Do-the-Talking-Fullscreen-API)
