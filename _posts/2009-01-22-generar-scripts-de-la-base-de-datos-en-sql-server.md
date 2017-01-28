---
layout: post
title: Generar Scripts de la Base de Datos en SQL Server
date: '2009-01-22 04:13:00 -0600'
categories: tutoriales
published: true
---

¿Alguna vez han necesitado generar un script de la base de datos en SQL Server ? No me refiero a solo el esquema, ya que esto se puede hacer fácilmente en [SQL Server 2005][sql-server], sino también a los datos.

Se que es posible crear un respaldo de la base de datos con toda esta información, que es una de las opciones mas utilizadas, pero todos sabemos que el backup solo puede ser leído y restaurado en un servidor MS SQL, y realmente no podemos leer el contenido de este. Pero que tal si quisieramos tener también un respaldo del esquema y además de todos los datos, procedimientos almacenados, funciones y todos los objetos de la base de datos, pero en formato [SQL][sql]. Para el desarrollo de una aplicación necesitaba solamente la estructura de algunas tablas, lo cual se solucionaba con el asistente que facilita SQL Server 2005, pero además de esto también ocupaba todos los datos de estas tablas. Me extraño que el [Management Studio][studio] no tuviera esta opción, ya que me parece algo sumamente necesario, que puede ser de gran ayuda para realizar migraciones o tener respaldos de ciertos scripts en la base datos. Además, en otros gestores de base de datos como [MySQL][mysql] realizar esto es una tarea muy básica y sencilla!

Pues mis sueños frustrados por encontrarle mas pulgas a los productos Microsoft no se hicieron realidad…!, ya que SQL Server si posee una herramienta para realizar esta tarea, solamente que no viene incluida en la Base de Datos, ya que es necesario descargarla por separado (como era de esperarse…). El [SQL Server Database Publishing Wizard][wizard] nos permite generar scripts completos de todos los objetos de la base de datos y copiarlos o guardarlos en archivos.

Por medio de un asistente podemos elegir si deseamos generar los scripts solamente del esquema, datos, procedimientos almacenados, funciones, etc. El asistente es muy intuitivo y fácil de utilizar, además se integra fácilmente con el Management Studio, Visual Studio 2005 o Visual Web Developer 2005.

Funciona perfectamente en SQL Server 2000/2005/2008. Pueden descargarlo en la [pagina oficial][wizard], y lo mejor es que es gratuito! (aunque no lo crean,…). En definitiva es una herramienta necesaria y recomendada para cualquier desarrollador o administrador de base de datos.

[sql-server]: http://www.microsoft.com/latam/sql/
[sql]: http://www.w3schools.com/sql/default.asp
[studio]: http://www.microsoft.com/downloads/details.aspx?familyid=C243A5AE-4BD1-4E3D-94B8-5A0F62BF7796&displaylang=es
[mysql]: http://www.mysql.com/
[wizard]: http://www.microsoft.com/downloads/details.aspx?familyid=56E5B1C5-BF17-42E0-A410-371A838E570A&displaylang=en
