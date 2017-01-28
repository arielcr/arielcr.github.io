---
layout: post
title: 'Empezando con CodeIgniter'
date: '2008-12-20 23:10:00 -0600'
categories: tutoriales
published: true
---

Hace unos meses empeze a trabajar en un sitio web que necesitaba un cliente, era basicamente un sitio de busqueda de propiedades con un [backend](http://es.wikipedia.org/wiki/Back_end) en donde se agregaran dichas propiedades. Se necesitaba una solución rápida, obviamente que sin dudar elegí [LAMP](http://es.wikipedia.org/wiki/LAMP) (Linux,Apache,MySQL,PHP). El problema es que el proyecto lo necesitaba trabajar en conjunto con alguien que no tenia nada de experiencia con [PHP](http://php.net/), y tampoco se contaba con el tiempo para una capacitación extensiva sobre el lenguaje, así que se me ocurrió utilizar algún tipo de [framework para PHP](http://www.tufuncion.com/top10_framework) que pudiera acelerar el proceso.

Yo había oído sobre frameworks javascript o AJAX, y rara vez oí mencionar que existían también en PHP. Uno de los candidatos fue [CakePHP](http://cakephp.org/), al cual no le tome mucha importancia ya que no poseía tanta popularidad como [CodeIgniter](http://codeigniter.com/), en donde hablaban muy bien en los reviews que leí, y además me llamo mucho la atención el gran parecido que tiene en estructura con Ruby-On-Rails. Básicamente el framework es una librería con muchas funciones en PHP predefinidas que hacen mas rápido el desarrollo en esta plataforma, sin que sea necesario que tengas un conocimiento amplio sobre el lenguaje, además de muchas funciones para conexión con bases de datos y consultas SQL que también facilitan el desarrollo.

La instalación es sencilla, tan solo se descargan los [archivos](https://codeigniter.com/download) y los copian en su servidor. Lo mejor es que en el sitio de codeigniter tienen una excelente [documentación](http://codeigniter.com/user_guide/), además de videos introductorios, tutoriales y muchas [referencias](http://codeigniter.com/user_guide/database/index.html) a las funciones del framework. Para empezar hay que configurar algunos ficheros, principalmente el de base de datos, estos son unos puntos importante para tener en cuenta:

* Para establecer los parámetros de conexión a la base de datos tienen que editar el archivo que se encuentra en: system/application/config/database.php en donde ingresan los datos de conexión a su servidor.

* Tienen que indicar que van a utilizar una base de datos, para esto editan el archivo ubicado en: `System/application/config/autoload.php` y buscan esta linea: `$autoload['libraries'] = array('');` y la remplazan por esta otra: `$autoload['libraries'] = array('database')`;

El framework además tiene la capacidad de hacer [scaffolding](http://en.wikipedia.org/wiki/Scaffold_%28programming%29), en donde se ve su parecido con RoR y me parece genial para realizar un mantenimiento rápido de la base de datos, es fácil usarlo:

* Ponen esta linea: `$this->load->scaffolding('<tabla>');` en el constructor de la aplicación. Luego en este archivo: `System/application/config/routes.php` ponen esta línea: `$route['scaffolding_trigger'] = “mante”;` y accesan a la pagina de scaffolding así: `localhost/controlador/mante`

La intención no es darles toda una capacitación sobre CodeIgniter, ya que el sitio oficial cuenta con todo lo que necesitan saber, solamente les dejo los consejos anteriores para que los tengan en cuenta ;).

Si ya saben y tienen experiencia con PHP les va a resultar extremadamente sencillo y entretenido usar CodeIgniter, aunque para mi la experiencia fue muy interesante y diferente, al final sigo prefiriendo usar PHP puro (por así decirlo…), recomiendo mucho codeigniter si quieren desarrollar sitios rápidamente, y si no tienen experiencia con PHP también es una buena opción, pero les recomiendo mejor que primero investiguen un poco sobre [PHP](http://w3schools.com/php/default.asp) en esencia para que tengan una mejor noción de sobre que están trabajando y que además sepan bien como modificar el código si tuvieran que hacerlo.

Finalmente el resultado fue muy alentador y gusto mucho al cliente. Cualquier pregunta duda o comentario sobre el framework pueden postearla acá!
