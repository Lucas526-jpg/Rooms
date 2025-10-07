# SQL injection attack, querying the database type and version on Oracle
## Conocimientos previos

-Uso de burpsuite.  
-comandos de sqli basicos para ver cantidad de columnas, tipo de datos de columna.

## Resolucion

Al inicar el laboratorio. Podemos confirmar que la pagina es vulnerable a SQLI ya que al seleccionar una etiqueta de filtrado, si ponemos una comilla simple ( ' ) al final de la url o en burpsuite, podremos ver como la pagina da error, advirtiendo que es vulnerable.

Para empezar a resolver el lab, debemos identificar cual es nuestro objetivo, como nos dice en la parte superior de la web vulnerable, debemos conseguir que la base de datos nos devuelva la siguiente cadema: 'Oracle Database 11g Express Edition Release 11.2.0.2.0 - 64bit Production, PL/SQL Release 11.2.0.2.0 - Production, CORE 11.2.0.2.0 Production, TNS for Linux: Version 11.2.0.2.0 - Production, NLSRTL Version 11.2.0.2.0 - Production', para esto, PortSwigger nos da un comando en el apartado "pistas" que deberemos usar que es: UNION SELECT 'abc' FROM dual, pero como lo usamos, bueno, deberas investigar un poco por tu cuenta para aprender o... seguir leyendo.

Para poder usar UNION SELECT, deberemos saber dos cosas:

1. Numero de columnas.
3. Tipo de datos de las columnas

Para hacer esto, en la web vulnerable, al seleccionar una etiqueta de filtrado veremos como se muestra en la url, a la par de esa etiqueta en la url pondremos el siguiente comando ' ORDER BY 1--, este comando dara error cuando pongamos la cantidad de columnas de la base de datos, cuando nos de error, la cantidad sera un numero menos del numero usado en el comando order by.

Usando el comando, podemos ver que el comando da un error en ORDER BY 3--, es decir, que la base de datos tiene 2 columnas.

Ahora para poder detectar el tipo de dato en las columnas, podemos usar el siguiente comando

