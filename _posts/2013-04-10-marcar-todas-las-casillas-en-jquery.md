---
layout: post
title: Marcar todas las casillas en jQuery
date: '2013-04-10 13:08:57 -0600'
categories: javascript
published: true
---

Si necesitan marcar todas casillas de verificación en un formulario, pueden utilizar este sencillo script para lograrlo.

{% highlight javascript %}
$("#boton").click(function(){
    $("#formulario").find("input[type=checkbox]").each(function(){
        $(this).attr("checked", "checked");
     });
});
{% endhighlight %}

Solamente indican el ID del botón o link al que desean agregarle la acción y el ID del formulario (o un div que contenga las casillas).
