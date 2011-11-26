---
layout: post
title: "Instalando ruby 1.9.2 mediante rvm"
date: 2011-11-26 17:50
comments: true
categories: ruby recipe
---
Al probar proyectos rails nos encontraremos con el problema de las múltiples
dependencias de otras librerías que tienen cada uno de ellos, y el problema que
eso supone para mantener nuestro sistema al día.

Lo mejor para estos casos es utilizar RVM, que nos instalará un entorno ruby
propio para nuestros proyectos, independizándonos así de los paquetes ya
instalados en el sistema.

Enlace: [http://beginrescueend.com/](http://beginrescueend.com/)

Receta de instalación de Ruby 1.9.2 con RVM:

```
# Install RVM
bash < <(curl -s https://rvm.beginrescueend.com/install/rvm)
echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load
RVM function' >> ~/.bash_profile
source ~/.bash_profile

# Install OpenSSL&ZLIB
rvm pkg install openssl
rvm pkg install zlib

# Install Ruby
rvm install 1.9.2 --with-zlib-dir=$rvm_path/usr
--with-openssl-dir=$rvm_path/usr
```
[http://pastie.org/2923827](http://pastie.org/2923827)
