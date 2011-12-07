---
layout: post
title: "Aplicación Rails en servidor web Nginx"
date: 2011-12-06 18:02
comments: false
categories: rails nginx
---
Una aplicación rails funciona con su propio servidor web, normalmente en el
puerto 3000 del sistema. Si queremos servir la aplicación en el puerto 80 estándar
a través de <a href="http://nginx.org">Nginx</a>, deberemos configurar este servidor web para que
actúe de proxy hacia la aplicación rails.

Esta es la receta para el archivo nginx.conf:

```
upstream rails.miservidor.com {
    server 127.0.0.1:3000;
}

server {
    listen   80;
    server_name rails.miservidor.com;
 
    access_log /var/www/rails.miservidor.com/log/access.log;
    error_log  /var/www/rails.miservidor.com/log/error.log;
    root       /var/www/rails.miservidor.com
    index      index.html;
 
    location / {
        proxy_set_header  X-Real-IP  $remote_addr;
        proxy_set_header  X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header  Host $http_host;
        proxy_redirect    off;
        try_files /system/maintenance.html $uri $uri/index.html $uri.html @ruby;
    }
 
    location @ruby {
        proxy_pass http://rails.miservidor.com;
    }
}
```
