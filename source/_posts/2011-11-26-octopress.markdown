---
layout: post
title: "Octopress"
date: 2011-11-26 17:31
comments: true
categories: blog ruby
---

[Octopress](http://octopress.org) es un sistema de blogging diferente a todo lo visto hasta ahora. Para
empezar, va a contracorriente de las modas: ¿desde cuándo para publicar en un
blog hay que controlar *Markdown*, *git*, algo de *rails* y *rsync*? Pues con **Octopress** las
cosas son así.

La ventaja principal: editas un archivo de texto formateado con
[Markdown](http://es.wikipedia.org/wiki/Markdown), haces un rsync y tu blog se
publica de una manera **estática**, es decir, no necesitas ni PHP, ni Mysql, ni
un software abierto a posibles fallos, para algo tan simple como escribir.

A mi me sirve, principalmente porque en lepus.uji.es sólo podemos poner
contenido estático, asi que... ¡Bienllegado Octopress!

```
$ rake generate
$ rake desploy
```
