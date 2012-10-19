---
layout: post
title: "Autenticando usuarios Google en una aplicación node.js"
date: 2012-06-14 14:17
comments: true
categories: nodejs google openid
---

Por fin saco un rato de tiempo para documentar lo que voy aprendiendo con node.js, en este caso tenía en mente realizar una sencilla demo de autenticación de usuarios contra el backend de usuarios de Google, de manera que pueda reaprovecharse para otros proyectos. Básicamente, lo que se pretende es crear un página sencilla, con un botón de **Login** donde el usuario pueda autenticarse, pero sin mantener una base de datos de usuarios locales, sino que delegaremos la autenticación a Google haciendo uso de su infraestructura [OpenId](http://es.wikipedia.org/wiki/OpenID)

La pila tecnológica utilizada en este caso esta basada en **Node.js**:

 * [Express](http://expressjs.com/) como framework de desarrollo web.
 * [Mongodb](http://www.mongodb.org/) como base de datos de persistencia.
 * [Passport](http://passportjs.org/) como middleware de autenticación.
 * [Mongoose](http://mongoosejs.com/) como librerías de acceso a la DB.
 * [Jade](http://jade-lang.com/) como sistema de plantillas.
 * [Jquery](http://jquery.com/) como librería javascript para manipulación del
   DOM.
 * [Twitter Bootstrap](http://twitter.github.com/bootstrap/) como framework de
  creación de interfaces de usuario.

Este es el proyecto en **github** que implementa esta sencilla utilidad,
sólamente hay que bajarlo y seguir un par de pasos para tenerlo funcionando,
serviría como código base para entender cómo funciona la autenticación en **node**.

[https://github.com/tombatossals/node-openid-auth-sample.git](https://github.com/tombatossals/node-openid-auth-sample.git)

