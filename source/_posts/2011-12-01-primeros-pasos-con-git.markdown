---
layout: post
title: "Primeros pasos con Git"
date: 2011-12-01 22:27
comments: true
categories: git
---
Antes de empezar cualquier proyecto Git en una nueva máquina deberemos
configurar algunas opciones globales que nos facilitarán nuestro trabajo con el
control de versiones. Veamos 3 opciones básicas:

```
$ git config --global user.name "Peter Pan"
$ git config --global user.email peter.pan@nuncajamas.com
$ git config --global color.ui true
```

Las dos primeras opciones establecen nuestro nombre completo y dirección de
correo que utilizaremos para identificar nuestros commits al repositorio. La
tercera opción nos vendrá muy bien para colorear los mensajes que nos muestra
Git por la salida estándar.

Estas tres opciones configuradas desde línea de comandos se traducen en una
serie de directivas almacenadas en el archivo de configuración .gitconfig:

```
$ cat $HOME/.gitconfig 
[user]
    name = Peter Pan
    email = peter.pan@nuncajamas.com
[color]
    ui = true
```
