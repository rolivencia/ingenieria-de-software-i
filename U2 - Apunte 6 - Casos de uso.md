# Casos de uso: para qué sirven y su rol en la elicitación y documentación de requerimientos

### Resumen introductorio basado en Alistair Cockburn, *The Mini-Book on Use Cases* (2025)

> **Nota sobre las fuentes.** Salvo indicación contraria, todo lo que sigue se apoya en Cockburn (2025) y su obra de referencia *Writing Effective Use Cases* (2000). La definición fundacional pertenece a **Ivar Jacobson**, inventor de la técnica a fines de la década de 1980. La notación gráfica UML (diagrama de casos de uso) que aparece más adelante **no** proviene del mini-libro —que es deliberadamente textual—, sino de la tradición UML / Proceso Unificado (Jacobson, Booch & Rumbaugh, 1999); se la presenta como complemento y se la señala explícitamente como tal.

---

## 1. Qué es un caso de uso

La definición de Jacobson, que Cockburn adopta sin reservas, puede formularse así:

> Un caso de uso es **el conjunto de todas las formas de usar un sistema para alcanzar la meta de un usuario determinado.**

Visto de cerca, un caso de uso es un **colector de escenarios** unidos por una **meta común del usuario**. Esa meta da nombre al caso de uso y se muestra *cumplida* en algunos escenarios y *fallida* en otros. El caso de uso reúne todos esos escenarios —el camino feliz y todas sus variantes y fracasos— bajo un único título.

Cockburn agrega que, según para qué lo necesitemos, un caso de uso puede entenderse de tres maneras complementarias:

- **Como especificación del comportamiento de un sistema.** Captura *todos* los requerimientos de comportamiento, pero *solo* esos: muestra las interacciones entre el sistema y los actores de su entorno, no el detalle de los datos, ni la interfaz de usuario, ni el rendimiento o la seguridad; cuestiones que pueden ser abordadas en una especificación a manera de apéndice pero no forman parte del concepto central de un caso de uso.
- **Como descripción de un proceso.** Es la única notación *textual* de descripción de procesos de uso extendido (las demás —diagramas de flujo, diagramas de actividad UML— son gráficas). Sirve para cualquier proceso, no solo de software.
- **Como formato de escritura para comportamientos con ramificación.** La información tiene forma: cuando hay un flujo con cierta cantidad de ramificaciones (pero no demasiadas), encaja con naturalidad en un caso de uso. Cuando la ramificación es excesiva, conviene una tabla o una máquina de estados.

---

## 2. Para qué sirven: los cuatro valores

Cockburn ordena la utilidad de los casos de uso en cuatro valores, **en orden de importancia decreciente**. La inversión respecto de la intuición habitual es deliberada y es la tesis central del libro:

1. **Alinear a toda la organización sobre qué se va a construir.** Este es el valor *más alto*. Patrocinadores, gerentes, analistas, líderes técnicos, programadores, testers y formadores leen al menos los casos de uso de alto nivel y comparten una misma visión de lo que se entregará. Las desalineaciones detectadas tarde son el error más caro de un proyecto.
2. **Servir de andamiaje para la investigación temprana.** Los casos de uso permiten a los analistas pensar y explorar las **condiciones excepcionales y los casos de borde** *antes* que los desarrolladores y testers. Cockburn afirma que es la única técnica que conoce con esta propiedad.
3. **Aportar una especificación detallada** a desarrolladores y testers: el contexto de cada escenario y cómo debe resolverse cada condición alternativa.
4. **Ofrecer una estructura de gestión del proyecto.** La sola *lista de nombres* de los casos de uso funciona como índice de todo lo que hay que construir: se le pueden asociar cronograma, costo, riesgo y asignaciones de equipo, con independencia del contenido de cada caso.

> **Corolario incómodo pero central.** Cuanto más detalle se vuelca dentro de un caso de uso, *menor* es su valor total, porque deja de ser legible y entonces nadie lo lee —y se pierde el primer valor, la alineación—. El valor de un caso de uso no se relaciona con su extensión ni con su complejidad.

---

## 3. Los casos de uso en el ciclo de vida: elicitación y documentación de requerimientos

Dentro del ciclo de vida del software, los casos de uso se ubican en la fase de **requerimientos**: tanto en la **elicitación** (descubrir qué necesita el sistema) como en la **documentación** (registrarlo de forma comunicable y verificable). Su contribución a cada tarea es distinta:

**En la elicitación.** El caso de uso es una herramienta de descubrimiento, no solo de registro. Al obligar a escribir primero el escenario principal de éxito y luego enumerar *todas* las condiciones que podrían provocar un comportamiento distinto, hace aflorar requerimientos que de otro modo permanecerían ocultos hasta la programación o las pruebas. El propio Cockburn ilustra esto con la extensión "6b" de un caso real de seguros: una condición sutil (vencimiento de un plazo con datos mínimos sin completar) que casi ninguna otra técnica habría detectado a tiempo. Además:

- Exige **nombrar a todos los actores secundarios** y los servicios que prestan, lo que revela interfaces externas que deben investigarse y deja claro qué hay que construir y qué ya existe.
- Requiere **escribir desde la perspectiva del usuario** —no desde dentro de la "caja" del sistema—, lo que permite preguntar a usuarios y directivos: *"¿Es este el sistema que quieren? ¿Está completo, sin huecos críticos?"*. Solo ellos pueden responder eso, de modo que el material debe ser legible para ellos.

**En la documentación.** El conjunto terminado de casos de uso muestra *todas* las acciones que el sistema deberá ejecutar bajo *todas* las circunstancias. Para lograrlo, cada caso debe nombrar explícitamente cada condición que enfrentará y cómo manejarla, y cada sistema de back-end con el que interactuará. Dos precisiones importantes que Cockburn subraya:

- Un caso de uso especifica las **acciones del sistema por todos sus lados**, pero **no especifica los datos en detalle ni la interfaz de usuario**. Identifica los datos solo a baja precisión ("el usuario proporciona sus datos personales").
- El resto de los requerimientos —datos en detalle, seguridad, rendimiento, UI— se captura en **documentos laterales** enlazados, para preservar la legibilidad del caso de uso. Un error frecuente es escribir muy bien los casos de uso y olvidar capturar todo lo demás.

> La participación conjunta de **usuarios de negocio y miembros del equipo técnico** en la escritura es indispensable: ningún grupo por separado logra capturarlos correctamente, porque los casos nombran tanto las metas del negocio como los sistemas de back-end.

---

## 4. El artefacto resultante: el modelo de casos de uso

Al cerrar la fase, el artefacto producido es el **modelo de casos de uso**, que se materializa en dos formas complementarias:

**a) Las especificaciones (el corazón de la técnica).** Es el texto estructurado de cada caso de uso: título, encabezado (sistema, actor primario, nivel de meta), escenario principal de éxito y extensiones. Aquí reside, según Cockburn, el verdadero valor: un caso de uso típico ocupa media página, a lo sumo una; muy pocos llegan a dos. La legibilidad no es un lujo, es la condición que habilita el primer valor (la alineación).

**b) Los diagramas (índice y mapa, no contenido).** Cockburn ofrece la **vista "velero"** (*sailboat*): un grafo de anidamiento donde un caso de uso de tope conecta los de nivel cometa (*kite*), estos se abren en casos de nivel del mar (*sea-level*), y por debajo aparecen los de nivel pez (*fish*). El diagrama sirve como **tabla de contenidos** y mapa de relaciones, no como portador del comportamiento. La notación gráfica más conocida —el **diagrama de casos de uso UML** con actores, elipses y límite del sistema— pertenece a la tradición UML / Proceso Unificado (Jacobson, Booch & Rumbaugh, 1999) y cumple ese mismo rol de índice visual; las reglas para confeccionarlo se detallan en el documento complementario de reglas.

> **Idea-fuerza para los estudiantes.** El diagrama responde *"¿qué servicios ofrece el sistema y a quién?"*. La especificación responde *"¿qué hace exactamente el sistema en cada situación, incluidos los fracasos?"*. El modelo de casos de uso necesita ambas, pero el peso del comportamiento recae en la especificación textual. Un diagrama elaborado con especificaciones pobres es un mapa sin territorio.

---

## 5. Síntesis

Los casos de uso son, ante todo, un **instrumento de alineación y descubrimiento** durante la fase de requerimientos. Capturan todo el comportamiento del sistema —y solo el comportamiento— de una forma lo bastante legible como para que toda la organización entienda qué se va a construir y pueda detectar errores antes de programar. Su producto, el modelo de casos de uso, combina especificaciones textuales (donde vive el comportamiento, con sus escenarios y extensiones) y diagramas (que indexan y mapean el conjunto). La regla maestra que atraviesa todo el libro: **sacrificar la perfección en favor de la legibilidad**, porque un caso de uso aproximado que se lee vale más que uno perfecto que nadie abre.

---

## Referencias

- Cockburn, A. (2025). *The Mini-Book on Use Cases* (The Simplifying Series). Humans and Technology Press.
- Cockburn, A. (2000). *Writing Effective Use Cases*. Addison-Wesley.
- Cockburn, A. (2024). *Unifying User Stories, Use Cases, Story Maps*.
- Jacobson, I., Booch, G. & Rumbaugh, J. (1999). *The Unified Software Development Process*. Addison-Wesley.
- Jacobson, I. & Cockburn, A. (2024). *Use-Case Foundation* (documento de acuerdo conceptual). https://alistaircockburn.com/Articles/Use-Case-Foundation-Ivar-Alistair
