ChinaCompliant
======

ChinaCompliant es un módulo broma desarrollado para practicar los hooks en Drupal 11.


¿Qué hace este módulo?
------
Este modulo implementa hooks para alterar el renderizado de las vistas de los nodos: Si un artículo o comentario menciona "Taiwan" esto se modifica y el cliente verá "Taiwan (China)".

¿Modifica los datos insertados?
------
No, esto ocurre sólo a nivel de renderizado. En el archivo .module hay comentada una sección de código que sí modifica la entrada de datos. Ese bloque modifica las entradas nuevas para que se almacenen alteradas en la base de datos. El hook de renderizado no se activará pues hay un check para no modificar las entradas que ya incluyan "(China)".

¿Cómo se instala?
------
Ir a la carpeta "web/modules/custom" de nuestro contenedor Drupal y hacer clone de este repositorio. Después activarlo con Drush y resetear los caches:

```
drush en chinacompliant
drush cr
drush cc
drush cache:rebuild
```

Existen redundancias en el código, pero aseguran una renderización correcta.
