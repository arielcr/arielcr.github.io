---
layout: post
title: Convertir números a letras en PHP
date: '2015-12-04 08:35:00 -0600'
categories: programacion
published: true
---

Aveces cuando se está implementando algún tipo de sistema de facturación es necesario desplegar el monto en letras al momento de imprimir la factura.

Si necesitan hacer esto, o simplemente quieren desplegar el equivalente en letras a un número, pueden usar esta [librería][libreria]. La instalación la pueden hacer con [Composer][composer], así que les queda muy fácil usarla en frameworks como [Laravel][laravel].

Solamente agregan esta linea a su archivo `composer.json` y realizan un `composer update`

{% highlight json %}
"arielcr/numero-a-letras": "dev-master"
{% endhighlight %}

Para convertir un valor a su equivalente en letras hacen lo siguiente:

{% highlight php %}
$letras = NumeroALetras::convertir(12345);
{% endhighlight %}

Pueden ver la documentación y el proyecto en Github [aquí][libreria].

¡Saludos!

[libreria]: https://github.com/arielcr/numero-a-letras
[composer]: https://getcomposer.org/
[laravel]: http://laravel.com/
