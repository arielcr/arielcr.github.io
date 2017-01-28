---
layout: post
title: "¿Cómo actualizar mi sitio web cada vez que hago cambios en GitHub?"
date: '2013-11-14 18:42:08 -0600'
categories: git
published: true
---

Es muy probable que alguna vez nos hallamos preguntado esto. Sería genial si cada vez que actualizo los cambios en mi repositorio, estos se "subieran" de manera automática a mi servidor web. Tal vez muchos estén haciendo esto de manera manual, actualizando tu repositorio y después subiendo tus archivos al servidor por FTP. Algunas desventajas de esto es que puedes perder el control de versiones, ya que al ser un proceso manual, es posible que no todos los cambios se vean reflejados en el sitio web, y termines con distintas versiones de archivos mezclados.

[GitHub][GitHub] permite ejecutar ciertos scripts después que realizas push a tu repositorio, estos son los llamados [Post-Receive Hooks][post-receive-hooks], y es lo que vamos a utilizar para automatizar todo este proceso.

Estos son los pasos que necesitas realizar:

1. Clonar el repositorio con los [WebHooks][web-hooks]

{% highlight shell %}
git clone https://github.com/arielcr/web-hooks.git
{% endhighlight %}

2. Subir la carpeta `web-hooks` a la raiz de tu servidor web.

3. Te vas a tu repositorio en tu cuenta de GitHub, a `Settings -> Service Hooks -> WebHooks URLs`

4. Una vez ahi copias la dirección con la ruta al archivo `update-server.php` (ej: http://tusitio.com/web-hooks/update-server.php)

5. Presionas "Update Settings"

Ahora, cada vez que hagas cambios en tu repositorio y los actualizes en GitHub, estos se van a ver reflejados de manera automática en tu servidor web. Este proceso va a crear una carpeta con el nombre de tu repositorio en la raiz del servidor web. Además, en la carpeta `logs` va a quedar un registro con todos los commits por cada repositorio que utilize este [WebHook][web-hooks].

Si te preguntas como funciona todo esto, lo que en realidad hace el WebHook `update-server.php` es que cada vez que actualizas el repositorio en GitHub, este comprueba que el repositorio no exista en tu servidor, si ya existe solamente lo actualiza y sino, lo clona en la carpeta con el mismo nombre.

Trataré de agregar más hooks útiles a este repositorio para que también los puedan utilizar de la misma manera.

[GitHub]: https://github.com/
[post-receive-hooks]: https://help.github.com/articles/post-receive-hooks
[web-hooks]: https://github.com/arielcr/web-hooks
