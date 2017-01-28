---
layout: post
title: 'Ruby On Rails Scaffolding'
date: '2008-08-05 02:16:00 -0600'
categories: tutoriales
published: true
---

[Ruby On Rails](http://www.rubyonrails.org/) es un excelente punto de partida para entender el patron de diseño [MVC](http://es.wikipedia.org/wiki/Modelo_Vista_Controlador) en web, y el framework cuenta con muchas herramientas que facilitan tu trabajo, te ahorran tiempo y te ayudan a desarrollar aplicaciones web muy rápidamente. Un ejemplo de esto es la funcionalidad de [scaffold](http://www.carlosleopoldo.com/post/que-es-el-scaffolding-o-scaffold/) incluida en Rails, que con solo unos cuantos comandos puedes generar tu modelo, vista, controlador y hasta crear la tabla en la base de datos. Además, siguiendo la teoría de [CRUD](http://es.wikipedia.org/wiki/CRUD), el comando de scaffold genera además toda la gestión para crear, eliminar, editar y mostrar los datos del modelo en que se esta trabajando, por lo que ya tienes las funciones básicas de un mantenimiento a una tabla, esto es muy útil y te ahorra mucho tiempo.

Explicare como hacer esto en unos simples pasos, si todavía no has instalado Ruby On Rails en tu máquina local, te recomiendo que sigas las [instrucciones](http://www.rubyonrails.org/) que vienen en el sitio oficial. También puedes seguir los [tutoriales básicos](http://www.onlamp.com/pub/a/onlamp/2006/12/14/revisiting-ruby-on-rails-revisited.html) que tienen, para que tengas una idea mas general de como funciona Ruby.

A partir del lanzamiento de [Rails 2.0](http://weblog.rubyonrails.org/2007/12/7/rails-2-0-it-s-done) ha cambiado un poco la manera en que se realiza el scaffold, por lo que si has seguido anteriormente tutoriales que utilizan versiones anteriores a esta, te veras un poco confundido, por lo que aquí explico como hacerlo correctamente en 4 sencillos pasos:

1. Generar la aplicación:

{% highlight shell %}
$ rails aplicacion
{% endhighlight %}

2. Usando tu [editor de texto](https://atom.io/), abre el archivo database.yml ubicado en \mi_aplicacion\config y configurarlo con tus credenciales de la base de datos. En mi caso estoy usando [MySQL](https://www.mysql.com/), ten en cuenta que por razones de convención, RoR necesita crear 3 bases de datos. Es importante que el nombre de cada una sea el mismo seguido de production, development o test:

{% highlight shell %}
development:
  adapter: sqlite3
  database: db/development.sqlite3
  pool: 5
  timeout: 5000

test:
  adapter: sqlite3
  database: db/test.sqlite3
  pool: 5
  timeout: 5000

production:
  adapter: mysql
  encoding: utf8
  database: your_db
  username: root
  password: your_pass
  socket: /tmp/mysql.sock
{% endhighlight %}

  3. Crear las bases de datos

  4. Generar la estructura con scaffold. Noten que después de scaffold sigue el nombre del modelo (tabla) seguido de las columnas y el tipo de dato:

{% highlight shell %}
$ generate scaffold User
{% endhighlight %}

  5. Crear las tablas en la base de datos

Listo! Ahí tienes una aplicacion lista para ser ejecutada, obviamente es un poco sencilla, pero muestra básicamente lo que puedes lograr utilizando esta herramienta y toda el tiempo que te ahorras también.

Si quieres ver tu aplicacion en acción solamente corres tu servidor web que tienes configurado para RoR, en mi caso estoy utilizando el WEBrick, que ya viene incluido en el framework. Puedes arrancarlo de la siguiente manera

{% highlight shell %}
$ rails server
{% endhighlight %}

Luego te vas a tu explorador preferido y escribes la ruta hacia tu aplicacion, en el caso de nuestro ejemplo es: http://localhost:3000/datos. Y a partir de ahí todo se explica por si mismo, te sorprenderá ver todo lo que hiciste en tan solo unas cuantas líneas de código. Es importante que después (como todo geek) te pongas a examinar un poco el código para ver que hay detrás de todo esto y como funciona.
