---
layout: post
title: "Sirviendo nuestro proyecto Node.js detrás de un servidor web Nginx"
date: 2012-03-16 16:46
comments: true
categories: nodejs nginx
---

Realizando un proyecto en [node.js](http://nodejs.org) y viendo cómo las cosas
empiezan a cuajar, te vas dando cuenta de necesidades adicionales a la propia
programación orientada a eventos, como por ejemplo, servir tus páginas desde el
puerto 80.

El servidor http que implementa **node.js** es rápido y eficiente, pero no
siempre podemos arrancarlo en el puerto 80. Puede que no tengamos un usuario
con los privilegios necesarios, puede que ya tengamos otras ṕaginas en esa
máquina que tienen que seguir funcionando, o puede que necesitemos
características propias de un servidor web y que no vienen incorporadas en el
servidor web de **node**.

En esos casos mejor delegar el frontal en un servidor web también rápido y
eficiente como es [Nginx](http://nginx.org). Pongo la receta a utilizar para
servir el contenido de nuestro servicio **Node** (escuchando en el puerto 3000)
en una ruta de nuestro servidor web:

Sección *http* de **Nginx**:

```
upstream app_miservicionode {
    server 127.0.0.1:3000;
}
```

Seccion *server* de **Nginx**:
```
location /ruta {
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header Host $http_host;
        proxy_set_header X-NginX-Proxy true;

        proxy_pass http://app_miservicionode;
        proxy_redirect off;
}
```

Y listo, con esto habilitamos un proxy de Nginx que redirigirá las peticiones
al puerto 80 de nuestro servidor, al puerto 3000 del interfaz local
(127.0.0.1), que es donde estará corriendo nuestro servicio **node.js**.

En una siguiente entrada veremos como conseguir que nuestro servicio **node**
este siempre funcionando en el sistema.
