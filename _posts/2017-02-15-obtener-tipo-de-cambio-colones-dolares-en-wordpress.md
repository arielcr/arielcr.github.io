---
layout: post
title: Obtener el tipo de cambio (colones/dolares) en Wordpress
date: '2017-02-15 08:35:00 -0600'
categories: tutoriales
published: true
---

Hace un tiempo publiqué un post sobre como [obtener el tipo de cambio en php][tipocambio] en donde
les compartí un script en php que utiliza el web service del BCCR (Banco Central de Costa Rica) para calcular el tipo de cambio
del día, además de algunas funciones para convertir un monto de colones a dolares y viceversa.

Al tiempo incluí el paquete en [packagist][packagist] para que se pueda utilizar con [composer][composer] para instalarlo en cualquier
proyecto que deseen.

Dado que muchos están usando [Wordpress][wordpress] para sus proyectos, desarrollé un [plugin][plugin] que hace lo mismo, pero con 
la facilidad de poder instalarlo en tu sitio en Wordpress y utilizarlo en cualquier archivo de template o si lo deseas también 
incluirlo en un post o en una página por medio de tags.

### Instalación

Para instalar el plugin debe de hacer lo siguiente:

1. Subir el archivo [wp-tipo-cambio-cr.zip][plugin] y descomprimirlo en el folder `/wp-content/plugins/` 
2. Activar el plugin a travez del menu *Plugins* en WordPress

#### En un template

###### Obtener tipo de cambio

{% highlight php %}
<?php wptcr_tipo_cambio('COMPRA'); ?>
{% endhighlight %}

{% highlight php %}
<?php wptcr_tipo_cambio('VENTA'); ?>
{% endhighlight %}

###### Convertir un monto

{% highlight php %}
<?php wptcr_convertir_colones_dolares(25000); ?>
{% endhighlight %}

{% highlight php %}
<?php wptcr_convertir_dolares_colones(100); ?>
{% endhighlight %}

#### En un post/page

Tipo de cambio de compra: `[WPTCR_TIPO_CAMBIO_COMPRA]`

Tipo de cambio de venta: `[WPTCR_TIPO_CAMBIO_VENTA]`

Colones a Dolares: `[WPTCR_CONVERTIR_COLONES_DOLARES monto=20000]`

Dolares a Colones: `[WPTCR_CONVERTIR_DOLARES_COLONES monto=200]`

Pronto les actualizare con el link al plugin en Wordpress para que si lo desean lo puedan instalar desde su sitio directamente.

Saludos!

[packagist]: https://packagist.org/packages/arielcr/tipocambio-bccr
[composer]: https://getcomposer.org/
[wordpress]: https://wordpress.org/
[plugin]: https://sourceforge.net/projects/wp-tipo-cambio-cr/files/wp-tipo-cambio-cr.zip
[tipocambio]: http://arielorozco.com/tutoriales/obtener-tipo-de-cambio-actual-colones-dolares-en-php/
