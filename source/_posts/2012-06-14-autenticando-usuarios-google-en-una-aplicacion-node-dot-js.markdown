---
layout: post
title: "Autenticando usuarios Google en una aplicación node.js"
date: 2012-06-14 14:17
comments: true
categories: nodejs google openid
---

Por fin saco un rato de tiempo para documentar lo que voy aprendiendo con node.js, en este caso me he propuesto realizar una sencilla demo de autenticación de usuarios contra el backend de usuarios de Google. Básicamente, queremos un botón de **Login** donde el usuario pueda autenticarse, pero no queremos mantener una base de datos de usuarios locales, sino delegar la autenticación a Google, en este caso haciendo uso de su infraestructura [OpenId](http://es.wikipedia.org/wiki/OpenID)

Para el que quiera ir directo al grano, este es el proyecto en **github** que implementa esta sencilla aplicación:
[https://github.com/tombatossals/node-openid-auth-sample.git](https://github.com/tombatossals/node-openid-auth-sample.git)

La pila tecnológica utilizada en este caso esta basada en **Node.js**
