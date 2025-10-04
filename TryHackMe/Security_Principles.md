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

## Respuesta ante incidentes

Los responsables de la respuesta ante incidentes responden de forma productiva y eficaz a las brechas de seguridad. Sus responsabilidades incluyen la creación de planes, políticas y protocolos que las organizaciones deben aplicar durante y después de los incidentes.  
Sus responsabilidades son:  
1. Desarrollar y adoptar un plan de respuesta a incidentes exhaustivo y viable.
2. Mantener sólidas prácticas de seguridad y apoyar las medidas de respuesta a incidentes.
3. Elaborar informes tras los incidentes y prepararse para futuros ataques, teniendo en cuenta las lecciones aprendidas y las adaptaciones que se deben realizar a partir de los incidentes.

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
