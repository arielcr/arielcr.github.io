---
layout: post
title: Depurar Javascript
date: '2008-01-31 17:20:00 -0600'
categories: javascript
published: true
---

Javascript es genial! pero acaso no les ha causado dolor de cabeza cuando por alguna razon tienen un error en un script (y mas si este script es muy grande…) y tienen que ir linea por linea a revisar el codigo, eso es frustrante. Recientemente tuve un problema con un script de validacion de un formulario muy extenso, se que el IE te da una pequeña alerta amarilla al lado izquierdo de su [sacastico]agil y versatil navegador[/sarcastico] cuando hay un error de estos, pero aveces esto no sucede, asi que decidi ver que depuradores existian por ahi para Javascript, encontre algunos muy interesantes:

**Para Firefox**

* [Venkman Javascript Debugger](https://addons.mozilla.org/es-ES/firefox/addon/216): es un addon para Firefox y navegadores basados en mozilla, muy util pero a mi parecer demasiadas funcionalidades si solamente necesitas localizar donde se encuentra el error.

* [Firebug](https://addons.mozilla.org/es-ES/firefox/addon/1843): muy conocido por todos, trae otras funciones aparte del depurador javascript, muy utiles por cierto, y las utilizo frecuentemente, el depurador me ha sido util en algunas ocasiones, pero insisto… solamente quiero saber donde esta el error!

**Para IE**

* [Microsoft Script Debugger](http://www.microsoft.com/downloads/details.aspx?FamilyID=2f465be0-94fd-4569-b3c4-dffdf19ccd99&displaylang=en): estas opciones son interesantes si eres un MicroFan, no lei mucho al respecto, ya que estoy utilizando Firefox, pero los MicroLovers pueden hecharle un vistazo.

* [Microsoft Script Editor](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnfp2k2/html/odc_fpdebugscripts.asp): este viene con el Office 2003, si utilizas el FrontPage… yo uso el DreamWeaver, asi que no he visto este en particular (ni creo utilizarlo…).

Despues de ver estas opciones, decidi darle la oportunidad a la consola de error que viene con el Firefox.

La habia utilizado para otras cosas, pero no para Javascript, y fue la solucion a mi problema. Por mas sencilla que parezca, tiene las opciones que necesito, simplemente abres la pagina con el Firefox, abres la consola y ahi tienes el error! le das click y te abre el codigo fuente del script en la linea donde esta el error. Es una opcion rapida y sencilla para los que buscan depurar su codigo con facilidad sin tener que establecer breakpoints ni nada por el estilo.
