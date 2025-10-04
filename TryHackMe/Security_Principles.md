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

## Examinador forense digital

Los detectives de la ciberseguridad, se centran en recopilar y analizar pruebas para ayudar a resolver delitos: acusar a los culpables y exonerar a los inocentes, o tambien, utilizan sus habilidades forenses para analizar incidentes, como infracciones de políticas.  
Responsabilidades:  
1. Recopilar pruebas digitales respetando los procedimientos legales.
2. Analizar las pruebas digitales para encontrar respuestas relacionadas con el caso.
3. Documentar hallazgos e informar sobre el caso.

## Analista de malware

Consiste en analizar programas sospechosos, descubrir qué hacen y redactar informes sobre sus hallazgos. A veces se denomina al analista de malware «ingeniero inverso», se deben tener solidos conocimientos en lenguajes de bajo nivel como c y ensamblador.  
Responsabilidaes:  
1. Realizar análisis estáticos de programas maliciosos, lo que implica ingeniería inversa.
2. Realizar análisis dinámicos de muestras de malware observando sus actividades en un entorno controlado.
3. Documentar y notificar todos los hallazgos.

## Pentester

La función de un pentester es comprobar la seguridad de los sistemas y el software de una empresa, lo que se consigue mediante intentos de descubrir fallos y vulnerabilidades a través de hacking sistematizado.  
Responsabilidades:  
1. Realizar pruebas en sistemas informáticos, redes y aplicaciones basadas en la web.
2. Llevar a cabo evaluaciones de seguridad, auditorías y análisis de políticas.
3. Evaluar e informar sobre los datos obtenidos, recomendando medidas para la prevención de ataques.

## Red Team
Los miembros del red team se encargan de poner a prueba las capacidades de detección y respuesta de la empresa.  
Esta función requiere imitar las acciones de los ciberdelincuentes, emular ataques maliciosos, mantener el acceso y evitar ser detectados.  
Responsabilidades:  
1. Emular el papel de un agente malicioso para descubrir vulnerabilidades explotables, mantener el acceso y evitar la detección.
2. Evaluar los controles de seguridad, la inteligencia sobre amenazas y los procedimientos de respuesta a incidentes de las organizaciones.
3. Evaluar e informar sobre los conocimientos adquiridos, con datos procesables para que las empresas eviten casos reales.

## Al finalizar, podremos resolver un quiz que nos indicara que rol en ciberseguridad se adapta mas a nosotros.
