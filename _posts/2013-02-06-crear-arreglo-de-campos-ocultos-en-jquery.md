---
layout: post
title: Crear arreglo de campos ocultos en jQuery
date: '2013-02-06 20:16:48 -0600'
categories: jquery
published: true
---

Puede ser que en algunas ocasiones necesiten crear dinámicamente campos ocultos en un formulario, o mejor aún, un arreglo de campos ocultos, y  según alguna acción que realize el usuario se vayan agregando valores a este arreglo, luego ustedes procesan el formulario como lo deseen. Si este es su caso, este pequeño código les puede ser muy útil:

{% highlight javascript %}
var $campo_oculto = $('',{type:'hidden',value:elvalor,name:'ocultos[]'});
$campo_oculto.appendTo('#formulario');
{% endhighlight %}

En `value` colocan el dato que desean asignar al arreglo y `name` es el nombre del campo oculto, recuerden que tiene que ir con parentesis cuadrados para que el formulario lo procese como un arreglo. Esto pueden colocarlo en una función o un `onclick` de algun botón.

Espero que les sea de utilidad!
