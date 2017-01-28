---
layout: post
title: CORS (Access-Control-Allow-Origin) en API RESTful con Silex
date: '2014-10-22 12:55:49 -0600'
categories: tutoriales
published: true
---

Es muy común cuando desarrollas un API [Restful][Restful] que te topes con el típico `No ‘Access-Control-Allow-Origin’ header is present on the requested resource.`. Esto sucede porque estás haciendo un [XMLHttpRequest][XMLHttpRequest] a un dominio distinto del de la aplicación, el navegador bloquea estas peticiones por motivos de seguridad. Una solución de esto es usar [CORS][CORS], y para nuestra facilidad esto es muy sencillo si desarrollas tu API con [Silex][Silex].

En el archivo donde inicias tu aplicación (generalmente app.php) debes colocar esto al inicio del script:

{% highlight php %}
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;
{% endhighlight %}

Y después incluyes esto:

{% highlight php %}
$app->after(function (Request $request, Response $response) {
    $response->headers->set('Access-Control-Allow-Origin', '*');
});
{% endhighlight %}

En una aplicación sencilla te quedaría algo así:

{% highlight php %}
use Silex\Application;
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;

$app = new Application();

$app['debug'] = false;

$app->after(function (Request $request, Response $response) {
    $response->headers->set('Access-Control-Allow-Origin', '*');
});

return $app;
{% endhighlight %}

Con eso ya tienes solucionado tu problema!

Si necesitas un esqueleto de una aplicación Silex puedes usar [mi template de silex][template] que esta basado en el de [Fabien Potencier][fabien] (creador de Silex), solo que con algunas librerías útiles  de más.

[Restful]: http://en.wikipedia.org/wiki/Representational_state_transfer
[XMLHttpRequest]: https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest
[CORS]: http://en.wikipedia.org/wiki/Cross-origin_resource_sharing
[Silex]: http://silex.sensiolabs.org/
[template]: https://github.com/arielcr/77-silex-starter
[fabien]: https://github.com/silexphp/Silex-Skeleton
