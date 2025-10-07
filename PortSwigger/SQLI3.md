# 📚SQL injection attack, querying the database type and version on MySQL and Microsoft📚

## Conocimientos previos

El uso de burpsuite y su repetidor.

## Resolucion

Para poder resolver este laboratio, se usa una logica similar a la del laboratorio anterior, deberemos saber cuantas columnas tiene la base de datos, para esto, podemos usar la consulta ' ORDER BY 1#, si te diste cuenta, ahora es un simbolo de # y no -- para comentar lo que sigue en la consulta, la diferencia es que esta es la notacion mas segura para bases de datos de Microsoft o mySql, ten en cuenta que esto lo deberemos hacer en burpsuite, ya que depeondiendo el navegador y el js, nos puede tomar o no la consulta directamente sin burpsuite.

al realizar las pruebas, podremos ver como la base de datos tambien tiene dos columnas, entonces como siguiente paso es adaptar nuestra consulta de version en base a la cantidad de columnas que tiene nuestra base de datos, en el cheat sheet nos dan la siguiente consulta:  SELECT @@version, para poder usarla correctamente en este lab, deberemos usar UNION, seguido de la consulta SELECT @@version, desde aqui es donde varia segun la cantidad de columnas, ya que deberemos añadir tantos null como columnas tenga la base de datos, terminando con el simbolo # para comentar lo que sigue despues de nuestra inyeccion.

Nos quedaria asi ' UNION SELECT @@version, null#, al ingresar esta inyeccion en burpsuite, habremos completado este laboratorio.


