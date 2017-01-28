---
layout: post
title: 'URL limpias con CodeIgniter'
date: '2008-12-22 22:26:00 -0600'
categories: tutoriales
published: true
---

Algo muy útil que permite el [CodeIgniter][codeigniter] es utilizar "URLs limpias", lo que hace esto es quitar cualquier nombre de archivo y extinción al final de la URL, inclusive los parámetros enviados por GET, con lo que obtenemos URLs limpias y fáciles de aprender.

Por ejemplo, usualmente en sitios dinámicos tenemos la dirección: `www.midominio.com/paginas.php?num=54` , en CodeIgniter se vería algo así: `www.midominio.com/index.php/paginas/num/54`. Eso limpia bastante la URL, y cumple con el patrón de diseño [MVC][mvc]. Para ver como trabajan las URLs en CodeIgniter pueden consultar la [referencia][referencia] del framework.

Como pudieron ver por defecto es necesario incluir el `index.php` en la URL, pero esto se puede modificar fácilmente, y después de buscar cual es la mejor manera que funciona en la mayoría de los casos, aquí se las dejo:

1. Abren el archivo `System/application/config/config.php` y se fijan que esta línea esté así: `$config['index_page'] = ""`;

2. En la raiz de su sitio crean un archivo en blanco que se llame [.htaccess][htaccess], lo abren con un editor de texto y copian esto:

{% highlight shell %}
RewriteEngine On
RewriteBase /
RewriteCond %{REQUEST_URI} ^system.*
RewriteRule ^(.*)$ /index.php/$1 [L]

RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L]

ErrorDocument 404 /index.php
{% endhighlight %}

3. Reinician su servidor web (si están trabajando localmente) y listo!

Si están trabajando su aplicación dentro de un directorio en su servidor tienen que cambiar la línea donde esta el `index.php?/$1` y anteponer el nombre del directorio `midirectorio/index.php?/$1`. Tomen en cuenta que esto funciona para servidores que corren [Apache][apache] y que soportan estos archivos de configuración.

Cualquier duda o consultan pueden comentarlo.

[codeigniter]: https://codeigniter.com/
[mvc]: https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador
[referencia]: http://codeigniter.com/user_guide/general/urls.html
[htaccess]: http://httpd.apache.org/docs/1.3/howto/htaccess.html
[apache]: https://es.wikipedia.org/wiki/Servidor_HTTP_Apache
