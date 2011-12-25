---
layout: post
title: "Herramientas Linux bajo entorno Windows"
date: 2011-12-23 17:08
comments: true
categories: windows linux
---
De vez en cuando me surge la necesidad de trabajar en un entorno Windows, y la
verdad es que se echan de menos determinadas herramientas GNU-Linux de las que
adolece cualquier sistema operativo Microsoft.

En esos casos lo primero que hago es instalarme [CygWin](http://cygwin.com),
bajando un simple instalador y siguiendo un wizard siguiente-siguiente
tendremos disponibles las principales herramientas Unix (cut, grep, find, awk, sort,
cat, ls, etc.), pudiendo a su vez añadir más utilidades al estilo de un
instalador de paquetes gráfico (por ejemplo podremos instalar vim, git,
mercurial, etc.).

Sólamente instalarlo, abrir una línea de comandos y ver un **bash** en
funcionamiento ya reconforta.

Además, si la consola clásica de Windows no nos convence, podemos utilizar una
consola más usable como es un terminal de putty adaptado a cygwin: [puttycfg](http://code.google.com/p/puttycyg/)

Os cuento cómo lo configuro:

* Descargo e instalo [CygWin](http://cygwin.com).

{% img http://www3.uji.es/~vrubert/blog/images/posts/cygwin01.jpg %}

* Descargo [puttycfg](http://code.google.com/p/puttycyg/), y pongo un acceso
   directo al ejecutable en la barra de acceso rápido de Windows:

{% img http://www3.uji.es/~vrubert/blog/images/posts/puttycfg04.jpg %}

* Arranco **putty** por primera vez y guardo una nueva sesión llamada
   **bash** con los siguientes datos:

{% img http://www3.uji.es/~vrubert/blog/images/posts/puttycfg01.jpg %}

* Edito el acceso directo de la barra de acceso rápido y le pongo un sufijo al
   comando ejecutable: "-load bash".

{% img http://www3.uji.es/~vrubert/blog/images/posts/puttycfg03.jpg %}

* Listo, al pulsar el acceso directo se me abre una consola similar a la de
   Linux, todo un lujo para el entorno en el que estamos. :)

{% img http://www3.uji.es/~vrubert/blog/images/posts/puttycfg02.jpg %}
