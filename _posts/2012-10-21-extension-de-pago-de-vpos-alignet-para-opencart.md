---
layout: post
title: Extensión de Pago VPOS Alignet para Opencart
date: '2012-10-21 01:18:09 -0600'
categories: tutoriales
published: true
---

[Opencart][opencart] es una excelente plataforma que te permite desarrollar sitios de ecommerce o carritos de compra de una manera fácil y rápida. Viene con numerosas librerías y herramientas que facilitan el desarrollo, es muy extensible y el código esta estructurado a manera de MVC, así que resulta muy cómodo modificarlo y adaptarlo a tus necesidades.

En el sitio oficial hay gran cantidad de [extensiones][extensiones] que puedes utilizar para agregar funciones adicionales o extender las ya existentes.

He tenido que integrar en varias ocasiones métodos de pago con tarjeta de crédito en sitios web, utilizando específicamente la plataforma de pago de VPOS del proveedor [Alignet][alignet] que utiliza el Banco Nacional de Costa Rica. El proceso de integración siempre es el mismo, lo que varían son los parámetros y llaves.

Por esta razón desarrollé una [Extensión de Alignet][extension] para de Opencart que puedes instalar en tu carrito de compras si necesitas hacer una integración con Alignet, y así ahorrarte todo la programación que esto conlleva. Lo único que necesitas es instalar la extensión y configurarla, llenando los campos con los datos especificos que Alignet da para el comercio. Existe un Modo de Pruebas que se puede activar cuando te encuentras en etapa de Testing y necesitas ver los valores retornados por el VPOS.

Los pasos par la instalación se encuentran en la página de la extensión, pero igualmente los detallo aquí:

1. Descargar la extensión [aquí][extension].
2. Copiar la carpeta `admin` y `catalog` a la raíz de tu carrito de compras.
3. Copiar el archivo `vpos_plugin.php` dado por Alignet a la carpeta `vpos`.
4. Pueden copiar las llaves en la carpeta `keys` dentro de `vpos`.
5. Instalar la extensión en el Panel de Administración del Opencart.
6. Configurarla según los parámetros provistos por Alignet.

Las rutas del plugin y de las llaves tienen que ser absolutas. Pueden usar la variable global `$_SERVER[‘DOCUMENT_ROOT’]` para obtener la ruta raiz de su sitio web.

Si tienen dudas con la instalación pueden preguntar aquí.

[opencart]: http://www.opencart.com/
[extensiones]: http://www.opencart.com/index.php?route=extension/extension
[alignet]: http://www.alignet.com/
[extension]: http://www.opencart.com/index.php?route=extension/extension/info&extension_id=8710
