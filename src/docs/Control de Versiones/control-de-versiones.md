# Sistemas de Control de Versiones

## ¿Que es un sistema de control de versiones?

## Arquitecturas de almacenamiento

### Centralizados

Existe un repositorio centralizado de todo el código, del cual es responsable un único usuario (o conjunto de ellos). Se facilitan las tareas administrativas a cambio de reducir flexibilidad, pues todas las decisiones fuertes (como crear una nueva rama) necesitan la aprobación del responsable.

Ejemplos: CVS, Subversión o Team Foundation Server.

#### SubVersion
Apache Subversion  (abreviado frecuentemente como SVN, por el comando svn)

Es una herramienta de control de versiones open source basada en un repositorio cuyo funcionamiento se asemeja enormemente al de un sistema de ficheros. Es software libre bajo una licencia de tipo Apache/BSD.

Utiliza el concepto de revisión para guardar los cambios producidos en el repositorio. Entre dos revisiones solo guarda el conjunto de modificaciones (delta), optimizando así al máximo el uso de espacio en disco. 

**SVN** permite al usuario crear, copiar y borrar carpetas con la misma flexibilidad con la que lo haría si estuviese en su disco duro local. Dada su flexibilidad, es necesaria la aplicación de buenas prácticas para llevar a cabo una correcta gestión de las versiones del software generado.

### Distribuidos

Cada usuario tiene su propio repositorio. Los distintos repositorios pueden intercambiar y mezclar revisiones entre ellos. Es frecuente el uso de un repositorio, que está normalmente disponible, que sirve de punto de sincronización de los distintos repositorios locales. 

Ejemplos: Git y Mercurial.



#### Git

Git es un software de control de versiones, pensando en la eficiencia, la confiabilidad y compatibilidad del mantenimiento de versiones de aplicaciones cuando estas tienen un gran número de archivos de código fuente. 

Su propósito es llevar registro de los cambios en archivos de computadora incluyendo coordinar el trabajo que varias personas realizan sobre archivos compartidos en un repositorio de código.

##### Flujo de trabajo
 * **Master/Main:** Es la rama principal. Contiene el repositorio que se encuentra publicado en producción, por lo que debe estar siempre estable.
 * **Development:** Es una rama sacada de Master. Es la rama de integración, todas las nuevas funcionalidades se deben integrar en esta rama. Luego que se realice la integración y se corrijan los errores (en caso de haber alguno), es decir que la rama se encuentre estable, se puede hacer un merge de development sobre la rama Master.
 * **Features:** Cada nueva funcionalidad se debe realizar en una rama nueva, específica para esa funcionalidad. Estas se deben sacar de Development. Una vez que la funcionalidad esté desarrollada, se hace un merge de la rama sobre Development, donde se integrará con las demás funcionalidades.
 * **Hotfix:** Son errores de software que surgen en producción, por lo que se deben arreglar y publicar de forma urgente. Es por ello, que son ramas sacadas de Master. Una vez corregido el error, se debe hacer una unificación de la rama sobre Master. Al final, para que no quede desactualizada, se debe realizar la unificación de Master sobre Development.
 * **Release:** Las ramas de release apoyan la preparación de nuevas versiones de producción. Para ellos se arreglan muchos errores menores y se preparan adecuadamente los metadatos. Se suelen originar de la rama develop y deben fusionarse en las ramas master y develop.

##### Comandos comunes
* Git config
* Git init
* Git add
* Git commit
* Git log

 
 

 
 



