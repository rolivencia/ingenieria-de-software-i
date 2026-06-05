> Este apunte es una traducción del capítulo 2 del libro _The Essentials of Modern Software Engineering_ (2019), de Jacobson, I.; Lawson, B. et al.
>
> Para una mayor comprensión del contexto en el que es utilizada la figura del estudiante _Smith_, se recomienda la lectura del capítulo 1 del libro.

# 2. Ingeniería de Software: Métodos y Prácticas

En este capítulo presentamos cómo se organiza la forma de trabajar para desarrollar software y, en cierta medida, qué medios adicionales se necesitan (por ejemplo, notaciones para las especificaciones). En particular:

- describimos los desafíos de la ingeniería de software, abarcando una amplia gama de aspectos como la manera de proceder paso a paso, involucrar a las personas, los métodos y las prácticas;
- esbozamos varios conceptos clave de algunos métodos de ingeniería de software de uso común creados durante las últimas cuatro décadas (es decir, métodos en cascada, métodos de ciclo de vida iterativo, métodos estructurados, métodos de componentes y métodos ágiles); y
- describimos la motivación detrás de la iniciativa de crear el estándar Essence como un fundamento básico y extensible para la ingeniería de software.

Esto también llevará al lector, de manera breve, a través del desarrollo de la ingeniería de software.

## 2.1 Desafíos de la Ingeniería de Software

Desde la visión específica y unipersonal de la ingeniería de software de Smith, pasamos a adoptar una visión más amplia del mundo en este capítulo y en el siguiente. Retomaremos el recorrido de Smith en el Capítulo 4. Entre 2012 y 2014, *IEEE Spectrum* publicó una serie de blogs sobre contratiempos de TI (*IT hiccups*).[^1] Hay todo tipo de errores y meteduras de pata que ocurren en todo tipo de industrias; mencionamos aquí algunos.

- Según el *New Zealand Herald*, la fuerza policial del país, en febrero de 2014, pidió disculpas por haber enviado por correo más de 20.000 multas de tránsito a los conductores equivocados. Al parecer, la NZ Transport Agency, responsable de actualizar automáticamente los datos de los conductores y enviarlos a la policía, no lo hizo entre el 22 de octubre y el 16 de diciembre de 2013. Como resultado, las personas que habían vendido sus vehículos durante ese período de dos meses fueron multadas incorrectamente por infracciones cometidas por los nuevos propietarios u otras personas que conducían los vehículos. En Nueva Zelanda, a diferencia de los EE. UU., las matrículas generalmente permanecen en un vehículo durante toda su vida útil.[^2]

- El *Wisconsin State Journal* informó en febrero de 2013 que ciertos fallos (*glitches*) en el polémico sistema de nóminas y prestaciones de la Universidad de Wisconsin habían provocado pagos indebidos por US$ 1,1 millones, que la universidad probablemente terminaría teniendo que asumir. Esto ocurrió después de que una noticia del mes anterior indicara que los problemas con el sistema de nóminas de la Universidad de Wisconsin habían dado lugar a pagos indebidos por US$ 33 millones a lo largo de los dos años anteriores.[^3]

Este tipo de problemas resaltados parecen ser de los que podemos encontrar graciosos; sin embargo, no tienen nada de gracioso si uno resulta ser una de las víctimas. Lo más sorprendente es que el problema con estas situaciones es que pueden prevenirse, pero casi inevitablemente ocurren.

## 2.2 El Auge de los Métodos y Prácticas de la Ingeniería de Software

Así como hemos comprimido el recorrido de Smith, de joven estudiante a ingeniero de software experimentado, en unos pocos párrafos, intentaremos comprimir unos 50 años de ingeniería de software en unos pocos párrafos. Lo haremos con una perspectiva particular en mente: qué dio lugar al desarrollo de un terreno común en la ingeniería de software, el estándar Essence. En el Apéndice A hay disponible una descripción más general de esta historia.

Sin embargo, la complejidad de los programas de software no parecía ser la única causa raíz de la llamada "crisis del software". Los emprendimientos de software y el desarrollo de productos no se tratan solo de programar; también tienen que ver con muchas otras cosas, como entender qué programar, cómo planificar el trabajo, cómo liderar a las personas y lograr que se comuniquen y colaboren de manera eficaz.

Para los fines de esta discusión introductoria, definimos un **método** como aquello que brinda orientación para todas las cosas que se necesita hacer al desarrollar y mantener software. Para los productos comerciales, "todas las cosas" son muchas. Es necesario trabajar con clientes y usuarios para llegar a "el qué" que el sistema va a hacer para sus usuarios: los requisitos. Además, hay que diseñar, codificar y probar. No obstante, también hay que formar un equipo y ponerlo al día, asignarle trabajo y dotarlo de una forma de trabajar.

Estas cosas son en sí mismas "minimétodos" o lo que muchas personas hoy llamarían **prácticas**. Existen prácticas relacionadas con la solución, como trabajar con los requisitos, trabajar con el código y realizar pruebas. Existen prácticas relacionadas con el emprendimiento, como formar un equipo colaborativo y un emprendimiento eficiente, así como mejorar la capacidad de las personas y recopilar métricas. Y existen, por supuesto, prácticas relacionadas con el cliente, como asegurarse de que lo que se construye es lo que los clientes realmente quieren.

El descubrimiento interesante que hicimos hace más de una década fue que, aunque la cantidad de métodos en el mundo era enorme, parecía que todos esos métodos no eran más que composiciones de un conjunto mucho más pequeño de prácticas, quizás unos pocos cientos de prácticas en total. Las prácticas son lo que llamamos *reutilizables*, porque pueden usarse una y otra vez para construir diferentes métodos.

Para comprender cómo, como comunidad de ingeniería de software, hemos mejorado nuestro conocimiento en la materia, ofrecemos una descripción de los desarrollos históricos. Nuestro propósito con esta breve historia es facilitarle al lector la comprensión de por qué se desarrolló Essence.

### 2.2.1 Existen los Ciclos de Vida

Del enfoque *ad hoc* utilizado en los primeros años de la computación surgió el **método en cascada** alrededor de la década de 1960; en realidad, no se trataba de un único método, sino de toda una clase de métodos. Los métodos en cascada describen un proyecto de ingeniería de software como algo que atraviesa una serie de fases, tales como Requisitos, Diseño, Implementación (Codificación) y Verificación (es decir, pruebas y corrección de errores) (ver Figura 2.1).

<img width="600" height="428" alt="figura_2_1_ciclo_cascada" src="https://github.com/user-attachments/assets/02c3c448-4ad9-40fb-8c59-967b6eb8ffa4" />

> **[FIGURA 2.1: Ciclo de vida en cascada]**: _Diagrama lineal con las fases: Requisitos (R) → Diseño (D) → Implementación / Código (I) → Verificación / Prueba (V)_.

Si bien los métodos en cascada ayudaron a aportar cierta disciplina a la ingeniería de software, muchas personas intentaron seguir el modelo al pie de la letra, lo que causó problemas graves, especialmente en esfuerzos grandes y complejos. Esto se debía a que la ingeniería de software no es tan simple como indica esta representación lineal.

Una forma de describir los métodos en cascada es la siguiente: ¿qué se tiene una vez que se cree haber completado los requisitos? Algo escrito en "papel". (Puede que se haya usado una herramienta y creado una versión electrónica del "papel", pero la cuestión es que se trata solo de texto e imágenes). Pero, como no se ha utilizado, ¿se sabe con seguridad en este punto si son los requisitos correctos? No, no se sabe. Tan pronto como las personas empiezan a usar el producto desarrollado a partir de esos requisitos, casi siempre quieren cambiarlo.

De manera similar, ¿qué se tiene después de haber completado el diseño? ¿Más "papel" sobre lo que se cree que hay que programar? Pero ¿se está seguro de que es lo que el cliente realmente pretendía? No, no se está. Sin embargo, fácilmente se puede afirmar que se va en tiempo, porque simplemente se escribe menos y con menor calidad.

Incluso después de haber programado de acuerdo con el diseño, todavía no se sabe con seguridad. Sin embargo, todas las actividades realizadas no aportan prueba de que lo hecho sea correcto.

Ahora bien, puede que se sienta que se ha hecho el 80%. Lo único que queda es probar. En este punto, el emprendimiento casi siempre se desmorona, porque lo que hay que probar es demasiado grande para abordarlo como una sola pieza de trabajo. Es el código que proviene de todos los requisitos. Se creía que quedaba un 20%, pero ahora se siente que puede quedar un 80%. Este es un problema bien conocido y común de los métodos en cascada.

Hay algunas lecciones aprendidas. Creer que se pueden especificar todos los requisitos por adelantado es un mito en la gran mayoría de las situaciones actuales. Esta lección aprendida ha llevado a la popularidad de los métodos de ciclo de vida más iterativos. **Iterar** significa que se pueden especificar algunos requisitos y se puede construir algo que cumpla con esos requisitos, pero, tan pronto como se empieza a usar lo construido, se sabrá cómo mejorarlo un poco. Luego se pueden especificar algunos requisitos más y construir, y probar estos hasta tener algo que se sienta listo para liberar. Pero, para ganar confianza, hay que involucrar a los usuarios en cada iteración para asegurarse de que lo que se tiene aporta valor.

<img width="600" height="274" alt="figura_2_2_ciclo_iterativo" src="https://github.com/user-attachments/assets/5a99362d-d872-4239-9333-d6c06d694994" />

> **[FIGURA 2.2: Ciclo de vida iterativo]**
> *Diagrama con varias iteraciones a lo largo del tiempo (Iteración 1, Iteración 2, Iteración 3...), cada una conteniendo las fases R, D, I y V.*

Estas lecciones dieron origen, a finales de la década de 1980, a un nuevo enfoque de ciclo de vida llamado **desarrollo iterativo**, un ciclo de vida adoptado por el paradigma ágil que está de moda actualmente (ver Figura 2.2).

Surgieron nuevas prácticas. Las antiguas prácticas de gestión de proyectos pasaron de moda y se popularizaron las prácticas basadas en la metáfora iterativa. La práctica más prominente fue **Scrum**, que comenzó a popularizarse a finales de la década de 1990 y todavía sigue siendo muy popular. Discutiremos esto con mayor profundidad en la Parte III del libro.

### 2.2.2 Existen las Prácticas Técnicas

Desde los primeros días del desarrollo de software, hemos lidiado con cómo hacer las cosas correctas en nuestros proyectos. Originalmente, lidiábamos con la programación porque escribir código era, obviamente, lo que teníamos que hacer. Las demás cosas que necesitábamos hacer eran *ad hoc*. No teníamos directrices reales sobre cómo hacer los requisitos, las pruebas, la gestión de la configuración, la gestión de proyectos y muchas de estas otras cosas importantes.

Más tarde se popularizaron nuevas tendencias.

#### 2.2.2.1 La Era de los Métodos Estructurados

Desde finales de la década de 1960 hasta mediados de la de 1980, los métodos más populares separaban el software a desarrollar en las funciones a ejecutar y los datos sobre los que operarían dichas funciones: las funciones residiendo en un almacén de programas y los datos residiendo en un almacén de datos. Estos métodos no eran descabellados, porque las computadoras de esa época tenían un almacén de programas, para las funciones traducidas a código, y un almacén de datos. Mencionaremos solo dos de los métodos más populares de aquel momento: SADT (*Structured Analysis and Design Technique*, Técnica de Análisis y Diseño Estructurado) y SA/SD (*Structured Analysis / Structured Design*, Análisis Estructurado / Diseño Estructurado). Como estudiante, realmente no es necesario que aprendas nada más sobre estos métodos. Se usaban para todo tipo de ingeniería de software. No eran los únicos métodos existentes. Había una gran cantidad de métodos publicados disponibles y, alrededor de cada método, había personas que lo defendían con vehemencia. Fue en este momento de la historia de la ingeniería de software cuando comenzó la **guerra de los métodos**. Y, lamentablemente, ¡todavía no ha terminado!

<img width="600" height="404" alt="figura_2_3_elemento_sadt" src="https://github.com/user-attachments/assets/d6a5a8fa-758a-430a-ac44-d14d7b97d019" />

> **[FIGURA 2.3: Elemento básico de SADT]**
> *Diagrama de un bloque "Función" con: Entrada (Input) por la izquierda, Salida (Output) por la derecha, Control por arriba y Mecanismos (Mechanisms) por abajo.*

Cada método traía consigo una gran cantidad de prácticas, como requisitos, diseño, pruebas, gestión de defectos, y la lista sigue.

Cada uno tenía su propia notación de planos o diagramas para describir el software desde diferentes puntos de vista y con diferentes niveles de abstracción (por ejemplo, ver la Figura 2.3 sobre SADT). Se construyeron herramientas para ayudar a las personas a usar la notación y a llevar registro de lo que estaban haciendo. Algunas de estas prácticas y herramientas eran bastante sofisticadas. El valor de estos enfoques era, por supuesto, que lo que se diseñaba estaba cerca de la realización, de la máquina: se escribía el programa por separado de la forma en que se diseñaban los datos. Los problemas eran que los programas y los datos están muy interconectados, y muchos programas podían acceder a los mismos datos y modificarlos. Aunque se desarrollaron muchos sistemas exitosos aplicando este enfoque, hubo muchos más fracasos. Los sistemas eran difíciles de desarrollar y aún más difíciles de cambiar de forma segura, y eso se convirtió en el talón de Aquiles de esta generación de métodos.

#### 2.2.2.2 La Era de los Métodos de Componentes

El siguiente cambio de paradigma[^4] llegó a principios de la década de 1980 y tuvo su mejor momento hasta principios de la década de 2000.

En términos simples, un sistema de software dejó de verse como algo con dos partes principales: funciones y datos. En cambio, un sistema era un conjunto de elementos que interactuaban: los **componentes** (ver también el Recuadro 2.1). Cada componente tenía una interfaz que lo conectaba con otros componentes, y a través de esa interfaz se comunicaban mensajes. Los sistemas se desarrollaban descomponiéndolos en componentes, que colaboraban entre sí para implementar los requisitos del sistema. Lo que había dentro de un componente importaba menos, siempre que proporcionara las interfaces necesarias a los componentes que lo rodeaban. Dentro de un componente podía haber programa y datos, o clases y objetos, scripts, o código antiguo (a menudo llamado *código heredado* o *legacy*) desarrollado muchos años atrás. Los componentes siguen siendo la metáfora dominante detrás de la mayoría de los métodos modernos. Un desarrollo interesante de los componentes que se ha vuelto muy popular son los **microservicios**, que discutiremos en la Parte III.

> ### Recuadro 2.1 — El Cambio de Paradigma en Detalle
>
> Con más detalle, este cambio de paradigma se inspiró en una nueva metáfora de programación —la programación orientada a objetos— y el detonante fue el nuevo lenguaje de programación Smalltalk. Sin embargo, las ideas clave detrás de Smalltalk se derivaron de un lenguaje de programación anterior, Simula 67, lanzado en 1967. Smalltalk y Simula 67 eran fundamentalmente diferentes de las generaciones anteriores de lenguajes de programación, en el sentido de que todo el sistema de software era un conjunto de clases que abarcaban sus propios datos, en lugar de programas (subrutinas, procedimientos, etc.) que direccionaban tipos de datos en algún almacén de datos. La ejecución del sistema se llevaba a cabo mediante la creación de objetos usando las clases como plantillas, y estos objetos interactuaban entre sí intercambiando mensajes. Esto contrastaba marcadamente con el modelo anterior, en el que se creaba un proceso cuando se activaba el sistema, y ese proceso ejecutaba el código línea por línea, accediendo a los datos concretos del almacén de datos y manipulándolos. Una década más tarde, alrededor de 1990, un complemento a la idea de los objetos recibió amplia aceptación, inspirado en particular por Microsoft. Obtuvimos los componentes.

Con los componentes, evolucionó una familia de métodos completamente nueva. Los métodos antiguos, con sus prácticas, se consideraron pasados de moda y se descartaron. Lo que comenzó a evolucionar fueron, en muchos casos, prácticas similares con algunas diferencias significativas, pero con nueva terminología. A principios de la década de 1990, se publicaron unos 30 métodos de componentes distintos. Tenían mucho en común, pero era casi imposible encontrar las semejanzas, ya que cada autor de método creaba su propia terminología.

En la segunda mitad de la década de 1990, OMG (un organismo de estándares llamado *Object Management Group*) sintió que era hora de al menos estandarizar la forma de representar los dibujos de software, es decir, las notaciones utilizadas para desarrollar software. Esto llevó a la creación de un grupo de trabajo para impulsar el desarrollo de un nuevo estándar. El trabajo dio como resultado el **Lenguaje Unificado de Modelado** (UML; ver Figura 2.4), que se utilizará más adelante en el libro.

<img width="600" height="447" alt="figura_2_4_casos_de_uso_uml" src="https://github.com/user-attachments/assets/d7105f82-c129-4059-aa91-25f7eb650d00" />

> **[FIGURA 2.4: Un diagrama (de hecho, un diagrama de Casos de Uso) del estándar UML]**
> *Diagrama de casos de uso del dominio de telefonía, con actores como "Suscriptor que llama" (Calling Subscriber), "Suscriptor llamado" (Called Subscriber) y "Sistema de Facturación de Clientes" (Customer Billing System), y casos de uso como "Realizar llamada local" (Place Local Call), "Realizar llamada de larga distancia" (Place Long Distance Call), "Recuperar información de facturación del cliente" (Retrieve Customer Billing Information) y "Obtener historial de llamadas" (Get Call History).*

Este desarrollo básicamente acabó con todos los métodos salvo el Proceso Unificado (comercializado bajo el nombre de *Rational Unified Process*, RUP). El Proceso Unificado dominó el mundo de la ingeniería de software alrededor del año 2000. Nuevamente, un paso lamentable, porque muchos de los otros métodos tenían prácticas muy interesantes y valiosas que podrían haberse puesto a disposición además de algunas de las prácticas del Proceso Unificado. Sin embargo, el Proceso Unificado se puso de moda y todo lo demás se consideró pasado de moda y, más o menos, se desechó.

Con los años, llegaron muchas más prácticas técnicas además de las soportadas por los 30 métodos de componentes. Evolucionaron prácticas arquitectónicas más avanzadas, o conjuntos de prácticas, por ejemplo para la arquitectura empresarial (EA), la arquitectura orientada a servicios (SOA), la arquitectura de líneas de productos (PLA) y, más recientemente, prácticas de arquitectura para el *big data*, la nube, la internet móvil y la internet de las cosas (IoT). Por el momento, conviene ver estas prácticas como punteros a áreas de interés de la ingeniería de software en un alto nivel de abstracción: basta con decir que EA trataba sobre grandes sistemas de información para, por ejemplo, la industria financiera; SOA organizaba el software como un conjunto de paquetes de servicios posiblemente opcionales; y PLA era la contraparte de EA, pero para empresas de productos, por ejemplo en la industria de las telecomunicaciones o la defensa. Más importante es saber que, una vez más, nuevas metodologías crecieron como hongos alrededor de cada una de estas tendencias tecnológicas. Con cada nueva tendencia, los autores de métodos empezaban de nuevo y reinventaban la rueda. En lugar de "pararse sobre los hombros de gigantes",[^5] preferían pararse sobre los pies de otro autor. Redefinían terminología ya adoptada y la guerra de los métodos simplemente continuaba.

#### 2.2.2.3 La Era de los Métodos Ágiles

El movimiento ágil —a menudo llamado simplemente *ágil*— es ahora la tendencia más popular, adoptada por todo el mundo. A lo largo de la historia de la ingeniería de software, los expertos siempre han intentado mejorar la forma en que se desarrolla el software. El objetivo ha sido comprimir los plazos para satisfacer las demandas y realidades de negocio en constante cambio. Si lo ágil tuviera una fecha de inicio, se podría situar en el momento en que 17 reconocidos expertos de la industria se reunieron y redactaron las palabras del *manifiesto ágil*. Presentaremos el manifiesto en la Parte IV, junto con la forma en que Essence contribuye a lo ágil. Pero, por ahora, basta con decir que lo ágil involucra un conjunto de prácticas técnicas y relacionadas con las personas. Lo más importante es que lo ágil enfatiza una mentalidad innovadora, de modo que el movimiento ágil evoluciona continuamente sus prácticas.

Lo ágil ha hecho evolucionar las prácticas técnicas utilizadas con los componentes. Sin embargo, su éxito no provino de introducir muchas prácticas técnicas nuevas, aunque algunas prácticas nuevas —como la integración continua, el desarrollo guiado por backlog y la refactorización— se popularizaron con lo ágil. La **integración continua** sugiere que los desarrolladores integren varias veces al día su nuevo código con la base de código existente y lo verifiquen. El **desarrollo guiado por backlog** significa que el equipo mantiene un backlog (lista pendiente) de elementos de requisitos con los que trabajar en iteraciones futuras. Discutiremos esta práctica con más detalle cuando hablemos de Scrum en la Parte III. La **refactorización** consiste en mejorar continuamente el código existente, iteración tras iteración.

Lo ágil más bien simplificó lo que ya estaba en uso para ayudar a trabajar en un estilo iterativo y a entregar software liberable a lo largo de muchas iteraciones más pequeñas, o *sprints*, como los llama Scrum.

### 2.2.3 Existen las Prácticas de las Personas

Por extraño que parezca, los métodos que empleábamos en los primeros días no prestaban mucha atención a los factores humanos. Todos entendían, por supuesto, que el software era desarrollado por personas, pero se escribieron muy pocos libros o artículos sobre cómo lograr que las personas estuvieran motivadas y empoderadas para desarrollar software de calidad. Los libros de métodos más exitosos guardaban bastante silencio sobre el tema. Básicamente se asumía que, de una forma u otra, esta era tarea de la gerencia.

Sin embargo, esta suposición cambió drásticamente con los métodos ágiles. Antes, había una alta dependencia de las herramientas, de modo que el código pudiera generarse automáticamente a partir de documentos de diseño, como los diagramas UML. En consecuencia, el rol de los programadores quedaba degradado, y otros roles tenían más prestigio, como los de gerentes de proyecto, analistas y arquitectos. Con los métodos ágiles, la programación se revalorizó como un trabajo creativo. Los programadores, las personas que finalmente creaban el software funcional, fueron "ascendidos" y la codificación volvió a ser una tarea prestigiosa.

Con lo ágil evolucionaron muchas prácticas nuevas, por ejemplo, los equipos autoorganizados, la programación en pares y las reuniones diarias de pie (*daily standups*).

Un **equipo autoorganizado** está compuesto por miembros que son más generalistas que especialistas: la mayoría sabe programar, aunque algunos sean expertos. Es como un equipo de fútbol: todos saben patear la pelota, aunque algunos sean mejores anotando goles y otro sea mejor evitando que la pelota entre en el arco.

La **programación en pares** significa que dos programadores trabajan lado a lado desarrollando la misma pieza de código. Se espera que la calidad del código mejore y que el costo total se reduzca. Por lo general, uno de los dos es más sénior que el otro, así que esto también es una forma de mejorar la competencia del equipo.

La **reunión diaria de pie** (*daily standup*) es una práctica destinada a reducir los impedimentos que tienen los miembros del equipo, así como a mantener la motivación. Cada mañana, el equipo se reúne durante 15 minutos para repasar la situación de cada miembro: qué ha hecho y qué va a hacer. Cualquier impedimento se plantea, pero no se aborda durante la reunión. Los asuntos se discutirán en reuniones separadas. Esta práctica forma parte de la práctica de Scrum, que se discute en la Parte III.

Dado el impacto que lo ágil ha tenido en el empoderamiento de los programadores, es fácil entender por qué se ha vuelto muy popular. Además, dado el impacto positivo que lo ágil ha tenido en nuestro desarrollo de software, no cabe duda de que merece haberse convertido en el paradigma más reciente.

### 2.2.4 Consecuencias

Hay una guerra de los métodos en marcha ahí afuera. Comenzó hace 50 años y todavía continúa. En broma, podemos llamarla la *Guerra de los Cincuenta Años*, y todavía no hay tregua. De hecho, no hay señales de que vaya a detenerse por sí sola.

- Con cada cambio de paradigma importante —como el paso de los métodos estructurados a los métodos de componentes, y de estos últimos a los métodos ágiles—, la industria básicamente desecha todo lo que sabe sobre ingeniería de software y empieza de nuevo con una terminología que tiene poca relación con la anterior. Las prácticas antiguas se consideran irrelevantes y las nuevas se sobrevaloran (*hype*). Hacer esta transición de lo viejo a lo nuevo es extremadamente costoso para la industria del software, en forma de capacitación, *coaching* y cambio de herramientas.

- Con cada innovación técnica importante —por ejemplo, la computación en la nube— que requiere un nuevo conjunto de prácticas, los autores de métodos también "reinventan la rueda". Aunque los costos no son tan enormes como en el punto anterior, ya que algunos de los cambios no son fundamentales en todo lo que hacemos (no es un cambio de paradigma) y, por tanto, el impacto se limita a, por ejemplo, el desarrollo en la nube, sigue habiendo un desperdicio insensato.

- Dentro de cada tendencia de la ingeniería de software hay muchos métodos en competencia. Por ejemplo, ya en 1990 había unos 30 métodos orientados a objetos en competencia. Cuando se escribió este libro, había unos 10 métodos en competencia para escalar lo ágil a grandes organizaciones; algunos de los más famosos son SAFe (*Scaled Agile Framework*), DAD (*Disciplined Agile Delivery*), LeSS (*Large Scale Scrum*) y SPS (*Scaled Professional Scrum*). Por lo general, incluyen algunas prácticas básicas ampliamente utilizadas, como Scrum, historias de usuario o, alternativamente, casos de uso, e integración continua, pero el autor del método las ha "mejorado" —dicho sarcásticamente—. Hay reutilización de ideas, pero no reutilización del texto original, así que el inventor original de la práctica siente que ha sido despojado de su trabajo; no hay colaboración entre los autores de los métodos, sino que más bien están "en guerra" como marcas en competencia.

  Dentro de estos famosos métodos hay algunas prácticas, a menudo útiles, que son específicas de cada uno. El problema es que todos estos métodos son monolíticos, no modulares, lo que significa que no se pueden combinar fácilmente prácticas de diferentes métodos (*mix and match*). Si eliges uno, quedas más o menos atado a él. Esto no es lo que quieren los equipos, y ciertamente tampoco sus empresas. Es, por supuesto, lo que les gusta a la mayoría de los autores de métodos cuyo método es seleccionado, aunque nunca haya sido su intención.

Por lo general, todo método reconocido tiene un padre fundador, a veces más de uno. Si tiene éxito, este padre es elevado al estatus de gurú. El gurú dicta, más o menos, qué entra en su método. Así, una vez que has adoptado un método, tienes la sensación de estar en una *prisión de métodos* controlada por el gurú de ese método. Ivar Jacobson, junto con Philippe Kruchten, fue una vez uno de esos gurús que gobernaba la prisión del Proceso Unificado. Jacobson se dio cuenta de que esto era "la cosa más loca del mundo", una situación indigna de cualquier industria y, en particular, de una industria tan enorme como la del software. Para erradicar esas innecesarias guerras de métodos y prisiones de métodos, se fundó la iniciativa SEMAT (*Software Engineering Method and Theory*, Método y Teoría de la Ingeniería de Software).

## 2.3 La Iniciativa SEMAT

Al momento de escribir este libro, hay alrededor de 20 millones de desarrolladores de software[^6] en el mundo, y el número crece año tras año. Se puede estimar que existen más de 100.000 métodos distintos para desarrollar software, ya que básicamente cada equipo ha desarrollado su propia forma de trabajar, aunque no la haya descrito de manera explícita.

Con el tiempo, el número de métodos crece mucho más rápido que el número de prácticas reutilizables. No hay ningún problema con esto. De hecho, es lo que queremos que suceda, porque queremos que cada equipo u organización pueda establecer su propio método. El problema es que, hasta ahora, no hemos tenido los medios para hacerlo realmente. Hasta ahora, crear tu propio método ha invitado a los autores de métodos a reinventar todo lo que querían cambiar. Esto ha ocurrido porque no hemos tenido un terreno común sólido en el que todos estuviéramos de acuerdo para expresar nuestras ideas. No teníamos un vocabulario común para comunicarnos entre nosotros, y no teníamos un conjunto sólido de prácticas reutilizables a partir del cual pudiéramos empezar a crear nuestro propio método.

En 2009, varios líderes de la comunidad de ingeniería de software se reunieron, por iniciativa de Ivar Jacobson, para discutir el futuro de la ingeniería de software. A través de ello, comenzó la iniciativa SEMAT, fundada junto con otros dos líderes: Bertrand Meyer y Richard Soley.

El llamado a la acción de SEMAT de 2009 decía lo siguiente:

> La ingeniería de software se ve gravemente obstaculizada hoy por prácticas inmaduras. Los problemas específicos incluyen:
>
> - La prevalencia de modas más típicas de la industria de la moda que de una disciplina de ingeniería.
> - La falta de una base teórica sólida y ampliamente aceptada.
> - La enorme cantidad de métodos y variantes de métodos, con diferencias poco comprendidas y artificialmente magnificadas.
> - La falta de evaluación y validación experimental creíble.
> - La brecha entre la práctica de la industria y la investigación académica.
>
> Apoyamos un proceso para *re-fundar* la ingeniería de software sobre una teoría sólida, principios probados y mejores prácticas que:
>
> - Incluyan un *núcleo* (kernel) de elementos ampliamente acordados, extensible para usos específicos.
> - Aborden tanto las cuestiones tecnológicas como las relacionadas con las personas.
> - Cuenten con el respaldo de la industria, la academia, los investigadores y los usuarios.
> - Soporten la extensión frente a requisitos y tecnología cambiantes.

Este llamado a la acción fue firmado por alrededor de 40 líderes de pensamiento de todo el mundo, provenientes de la mayoría de las áreas de la ingeniería de software y las ciencias de la computación; 20 empresas y unas 20 universidades lo firmaron, y más de 2.000 individuos lo respaldaron. Deberías ver los "problemas específicos" identificados anteriormente como evidencia de que el mundo del software tiene problemas graves. Cuando se trata de la solución de "re-fundar la ingeniería de software", las palabras clave aquí son "un núcleo de elementos ampliamente acordados", que es en lo que se centra este libro.

No fue tarea fácil lograr que los profesionales de todo el mundo se pusieran de acuerdo sobre de qué trata la ingeniería de software, y mucho menos sobre cómo hacerla. Esto generó, por supuesto, una controversia significativa. Sin embargo, los partidarios de SEMAT perseveraron. No importa que el mundo se vuelva más complejo y que no haya una única respuesta: debería haber algún terreno común, un núcleo.

## 2.4 Essence: El Estándar de OMG

Después de varios años de arduo trabajo, el lenguaje subyacente y el núcleo de la ingeniería de software fueron aceptados en junio de 2014 como un estándar por OMG, y se le dio el nombre de **Essence**. Como se desprende del llamado a la acción, los líderes de SEMAT se dieron cuenta, desde el inicio mismo, de que un terreno común de la ingeniería de software (un núcleo) necesitaba ser ampliamente aceptado. En 2011, después de haber trabajado dos años juntos y de haber alcanzado parte de una propuesta de terreno común, evaluamos en qué punto estábamos y comprendimos que la mejor manera de lograr que este terreno común fuera ampliamente aceptado era convertirlo en un estándar formal de un organismo de estándares acreditado. La elección recayó en OMG. Sin embargo, tomó tres años más conseguir que superara el proceso de estandarización. Con base en la experiencia de los usuarios de Essence, OMG continúa mejorándolo a través de un grupo de trabajo asignado a esta labor.

En el resto de esta parte del libro, presentaremos Essence, los conceptos y principios clave detrás de Essence, y el valor y los casos de uso de Essence. Este material es, sin duda, útil tanto para estudiantes como para profesionales. Los lectores interesados en aprender más, consulten Jacobson et al. [2012, 2013a, 2013b] y Ng [2014].

## ¿Qué Deberías Ser Capaz de Hacer Ahora?

Después de estudiar este capítulo, deberías ser capaz de:

- explicar el significado de un *método* (como aquello que brinda orientación para todas las cosas que se necesita hacer al desarrollar y mantener software);
- explicar el significado de una *práctica* y sus tipos (es decir, prácticas relacionadas con la solución, prácticas relacionadas con el emprendimiento, prácticas relacionadas con el cliente);
- explicar el significado de los métodos en cascada y su papel en la historia de la ingeniería de software;
- explicar los métodos de ciclo de vida iterativo, los métodos estructurados, los métodos de componentes y los métodos ágiles, así como sus características;
- dar ejemplos de algunas prácticas (por ejemplo, equipos autoorganizados, programación en pares y reuniones diarias de pie como ejemplos de prácticas ágiles);
- explicar el problema de la "prisión de métodos" discutido en el capítulo; y
- explicar la iniciativa SEMAT y la motivación detrás del estándar Essence.

Nuevamente señalamos que hay lecturas adicionales, ejercicios y material complementario disponibles en [www.software-engineering-essentialized.com](http://www.software-engineering-essentialized.com).

---

## Notas al pie

[^1]: http://spectrum.ieee.org/riskfactor/computing/it/it-hiccups-of-the-week

[^2]: http://spectrum.ieee.org/riskfactor/computing/it/new-zealand-police-admits-sending-20-000-traffic-tickets-to-the-wrong-motorists

[^3]: http://spectrum.ieee.org/riskfactor/computing/it/it-hiccups-of-the-week-university-of-wisconsin-loses-another-11-million-in-payroll-glitches

[^4]: De Wikipedia: "Un cambio de paradigma, según lo identificado por el físico y filósofo estadounidense Thomas Kuhn, es un cambio fundamental en los conceptos básicos y las prácticas experimentales de una disciplina científica".

[^5]: De Wikipedia: "La metáfora de los enanos parados sobre los hombros de gigantes... expresa el significado de 'descubrir la verdad construyendo sobre descubrimientos previos'".

[^6]: https://www.infoq.com/news/2014/01/IDC-software-developers
