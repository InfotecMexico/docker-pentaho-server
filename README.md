# Docker Pentaho Server

**Que es Pentaho Server?**
Se trata de un software de inteligencia de negocios de código abierto escrito en java que permite, entre otras cosas, ejecutar componentes de inteligencia de negocios como:
- Análisis dinámicos u OLAP (mediante Mondrian como motor y gran cantidad de herramientas gráficas como Pivot4J)
- Reportes (mediante Pentaho Reporting)
- Procesos de Integración de Datos (mediante Pentaho Data Integration)
- Tableros de mando (mediante CDF/CDE/CDA)
- etc
Cabe aclarar que Pentaho Server es uno de los componentes de la Suite Pentaho (ahora Hitachi Ventara), algunos de los otros componetes como Pentaho reporting y Pentaho Data Integration son independientes y poseen una interface gráfica de tipo desktop, aunque Pentaho Data Integration posee una excelente interface web llamada [WebSpoon](https://github.com/HiromuHota/webspoon-docker)  

**Crear la imagen**
Una vez clonado este repositorio deberá:
- Descargar la versión 8 del JDK de Oracle y asegurate que poseá este nombre: *jdk-8-linux-x64.tar.gz* cuando lo descargues, se puede encontrar [aquí](https://www.oracle.com/java/technologies/javase/javase8u211-later-archive-downloads.html)
- Descargar Pentaho Server CE, asegurate que posea el nombre *pentaho-server-ce.zip* cuando lo descargues, puedes utilizar este [enlace](https://razaoinfo.dl.sourceforge.net/project/pentaho/Pentaho%209.0/server/pentaho-server-ce-9.0.0.0-423.zip) 
- Finalmente, crear la imagen:

```
docker build -t pentahoserver .
```

**Crear un contenedor**
```
docker run --name mipentahoserver -d -p 8080:8080 pentahoserver
```
Puedes ver el log de tu contener de la siguiente manera:
```
docker logs mipentahoserver
```
Finalmente podrás disfrutar de tu Pentaho server accediendo a la url: *http://localhost:8080/pentaho* 

**Agradecimientos**
- La instalación del JDK se realiza con una pequeña modificación del script creado por [chrishantha](https://github.com/chrishantha/install-java)
- A [Ubuntu Peronista](https://ubuntuperonista.blogspot.com/) por sus constantes aportes a la causa.


**TODO**
- Ejemplo de cambio de Time Zone
- Ejemplo de como agregar nuevos controladores JDBC
- Agregar versiones anteriores

***

**Licencia**

Creado por Mariano Alberto García Mattío en 2020

Licensed under the Apache License, Version 2.0
