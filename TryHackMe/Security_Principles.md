# Principios de Seguridad

## Introduccion

Se presentan los temas que se abordaran, como la triada CID y DAD, modelos de seguridad como Bell-LaPadula, principios de seguridad como la defensa en profundidad, el modelo zero trust o el modelo trust but verify, norma ISO/IEC 19249, diferencias entre vulnerabilidad, amenaza y riesgo.

## CIA

Cuando se quiere evaluar la seguridad de un sistema, hay que pensar en términos de la tríada de la seguridad: confidencialidad, integridad y disponibilidad.

La **confidencialidad** garantiza que solo las personas o destinatarios previstos puedan acceder a los datos.  
La **integridad** tiene como objetivo garantizar que los datos no puedan ser alterados; además, podemos detectar cualquier alteración si se produce.  
La **disponibilidad** tiene como objetivo garantizar que el sistema o servicio esté disponible cuando sea necesario.

Mas alla de la triada CIA:

**Autenticidad**: Auténtico significa que no es fraudulento ni falso. La autenticidad consiste en garantizar que el documento, archivo o dato procede de la fuente que se afirma.  
**No repudio**: repudiar significa negarse a reconocer la validez de algo. El no repudio garantiza que la fuente original no pueda negar que es la fuente de un documento, archivo o dato concreto. Esta característica es indispensable para diversos ámbitos, como las compras, el diagnóstico de pacientes y la banca.

En 1998, Donn Parker propuso el hexágono de Parker, un conjunto de seis elementos de seguridad. Son los siguientes:

Disponibilidad
Utilidad
Integridad
Autenticidad
Confidencialidad
Posesión

Utilidad:se centra en la utilidad de la información. Por ejemplo, un usuario podría haber perdido la clave de descifrado para acceder a un ordenador portátil con almacenamiento cifrado. Aunque el usuario todavía tiene el ordenador portátil con sus discos intactos, no puede acceder a ellos. En otras palabras, aunque sigue estando disponible, la información se encuentra en un formato que no es útil, es decir, no tiene utilidad.  
Posesión: este elemento de seguridad requiere que protejamos la información contra la apropiación, copia o control no autorizados. Por ejemplo, un adversario podría llevarse una unidad de copia de seguridad, lo que significa que perderíamos la posesión de la información mientras él tenga la unidad. Alternativamente, el adversario podría lograr cifrar nuestros datos utilizando ransomware, lo que también conduciría a la pérdida de la posesión de los datos.

### Pregunta
Haga clic en «Ver sitio» y responda las cinco preguntas. ¿Cuál es la bandera que obtuvo al final?  
Respuesta: THM{CIA_TRIAD}

## DAD

Lo contrario de la tríada CIA sería la tríada DAD: divulgación, alteración y destrucción.

La **divulgación** es lo contrario de la confidencialidad. En otras palabras, la divulgación de datos confidenciales sería un ataque a la confidencialidad.
La **alteración** es lo contrario de la integridad. Por ejemplo, la integridad de un cheque es indispensable.
La **destrucción/denegación** es lo contrario de la disponibilidad.

Proteger la confidencialidad y la integridad al extremo puede restringir la disponibilidad, y aumentar la disponibilidad al extremo puede dar lugar a la pérdida de confidencialidad e integridad. La buena aplicación de los principios de seguridad requiere un equilibrio entre los tres.

### Pregunta
El atacante logró acceder a los registros de los clientes y los publicó en Internet. ¿Qué tipo de ataque es este?  
Respuesta: Disclosure

## Conceptos fundamentales de los modelos de seguridad

¿cómo podemos crear un sistema que garantice una o más funciones de seguridad? La respuesta estaría en el uso de modelos de seguridad.  
Presentaremos tres modelos de seguridad fundamentales:  
Modelo Bell-LaPadula  
Modelo de integridad Biba  
Modelo Clark-Wilson  

### Modelo Bell-LaPadula

El modelo Bell-LaPadula tiene como objetivo lograr la confidencialidad mediante la especificación de tres reglas:

Propiedad de seguridad simple: esta propiedad se conoce como «no lectura ascendente» y establece que un sujeto con un nivel de seguridad inferior no puede leer un objeto con un nivel de seguridad superior. Esta regla impide el acceso a información confidencial por encima del nivel autorizado.  
Propiedad de seguridad estrella: esta propiedad se conoce como «no escribir hacia abajo»; establece que un sujeto con un nivel de seguridad superior no puede escribir en un objeto con un nivel de seguridad inferior. Esta regla impide la divulgación de información confidencial a un sujeto con un nivel de seguridad inferior.  
Propiedad de seguridad discrecional: esta propiedad utiliza una matriz de acceso para permitir operaciones de lectura y escritura. En la tabla siguiente se muestra un ejemplo de matriz de acceso que se utiliza junto con las dos primeras propiedades.

El modelo Bell-LaPadula tiene ciertas limitaciones. Por ejemplo, no fue diseñado para gestionar el intercambio de archivos.

### Modelo Biba

El modelo Biba tiene como objetivo lograr la integridad mediante la especificación de dos reglas principales:

Propiedad de integridad simple: esta propiedad se conoce como «no leer hacia abajo»; un sujeto con mayor integridad no debe leer de un objeto con menor integridad.  
Propiedad de integridad estrella: esta propiedad se conoce como «no escribir hacia arriba»; un sujeto con menor integridad no debe escribir en un objeto con mayor integridad.

Estas dos propiedades se pueden resumir como «lectura ascendente, escritura descendente». Esta regla contrasta con el modelo Bell-LaPadula, lo que no debería sorprender, ya que uno se ocupa de la confidencialidad y el otro de la integridad.

El modelo Biba adolece de varias limitaciones. Un ejemplo es que no gestiona las amenazas internas.

### Modelo Clark-Wilson

El modelo Clark-Wilson también tiene como objetivo lograr la integridad mediante el uso de los siguientes conceptos:

Elemento de datos restringido (CDI): se refiere al tipo de datos cuya integridad queremos preservar.
Elemento de datos sin restricciones (UDI): se refiere a todos los tipos de datos que no son CDI, como las entradas del usuario y del sistema.
Procedimientos de transformación (TP): estos procedimientos son operaciones programadas, como la lectura y la escritura, y deben mantener la integridad de los CDI.
Procedimientos de verificación de la integridad (IVP): estos procedimientos comprueban y garantizan la validez de los CDI.

Solo hemos tratado tres modelos de seguridad. Hay muchos otros modelos de seguridad. Algunos ejemplos son:

Modelo de Brewer y Nash.
Modelo de Goguen-Meseguer.
Modelo de Sutherland.
Modelo de Graham-Denning.
Modelo de Harrison-Ruzzo-Ullman.

### Pregunta
Haga clic en «Ver sitio» y responda a las cuatro preguntas. ¿Cuál es la bandera que ha obtenido al final?  
Respuesta: THM{SECURITY_MODELS}

## Defensa en profundidad
Se refiere a la defensa multinivel de añadir multiples capas de seguridad, por ejemplo:

Usted tiene un cajón con llave donde guarda sus documentos importantes y sus objetos de valor. La habitación correspondiente estuviera cerrada con llave, que la puerta principal del apartamento estuviera cerrada con llave, que la puerta del edificio estuviera cerrada con llave e incluso quizá querríamos instalar algunas cámaras de seguridad por el camino. Aunque estos múltiples niveles de seguridad no pueden detener a todos los ladrones, bloquearían a la mayoría y ralentizarían a los demás.

## ISO/EAC 12249

La Organización Internacional de Normalización (ISO) y la Comisión Electrotécnica Internacional (IEC) han creado la norma ISO/IEC 19249.
Que enumera cinco principios arquitectónicos:

Separación de dominios: cada conjunto de componentes relacionados se agrupa como una única entidad.  
Capas: cuando un sistema se estructura en muchos niveles o capas abstractas, es posible imponer políticas de seguridad en diferentes niveles; además, sería factible validar el funcionamiento.  
Encapsulación: en la programación orientada a objetos (OOP), ocultamos las implementaciones de bajo nivel y evitamos la manipulación directa de los datos de un objeto proporcionando métodos específicos para ese fin.
Redundancia: este principio garantiza la disponibilidad y la integridad.  
Virtualización: El concepto de virtualización consiste en compartir un único conjunto de hardware entre varios sistemas operativos.

La norma ISO/IEC 19249 enseña cinco principios de diseño:

El principio del privilegio mínimo enseña que se debe proporcionar la menor cantidad de permisos posibles para que alguien realice su tarea y nada más.  
Minimización de la superficie de ataque: todos los sistemas tienen vulnerabilidades que un atacante podría utilizar para comprometerlos. Algunas vulnerabilidades son conocidas, mientras que otras aún no se han descubierto. Estas vulnerabilidades representan riesgos que debemos intentar minimizar.  
Validación centralizada de parámetros: Muchas amenazas se deben a que el sistema recibe entradas, especialmente de los usuarios. Las entradas no válidas pueden utilizarse para explotar vulnerabilidades del sistema, como la denegación de servicio y la ejecución remota de código. Por lo tanto, la validación de parámetros es un paso necesario para garantizar el estado correcto del sistema. Teniendo en cuenta el número de parámetros que maneja un sistema, la validación de los mismos debe centralizarse en una biblioteca o sistema.  
Servicios de seguridad generales centralizados: como principio de seguridad, debemos aspirar a centralizar todos los servicios de seguridad.  
Preparación para el manejo de errores y excepciones: siempre que construimos un sistema, debemos tener en cuenta que se producen y se producirán errores y excepciones.

### Preguntas

¿Qué principio está aplicando cuando apaga un servidor inseguro que no es crítico para el negocio?  
Respuesta: 2.  

Su empresa ha contratado a un nuevo representante de ventas. ¿Qué principio están aplicando cuando le piden que les dé acceso solo a los productos y precios de la empresa?  
Respuesta: 1.

Mientras leía el código de un cajero automático, observó una gran cantidad de código para manejar situaciones inesperadas, como la desconexión de la red y los cortes de energía. ¿Qué principio están aplicando?
Respuesta: 5.

## Confianza cero frente a confianza pero verificación

Dos principios de seguridad que nos interesan en relación con la confianza:

onfía, pero verifica: este principio nos enseña que siempre debemos verificar, incluso cuando confiamos en una entidad y en su comportamiento.  
Confianza cero: este principio trata la confianza como una vulnerabilidad y, en consecuencia, se ocupa de las amenazas relacionadas con el personal interno.

La microsegmentación es una de las implementaciones utilizadas para la confianza cero. Se refiere al diseño en el que un segmento de red puede ser tan pequeño como un solo host. Además, la comunicación entre segmentos requiere autenticación, comprobaciones de la lista de control de acceso y otros requisitos de seguridad.
Hay un límite en cuanto a la medida en que podemos aplicar la confianza cero sin afectar negativamente a un negocio; sin embargo, esto no significa que no debamos aplicarla siempre que sea factible.

## Amenaza frente a riesgo

Hay tres términos que debemos tener en cuenta para evitar cualquier confusión.

Vulnerabilidad: Vulnerable significa susceptible de sufrir ataques o daños. En seguridad de la información, una vulnerabilidad es una debilidad.  
Amenaza: Una amenaza es un peligro potencial asociado a esta debilidad o vulnerabilidad.  
Riesgo: El riesgo se refiere a la probabilidad de que un agente malicioso aproveche una vulnerabilidad y al consiguiente impacto en el negocio.   
