---
layout: post
title: Obtener tipo de cambio actual (Colones-Dolares) en PHP
date: '2010-12-29 21:40:32 -0600'
categories: tutoriales
published: true
---

En muchos sitios web, como en los carritos de compra, es necesario obtener el tipo de cambio asociado a una moneda, ya sea para calcular el precio o para fines informativos. Muchos [sistemas][sistemas] ya incluyen esta funcionalidad, y lo más usual es que sea el mismo administrador el que tenga que estar actualizando este dato.

Lo más optimo es obtener este valor de alguna fuente confiable, ya que se desea que este dato esté actualizado. Por lo general la mayoría de los Bancos ponen a disposición algún tipo de servicio web por el cual se pueden obtener estos valores.

En mi país (Costa Rica) el Banco Central dispone de un [WebService][webservice] que se puede utilizar para obtener el tipo de cambio actual. Hay varios métodos para obtener estos datos, dependiendo del lenguaje en que se este desarrollando, en esta ocasión les voy a explicar como hacerlo en [PHP][php], y para facilitarles el trabajo pongo a su disposición [una clase en php][clase] donde solamente indican el valor que desean (compra o venta) y esta se los retorna. Esta clase funciona específicamente para consumir el WebService del Banco Central de Costa Rica, pero es completamente adaptable para utilizar cualquier otro servicio, ya que los métodos que utiliza son los que generalmente se usan para obtener datos por este medio.

Para utilizar la herramienta esto es lo que tienen que hacer:

1. Descargar los [archivos necesarios][clase] (estos incluyen la clase y la librería [nusoap][nusoap] si se desean obtener los datos con [SOAP][soap])
2. Incluir la clase en el archivo que deseas utilizarla
3. Obtener los datos de esta manera:

{% highlight php %}
require_once("Indicador.php");
$i = new Indicador(true);
$valor = $i->obtenerIndicadorEconomico(Indicador::VENTA);
{% endhighlight %}

El constructor de la clase `Indicador` recibe como parámetro un booleano que indica si los datos se van a obtener por medio del método SOAP (si no lo indicas por defecto es falso). Esto depende mucho del servidor donde se encuentre tu sitio web, ya que algunos no permiten utilizar la función de [file_get_contents][file-get-contents] (usada con el método GET)  por razones de seguridad, en este caso es cuando necesitas obtener los datos con SOAP (es importante que siempre incluyas bajo el mismo directorio donde está la clase `Indicador.php` la carpeta `/soap` que contiene los archivos necesarios para utilizar este método).

La función `obtenerIndicadorEconomico` recibe como parámetro el tipo de cambio que se desea, estos son valores constantes definidos en la misma clase, por lo que para indicar si deseas el valor de la Venta pasarías por parámetro `Indicador::VENTA` y para la compra `Indicador::COMPRA`.

Con esto ya obtienes el valor del tipo de cambio actualizado. Yo recomiendo programar algún tipo de cronjob o algo por el estilo para guardar este valor en base de datos, y no estar accesando al WebService cada vez que se ingresa al sitio web.

Como siempre los [archivos y el código][archivos] están siempre disponibles.

***
**[ACTUALIZACIÓN]**: Hace poco agregué esta herramienta en [packagist][packagist], por lo que ya es posible instalarla más facilmente por medio de [composer][composer]. El proyecto está en github: [https://github.com/arielcr/tipocambio-bccr][paquete], ahí van a encontrar las instrucciones de como utilizarlo.

[packagist]: https://packagist.org/packages/arielcr/tipocambio-bccr
[composer]: https://getcomposer.org/
[paquete]: https://github.com/arielcr/tipocambio-bccr
[sistemas]: http://www.opencart.com/
[webservice]: http://es.wikipedia.org/wiki/Servicio_web
[php]: http://es.wikipedia.org/wiki/PHP
[clase]: https://github.com/arielcr/indicadores-bccr/downloads
[nusoap]: http://sourceforge.net/projects/nusoap/
[soap]: http://es.wikipedia.org/wiki/Simple_Object_Access_Protocol
[file-get-contents]: http://php.net/manual/en/function.file-get-contents.php
[archivos]: https://github.com/arielcr/indicadores-bccr
