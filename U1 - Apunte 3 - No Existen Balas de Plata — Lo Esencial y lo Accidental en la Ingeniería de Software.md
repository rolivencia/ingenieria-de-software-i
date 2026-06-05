# No Existen Balas de Plata — Lo Esencial y lo Accidental en la Ingeniería de Software

por Frederick P. Brooks

---

> *No existe un solo desarrollo, ya sea tecnológico o de gestión, que por sí solo prometa, en una década, una mejora de al menos un orden de magnitud en la productividad, confiabilidad o simplicidad.*

---

<img width="830" height="432" alt="image" src="https://github.com/user-attachments/assets/150ef729-2bf9-4139-845a-967bc74d5374" />

<figure class="epigraph">
  <blockquote>
    El hombre lobo de Eschenbach, Alemania: grabado de línea, 1685. Cortesía de The Grainger Collection, Nueva York.
  </blockquote>
</figure>


---

## Resumen

Todo constructo de software involucra tareas esenciales, esto es, la creación de estructuras conceptuales complejas que forman las entidades abstractas de software, y tareas accidentales, es decir, la representación de estas entidades abstractas en lenguajes de programación y su mapeo en lenguajes de máquina sujetos a restricciones de espacio y velocidad.

En el pasado, la mayor parte de los grandes incrementos en la productividad del software vinieron de la eliminación de barreras artificiales que las tareas accidentales extremadamente difíciles ocasionaban, tales como las severas restricciones del hardware, los lenguajes de programación torpes y la falta de tiempo de máquina. ¿Cuánto del quehacer de los ingenieros de software actualmente está todavía dedicado a lo accidental, como opuesto a lo esencial? A menos que sea más de 9/10 del esfuerzo total, reduciendo el tiempo de todas las tareas accidentales a cero no dará un aumento de un orden de magnitud.

Por lo tanto, parece que ha llegado el momento de abordar las partes esenciales de la labor del software, aquellas concernientes con la creación de estructuras conceptuales abstractas de gran complejidad. Sugiero:

- Explotar el mercado masivo para evitar construir lo que se pueda comprar.
- Usar prototipos rápidos como parte de una iteración planificada para establecer los requisitos del software.
- Desarrollar el software orgánicamente, añadiendo más y más funcionalidades a los sistemas a medida que se ejecuten, usen y prueben.
- Identificar y desarrollar a los grandes diseñadores conceptuales de la nueva generación.

---

## Introducción

De todos los monstruos que pueblan las pesadillas de nuestro folklore, ninguno aterra más que los hombres lobo, pues se transforman inesperadamente de algo familiar en horror. Es por ellos que buscamos balas de plata que mágicamente los puedan sepultar.

Los típicos proyectos de software comparten algunas de estas características (al menos tal como lo ve el gestor no técnico), generalmente ingenuo y sincero, pero capaz de convertirse en el monstruo de los plazos no cumplidos, de los presupuestos rebasados y productos defectuosos. Por eso escuchamos lamentos desesperados por una bala de plata, algo que haga disminuir los costos del software tan rápidamente como lo hacen los costos del hardware.

Pero como se ve el horizonte de aquí a una década, no se observan balas de plata. No existe un solo desarrollo, ni en la tecnología ni en la gestión, que por sí solo prometa al menos una mejora de un orden de magnitud en la productividad, confiabilidad o simplicidad. En este capítulo trataremos de ver por qué; examinaremos tanto la naturaleza del problema del software como las propiedades de las balas que han sido propuestas.

Sin embargo, no es lo mismo ser escéptico que pesimista. A pesar de que no se vislumbran avances sorprendentes —y de hecho creo que eso es inconsistente con la naturaleza del software— están en marcha muchas innovaciones promisorias. Un esfuerzo disciplinado y consistente para desarrollar, propagar y explotar estas innovaciones debería en efecto producir una mejora de un orden de magnitud. No hay un camino sin obstáculos, pero hay uno.

El primer paso hacia la cura de la enfermedad fue la sustitución de teorías demoníacas y de humores por la teoría del germen. Solo ese paso en sí, el comienzo de la esperanza, se deshizo de todas las esperanzas en soluciones mágicas. Esto mostró a los programadores que el progreso sería realizado paso a paso, con gran esfuerzo, y que se tendría que prestar una atención persistente e incesante al hábito de la pulcritud. Así se encuentra hoy la ingeniería de software.

---

## ¿Tiene Que Ser Difícil? — Dificultades Esenciales

No solo no existen balas de plata a la vista; la propia naturaleza del software hace improbable que exista una: ninguna invención hará por la productividad, la confiabilidad y la simplicidad del software lo que la electrónica, los transistores y la integración a gran escala hicieron por el hardware de computadoras. No podemos esperar ver incrementos que se dupliquen cada dos años.

En principio, debemos observar que la anomalía no es que el progreso del software sea tan lento sino que el progreso del hardware sea tan rápido. Ninguna otra tecnología desde el inicio de la civilización ha visto incrementos en la relación precio-rendimiento de seis órdenes de magnitud en 30 años.

En ninguna otra tecnología se puede escoger obtener beneficios ya sea aumentando el rendimiento o reduciendo costos. Estos beneficios provienen de la transformación de la manufactura de computadoras a partir de una industria de ensamblaje a una industria de procesos.

En segundo término, para ver qué tasa de progreso podemos esperar en la tecnología del software, examinemos sus dificultades. De acuerdo con Aristóteles, las dividimos en esencia —las dificultades intrínsecas a la naturaleza del software— y accidentes —aquellas dificultades que hoy enfrentamos en su producción pero que no son intrínsecas.

Los accidentes los discutimos en la próxima sección. Consideremos primero la esencia.

La esencia de una entidad de software es un constructo de conceptos interrelacionados: conjuntos de datos, relaciones entre campos de datos, algoritmos e invocaciones de funciones. Esta esencia es abstracta, en el sentido de que el constructo conceptual es el mismo independientemente de su representación. No obstante, es muy precisa y rica en detalles.

Creo que la parte más difícil de la construcción del software es la especificación, el diseño y las pruebas de este constructo conceptual, no el trabajo de representarlo y probar la fidelidad de dicha representación. Y, con seguridad, todavía cometemos errores de sintaxis; pero son solo detalles comparados con los errores conceptuales en la mayor parte de los sistemas.

Si esto es cierto, la construcción del software siempre será difícil. Por su propia naturaleza no existen balas de plata.

Consideremos las propiedades intrínsecas de esta esencia irreductible de los sistemas modernos de software: la complejidad, conformidad, variabilidad e invisibilidad.

### Complejidad

Las entidades de software son más complejas por su tamaño que tal vez cualquier otro constructo humano, porque no hay dos partes iguales (al menos encima del nivel declarativo). Si existen, hacemos que las dos partes similares sean una sola subrutina, abierta o cerrada. En este sentido, los sistemas de software difieren profundamente de las computadoras, los edificios o automóviles, donde abundan los elementos repetidos.

Las computadoras digitales son en sí más complejas que la mayoría de las cosas que se construyen; tienen un número muy grande de estados. Esto hace que sea difícil concebirlos, describirlos y probarlos. Los sistemas de software tienen más estados de órdenes de magnitud que las computadoras.

Del mismo modo, hacer una entidad de software a mayor escala no es únicamente una repetición de los mismos elementos en grande; necesariamente es un incremento en el número de elementos diferentes. En la mayoría de los casos, los elementos interactúan entre sí de una forma no lineal, y la complejidad del todo se incrementa mucho más que linealmente.

La complejidad del software es una propiedad esencial, no accidental. Por lo tanto, las descripciones de una entidad de software que omiten su complejidad muchas veces también omiten su esencia. Durante tres siglos, las matemáticas y las ciencias físicas dieron grandes pasos en la construcción de modelos simplificados de fenómenos complejos, derivando propiedades de estos modelos y verificándolas experimentalmente. Esto funcionó porque las complejidades ignoradas en los modelos no eran propiedades esenciales del fenómeno. Esto no funciona cuando las complejidades son la esencia.

Muchos de los problemas clásicos del desarrollo de productos de software se derivan de su complejidad esencial y su incremento no lineal con el tamaño. A partir de la complejidad deriva la dificultad de comunicación entre los miembros del equipo, lo cual conduce a defectos del producto, costos excesivos y retrasos en el calendario. De la complejidad viene la dificultad de enumerar, ni hablar de comprender, todos los posibles estados del programa, y de ahí viene la falta de confiabilidad. De la complejidad de las funciones procede la dificultad de invocarlas, lo cual hace que los programas sean difíciles de usar. De la complejidad de la estructura viene la dificultad de la extensión del programa hacia nuevas funcionalidades sin crear efectos laterales. De la complejidad de la estructura provienen los estados no visualizados que constituyen agujeros de seguridad.

De la complejidad no solo se derivan problemas técnicos, sino también problemas de gestión. Esta complejidad dificulta la visión global, impidiendo así la integridad conceptual. Dificulta encontrar y controlar todos los cabos sueltos. Crea una tremenda carga de aprendizaje y comprensión que hace que la rotación de personal sea un desastre.

### Conformidad

Los ingenieros de software no son los únicos que encaran la complejidad. Los físicos tratan con objetos terriblemente complejos incluso a nivel de partículas "fundamentales". Sin embargo, el trabajo del físico descansa en una sólida fe de que existen principios unificadores a ser descubiertos, ya sea en los quarks o en las teorías del campo unificado. Einstein con frecuencia argumentaba que debían existir explicaciones simplificadas de la naturaleza, porque dios no es caprichoso o arbitrario.

No hay tal fe que consuele al ingeniero de software. Gran parte de la complejidad que debe llegar a gestionar tiene una complejidad arbitraria, forzada sin rima o razón por las numerosas tradiciones y sistemas humanos a los que deben ajustarse sus interfaces. Y, de vez en cuando, estas difieren de una interfaz a otra no debido a la necesidad sino solo porque fueron diseñados por diferentes personas y no por dios.

En muchos casos el software debe adecuarse porque es el último en entrar en escena. En otros debe adecuarse porque se percibe como el más adaptable. Pero en todos los casos, gran parte de la complejidad proviene de su adaptación a otras interfaces; esta complejidad no puede simplificarse por ningún rediseño del software únicamente.

### Capacidad de cambio

El software está sujeto constantemente a presiones de cambio. Por supuesto, también los edificios, autos y computadoras. Aunque los artículos manufacturados rara vez cambian después de su fabricación; son reemplazados por modelos posteriores, o por la incorporación de cambios importantes en copias posteriores del mismo diseño básico. El retiro del mercado de automóviles es realmente bastante raro; así también son infrecuentes los cambios en computadoras ya vendidas. Ambos son mucho menos frecuentes que las modificaciones del software ya distribuido.

En parte, esto es porque el software en un sistema encarna su función en sí, y la función es la parte que más siente las presiones de cambio. En parte, también es porque el software puede modificarse más fácilmente: es un artefacto intelectual infinitamente maleable. De hecho, los edificios cambian, aunque los altos costos del cambio todos lo entienden y sirven para amortiguar los caprichos por cambios.

Todo software exitoso inexorablemente cambia. Aquí suceden dos procesos. Cuando un producto de software resulta útil, las personas lo prueban en nuevos casos al borde, o más allá, del dominio original. Las presiones para extender su funcionalidad provienen principalmente de los usuarios quienes gustan de la funcionalidad básica e inventan nuevos usos.

En segundo término, el software exitoso también sobrevive más allá de la vida normal de la computadora para la cual fue desarrollado en principio. Si no, llegan nuevas computadoras, o al menos nuevos discos, nuevos desplegadores y nuevas impresoras; y el software debe adaptarse a estos nuevos vehículos de oportunidades.

En resumen, los productos de software forman parte de una matriz cultural de aplicaciones, usuarios, leyes y computadoras. Todos ellos cambian constantemente, y sus cambios obligan inexorablemente al software a cambiar.

### Invisibilidad

El software es invisible y no visualizable. Las abstracciones geométricas son herramientas poderosas. El plano de un edificio ayuda tanto al arquitecto como al cliente a evaluar los espacios, el tránsito y las vistas. Las contradicciones llegan a ser obvias y se pueden detectar omisiones. Los dibujos a escala de partes mecánicas y los modelos de palitos de moléculas, aunque son abstracciones, sirven al mismo propósito. Una realidad geométrica es aprehendida a través de una abstracción geométrica.

La realidad del software no forma parte intrínseca del espacio. Por lo tanto no tiene una representación geométrica directa en la forma en que existen mapas de la tierra, en que los chips de silicio tienen diagramas y las computadoras tienen esquemas de conexiones. Tan pronto como intentamos hacer el diagrama de una estructura de software, encontraremos que está compuesto, no de uno, sino de varios grafos dirigidos generales, superpuestos unos sobre otros. Estos grafos pueden representar flujos de control, flujos de datos, patrones de dependencia, secuencias de tiempo o relaciones nombre-espacio. Por lo general, ni siquiera son planos, mucho menos jerárquicos. Por cierto, una de las formas de establecer el control conceptual sobre tal estructura es forzarla a reducir enlaces hasta que uno o más grafos lleguen a ser jerárquicos.

A pesar del progreso en restringir y simplificar las estructuras del software, aún permanecen básicamente no visualizables, privando así a la mente de una de las herramientas conceptuales más poderosas. Esta carencia no solo impide el proceso de diseño dentro de una sola mente, sino que dificulta severamente la comunicación entre nuestras mentes.

---

## Los Adelantos del Pasado Resolvían Dificultades Accidentales

Si examinamos los tres pasos que han sido más fructíferos en la tecnología del software en el pasado, descubrimos que cada uno de ellos atacó una dificultad mayor diferente en la construcción del software, aunque estas dificultades fueron accidentales, no esenciales. También podemos observar los límites naturales a la extrapolación de cada uno de tales ataques.

### Lenguajes de alto nivel

Con seguridad el impacto más importante para la productividad, confiabilidad y simplicidad del software ha sido el uso creciente de lenguajes de programación de alto nivel. La mayor parte de los observadores le acreditan a ese desarrollo un aumento de al menos un factor de cinco en la productividad, y con ganancias correspondientes en confiabilidad, simplicidad e inteligibilidad.

¿Qué consigue el lenguaje de alto nivel? Liberar al programa de gran parte de su complejidad accidental. Un programa abstracto consiste de constructos conceptuales: operaciones, tipos de datos, secuencias y comunicación. Un programa de computadora concreto está involucrado con bits, registros, condiciones, bifurcaciones, canales, discos y demás. En la medida en que el lenguaje de alto nivel plasme los constructos deseados en el programa abstracto y evite todos los de bajo nivel, elimina un nivel completo de complejidad que jamás fue intrínseco al programa en absoluto.

Lo más que un lenguaje de alto nivel puede hacer es suministrar todos los constructos que el programador imagina en el programa abstracto. Ciertamente, el nivel de sofisticación de nuestro pensamiento acerca de estructuras de datos, tipos de datos y operaciones está aumentando constantemente, aunque a un ritmo cada vez menor. Y el desarrollo de los lenguajes se aproxima cada vez más a la sofisticación de los usuarios.

Además, se llega a un punto en que la elaboración de un lenguaje de alto nivel llega a ser una carga que incrementa, no reduce, la labor intelectual del usuario que rara vez utiliza los constructos más esotéricos.

### Tiempo compartido

La mayoría de los observadores le acreditan al tiempo compartido un gran aumento en la productividad de los programadores y en la calidad de sus productos, aunque no tan grande como la conseguida por los lenguajes de alto nivel.

El tiempo compartido ataca una dificultad claramente diferente. El tiempo compartido preserva la inmediatez, y por lo tanto nos hace capaces de mantener una visión global de la complejidad. La lenta velocidad de respuesta de la programación por lotes significa que inevitablemente olvidamos las minucias, si no el mismo impulso, de lo que estamos pensando cuando dejamos de programar y requerimos compilar y ejecutar. Esta interrupción de la conciencia es costosa en tiempo, porque debemos refrescar nuestra memoria. El efecto más serio puede ser la pérdida de comprensión de todo lo que sucede en un sistema complejo.

La lenta velocidad de respuesta, como las complejidades del lenguaje de máquina, es una dificultad accidental en vez de esencial del proceso de software. Los límites de la contribución del tiempo compartido se derivan directamente. El efecto principal es la reducción del tiempo de respuesta del sistema. En tanto nos aproximamos a cero, en cierto punto se pasará el umbral de perceptibilidad humana, alrededor de 100 milisegundos. Más allá de este umbral no se esperan más beneficios.

### Ambientes integrados de desarrollo

Unix e Interlisp han sido los primeros ambientes de programación integrados utilizados ampliamente, y parecen haber mejorado la productividad por factores enteros. ¿Por qué?

Ambos atacan las dificultades accidentales al usar programas individuales en forma conjunta, proporcionan bibliotecas integradas, formatos unificados de archivos, tuberías y filtros. En consecuencia, las estructuras conceptuales que en principio siempre podían invocarse, alimentarse y usarse entre sí, pueden en efecto hacerlo fácilmente en la práctica.

Este avance a su vez ha estimulado el desarrollo de todo un banco de herramientas, puesto que cada nueva herramienta podría ser aplicada a cualquier programa que utilice los formatos estándar.

Debido a estos éxitos, los ambientes son la materia de gran parte de la investigación actual en ingeniería de software. En la siguiente sección veremos sus promesas y limitaciones.

---

## Esperanzas por la Plata

Ahora veremos los desarrollos técnicos que habitualmente se consideran como potenciales balas de plata. ¿Qué problemas abordan: son los problemas de la esencia, o son los residuos de nuestras dificultades accidentales? ¿Ofrecen avances revolucionarios o solo incrementales?

### Ada y otros avances en los lenguajes de alto nivel

Uno de los desarrollos recientes más promocionados es el lenguaje de programación Ada, un lenguaje de alto nivel, de propósito general de los 80's. Ada, en efecto, no solo refleja mejoras evolutivas en los conceptos del lenguaje, sino que plasma rasgos que promueven conceptos de diseño moderno y modularización. Quizá la filosofía de Ada sea más avanzada que el propio lenguaje Ada, debido a su filosofía de modularización, de tipos de datos abstractos y de estructuras jerárquicas. Ada es quizás sobreabundante, el resultado natural del proceso por el cual hubo una exageración de requisitos en su diseño. Eso no es fatal; los problemas de aprendizaje pueden ser resueltos por el subconjunto de vocabularios de trabajo, y el progreso del hardware nos dará MIPS baratos para pagar los costos de compilación. Avanzar en la estructuración de los sistemas de software es en efecto un muy buen uso para el incremento de MIPS que nuestros dólares pagarán. Los sistemas operativos, cuyo desprestigio fue notorio en los 60's por su consumo de memoria y ciclos de reloj, han demostrado ser una forma excelente en la cual usar algunos de los MIPS y bytes de memoria baratos de la anterior oleada de hardware.

Sin embargo, Ada no demostrará ser la bala de plata que asesine al monstruo de la productividad del software. Después de todo, es solo otro lenguaje de alto nivel, y la mayor recompensa de tales lenguajes provino de la primera transición, pasando de las complejidades accidentales del lenguaje de máquina a la declaración más abstracta de soluciones graduales. Una vez que se hayan eliminado esos accidentes, los restantes serán más pequeños, y los beneficios obtenidos por su remoción seguramente serán menores.

Predigo que dentro de una década, cuando se evalúe la efectividad de Ada, se verá que realizó una diferencia sustancial, pero no por algún rasgo particular del lenguaje, ni siquiera debido a la combinación de todos ellos. Tampoco el nuevo ambiente de Ada probará ser la causa de las mejoras. La mayor contribución de Ada será que al haberse cambiado a este lenguaje se produjo la capacitación de los programadores en técnicas modernas de diseño de software.

### Programación orientada a objetos

Muchos practicantes del área guardan más esperanzas en la programación orientada a objetos que en cualquier otra de las técnicas de moda. Yo me encuentro entre ellos. Mark Sherman de Dartmouth hace notar que debemos tener cuidado al distinguir dos ideas separadas que van bajo ese nombre: tipo de datos abstracto y tipos jerárquicos, también llamados clases. El concepto de tipo abstracto de datos es que el tipo de un objeto debe estar definido por un nombre, un conjunto apropiado de valores, y un conjunto apropiado de operaciones, más que por una estructura de almacenamiento, la cual debería estar oculta. Algunos ejemplos son los paquetes de Ada (con tipos privados) o los módulos de Modula.

Los tipos jerárquicos, tales como las clases de Simula-67, permiten la definición de interfaces generales que además pueden ser refinadas a través del suministro de tipos subordinados. Los dos conceptos son ortogonales: pueden existir jerarquías sin ocultamiento y ocultamiento sin jerarquías. Ambos conceptos representan avances reales en el arte de la construcción del software.

Cada uno de ellos elimina una dificultad accidental más del proceso, y permite al diseñador expresar la esencia de su diseño sin tener que expresar grandes cantidades de material sintáctico que no añade nuevo contenido de información. Para los tipos tanto abstractos como jerárquicos, la consecuencia es eliminar un tipo de dificultad accidental de orden superior y permitir una expresión de orden superior del diseño.

Sin embargo, tales avances no pueden hacer más que eliminar todas las dificultades accidentales de la expresión del diseño. La complejidad del diseño en sí es esencial; y dichos ataques no producen ningún cambio al respecto. La programación orientada a objetos puede obtener un incremento de un orden de magnitud solo si la maleza innecesaria de la especificación de tipos que permanece actualmente en nuestros lenguajes de programación sea por sí misma responsable de nueve décimas partes del trabajo involucrado en el diseño de los productos de programación. Yo lo dudo.

### Inteligencia artificial

Mucha gente espera que los avances en inteligencia artificial proporcionen el gran paso revolucionario que dará ganancias de órdenes de magnitud a la productividad y a la calidad del software. Yo no.

Para ver por qué, debemos diseccionar qué se entiende por "inteligencia artificial" y entonces veremos cómo se aplica.

Parnas ha aclarado el caos terminológico:

> *Actualmente existen dos definiciones de uso común bastante diferentes de IA. IA-1: El uso de computadoras para resolver problemas que previamente solo se podían resolver a través de la aplicación de la inteligencia humana. IA-2: El uso de un conjunto específico de técnicas de programación conocidas como heurísticas o programación basada en reglas. En este enfoque se estudia a humanos expertos para determinar qué heurísticas o reglas empíricas usan para resolver problemas. … Se diseña el programa para resolver un problema a la manera en que los humanos parecen hacerlo.*
>
> *La primera definición tiene un significado movedizo. … Actualmente, ciertas cosas pueden encajar con la definición de la IA-1 pero, una vez que observamos cómo funciona el programa y entendemos el problema, no lo consideraremos más como IA. … Lamentablemente no puedo identificar un cuerpo de tecnología que sea exclusivo de este campo. … La mayor parte del trabajo es específico del problema, y se requiere cierta abstracción o creatividad para ver cómo transferirlo.*

Estoy completamente de acuerdo con esta crítica. Las técnicas usadas en el reconocimiento de voz parecen tener poco en común con las utilizadas en el reconocimiento de imágenes, y ambas son diferentes de las utilizadas en los sistemas expertos. He tenido dificultades en ver cómo el reconocimiento de imágenes, por ejemplo, haga un aporte considerable en la práctica de la programación. Y lo mismo con el reconocimiento de voz. La dificultad de construir software es decidir qué se quiere expresar, y no cómo expresarlo. Ningún medio de expresión puede brindar más que incrementos marginales.

La tecnología de los sistemas expertos, IA-2, merece una sección aparte.

### Sistemas expertos

La parte más avanzada y más ampliamente aplicada de la inteligencia artificial es la tecnología para la construcción de sistemas expertos. Muchos científicos de software trabajan arduamente aplicando esta tecnología a ambientes de construcción de software. ¿Cuál es el concepto, y cuáles son sus perspectivas?

Un sistema experto es un programa que tiene un motor de inferencia generalizada y una base de reglas. Está diseñado para tomar datos de entrada y suposiciones, y explora las consecuencias lógicas a través de inferencias derivadas de la base de reglas, obtiene conclusiones y consejos, y ofrece explicar sus resultados mostrando al usuario la trazabilidad de su razonamiento. Los motores de inferencia normalmente pueden tratar con datos difusos o probabilísticos y reglas, además de la lógica puramente determinista.

Tales sistemas ofrecen algunas ventajas claras sobre los algoritmos programados al obtener las mismas soluciones a los mismos problemas:

- La tecnología de los motores de inferencia se desarrolló en forma de una aplicación independiente y luego se aplicó a muchos usos. Se puede justificar así una mayor inversión en los motores de inferencia. De hecho, esa tecnología está bastante avanzada.
- Las partes variables de los materiales específicos de la aplicación se codifican en la base de reglas de una forma uniforme, y existen herramientas para desarrollar, cambiar, probar y documentar esta base de reglas. Esto estandariza gran parte de la complejidad de la aplicación misma.

Edward Feigenbaum afirma que el poder de tales sistemas no proviene de los mecanismos de inferencia siempre extravagantes, sino más bien de la base de conocimiento siempre rica que refleja el mundo real de forma más exacta. Creo que el avance más importante que ofrece esta tecnología consiste en la separación de la complejidad de la aplicación del programa en sí.

¿Cómo se puede aplicar esto a la tarea del software? De muchas maneras: sugerir reglas de interfaz, recomendar acerca de estrategias de pruebas, recordar las frecuencias del tipo de errores, ofrecer consejos acerca de la optimización, etc.

Por ejemplo, consideremos un consejero de prueba imaginario. En su forma más rudimentaria, el diagnóstico de los sistemas expertos es muy parecido a la lista de control de un piloto; ofrece básicamente sugerencias como las posibles causas del problema. A medida que la base de reglas se desarrolla, las sugerencias se hacen más específicas, toma en cuenta de manera más sofisticada los informes de los síntomas del problema. Uno lo puede ver como un auxiliar de depuración que ofrece sugerencias muy generales al principio, pero a medida que se incorpora cada vez más la estructura del sistema en la base de reglas, llega a ser cada vez más específico en las hipótesis que genera y en las pruebas que recomienda. Un sistema experto de este tipo puede diferir radicalmente de los convencionales en que su base de reglas probablemente debería estar modularizada jerárquicamente de la misma forma que el producto de software correspondiente, así que a medida que el producto se modifica modularmente, la base de reglas de diagnóstico puede también modificarse modularmente.

El trabajo necesario para generar reglas de diagnóstico es un trabajo que deberá hacerse de cualquier manera para generar el conjunto de casos de prueba para los módulos y el sistema. Si se hizo de una forma adecuada y general, con una estructura uniforme para las reglas y un buen motor de inferencia disponible, puede realmente reducir el trabajo entero de generar casos de prueba ilustrativos, además de servir como ayuda al mantenimiento de por vida y a las pruebas de modificación. De la misma forma, podemos proponer otros consejeros —probablemente muchos y quizás simples— aplicables a otras partes de la tarea de construcción del software.

Muchas dificultades se interponen en el camino del programador en la realización temprana de consejeros expertos útiles. Una parte crucial de nuestro escenario imaginario es el desarrollo de formas fáciles de obtener, a partir de la especificación de la estructura del programa, la generación automática o semiautomática de reglas de diagnóstico. Aún más difícil e importante es la doble tarea de la adquisición de conocimiento: encontrar expertos elocuentes, autoanalíticos que sepan por qué hacen las cosas; y desarrollar técnicas eficientes para la extracción de lo que ellos conocen y su destilación en forma de bases de reglas. El prerrequisito esencial en la construcción de un sistema experto es tener un experto.

La mayor contribución de los sistemas expertos seguramente será la de poner al servicio del programador inexperto la experiencia y la sabiduría acumulada de los mejores programadores. Este aporte no es menor. La brecha entre la mejor práctica del ingeniero de software y la práctica promedio es muy amplia —quizás más amplia que en otras ramas de la ingeniería. Una herramienta que difunda una buena práctica sería algo importante.

### Programación "automática"

Por casi 40 años, la gente ha estado anticipando y escribiendo acerca de la "programación automática", o la generación de un programa para resolver un problema a partir de la exposición de las especificaciones del problema. Hoy, algunas personas escriben como si esta tecnología fuese a proporcionar el siguiente gran salto.

Parnas da a entender que el término se ha utilizado por el glamour y no por el contenido semántico, afirmando:

> *En resumen, la programación automática siempre ha sido un eufemismo para la programación con un lenguaje de más alto nivel del que disponía el programador en ese momento.*

En esencia, argumenta que en la mayoría de los casos lo que se requiere especificar es el método de solución, no el problema.

Se pueden encontrar excepciones. La técnica para construir generadores es muy poderosa, y se usa rutinariamente con buenos resultados en programas de clasificación. Algunos sistemas para la integración de ecuaciones diferenciales también han permitido la especificación directa del problema. El sistema evaluaba los parámetros, seleccionados de una biblioteca de métodos de solución, y generaba los programas.

Estas aplicaciones tienen propiedades muy convenientes:

- Los problemas se caracterizan rápidamente mediante unos pocos parámetros.
- Existen muchos métodos conocidos de solución que proporcionan una biblioteca de opciones.
- Un análisis extensivo ha conducido a reglas explícitas para seleccionar las técnicas de solución, dados los parámetros del problema.

Es difícil ver cómo generalizar dichas técnicas a un universo más amplio de los sistemas de software comunes, donde los casos con propiedades tan claras son la excepción. Es difícil incluso imaginar cómo podría probablemente suceder este gran avance en la generalización.

### Programación gráfica

Un tema favorito para las disertaciones de doctorado en ingeniería de software es la programación gráfica, o visual, esto es, la aplicación de gráficas de computadora al diseño de software. Algunas veces la promesa de tal enfoque se postula por la analogía con el diseño de chips VLSI, donde las gráficas de computadora juegan un papel fundamental. A veces este enfoque está justificado al considerar los diagramas de flujo como el medio ideal de diseño de programas, y proporcionan instrumentos poderosos para su construcción.

Nada convincente, ni mucho menos emocionante, aún ha surgido de dichos esfuerzos. Estoy convencido de que nada surgirá.

En primer lugar, como he argumentado en otro lado, el diagrama de flujo es una abstracción muy pobre de la estructura del software. Y en efecto, es mejor verlo como un intento desesperado de dotar de un lenguaje de control de alto nivel a la computadora propuesta por Burks, von Neumann y Goldstine. La lastimosa forma de elaborar diagramas de flujo hoy en día, a través de múltiples páginas y de cajas de conexiones, ha demostrado ser esencialmente inútil como herramienta de diseño: los programadores dibujan diagramas de flujo después de, no antes de, escribir los programas que los describen.

En segundo lugar, las pantallas de hoy son muy pequeñas, en píxeles, para mostrar tanto el alcance como la resolución de cualquier detalle importante del diagrama de software. La así llamada "metáfora de escritorio" de las estaciones de trabajo actuales es en su lugar una metáfora de un "asiento de avión". Cualquiera que haya revuelto un montón de papeles mientras está sentado entre dos pasajeros corpulentos reconocerá la diferencia: solo se pueden ver unas cuantas cosas a la vez. El escritorio real proporciona una visión global y accesos aleatorios a una veintena de páginas. Más aún, cuando se produce un fuerte ataque de creatividad, más de un programador o escritor se ha sabido que abandona su escritorio por un espacio más amplio. La tecnología del hardware tendrá que avanzar bastante antes de que el ámbito global de nuestros ámbitos particulares sea suficiente para la tarea del diseño de software.

Tal como he argumentado anteriormente, el software en esencia es muy difícil de visualizar. Ya sea que dibujemos flujos de control, anidamientos de alcance variable, referencias cruzadas variables, flujos de datos, estructuras de datos jerárquicas, o lo que sea, sentimos solo una dimensión del intrincado entrelazado del elefante del software. Si superponemos todos los diagramas generados por las muchas vistas relevantes, es difícil extraer alguna visión global. La analogía con el VLSI es esencialmente engañosa: el diseño de un chip es un objeto tendido en dos dimensiones cuya geometría refleja su esencia. Un sistema de software no lo es.

### Verificación de programas

La mayor parte del trabajo en la programación moderna se dedica a probar y a reparar errores. ¿Hallaremos quizá una bala de plata cuando eliminemos los errores en el código fuente en la fase de diseño del sistema? ¿Podremos mejorar radicalmente tanto la productividad como la confiabilidad del producto siguiendo la estrategia totalmente distinta de proporcionar diseños correctos antes de volcar un inmenso esfuerzo en la implementación y la prueba de los mismos?

Dudo que aquí encontremos la magia. La verificación de programas es un concepto bastante poderoso, y será muy importante para cosas tales como la seguridad en los núcleos de los sistemas operativos. Sin embargo, la tecnología no promete ahorrarnos trabajo. Las verificaciones representan tanto trabajo que solo un puñado de programas sustanciales son verificados.

La verificación de programas no significa programas a prueba de errores. Aquí tampoco hay magia. Las demostraciones matemáticas también están sujetas a errores. Así que mientras las verificaciones podrían reducir la carga de prueba del programa, no podrán eliminarlas.

Más seriamente, incluso la verificación perfecta del programa puede solo establecer que un programa cumple con sus especificaciones. La parte más difícil de la labor de software es llegar a una especificación completa y coherente, y gran parte de la esencia de construir un programa es de hecho la depuración de las especificaciones.

### Ambientes y herramientas

¿Cuánto más podemos esperar de la explosión en las investigaciones acerca de mejores ambientes de programación? La reacción instintiva es que los problemas con grandes recompensas fueron los primeros en ser atacados, y han sido resueltos: los sistemas de archivos jerárquicos, la uniformidad en los formatos de archivo como en las interfaces entre programas y herramientas generalizadas. Los editores inteligentes de lenguajes específicos son desarrollos que todavía no son utilizados ampliamente en la práctica, aunque la mayoría de ellos promete liberarnos de errores sintácticos y errores semánticos simples.

Quizá el principal beneficio que aún queda pendiente en los ambientes de programación es el uso de sistemas de bases de datos integrados que lleven un seguimiento de la multitud de detalles que cada programador debe recordar exactamente y que mantenga su actualización dentro de un grupo de colaboradores en un solo sistema.

Sin duda este trabajo vale la pena y dará frutos tanto en la productividad como en la confiabilidad. Aunque por su propia naturaleza, la ganancia de aquí en adelante debe ser marginal.

### Estaciones de trabajo

¿Qué beneficios podemos esperar para el software del inevitable y rápido incremento en la potencia y la capacidad de memoria de las estaciones de trabajo personales? Bueno, ¿cuántos MIPS se pueden usar de forma fructífera? La redacción y edición de programas y documentos están completamente respaldadas por las velocidades actuales. A la compilación le vendría bien un impulso, aunque un factor de 10 en la velocidad de la máquina seguramente dejaría tiempo para pensar, la principal actividad diaria del programador. De hecho, así parece ser actualmente.

Estaciones de trabajo más poderosas sin duda son bienvenidas. No podemos esperar mejoras mágicas de ellas.

---

## Ataques Prometedores a la Esencia Conceptual

A pesar de que ningún gran avance tecnológico promete dar el tipo de resultados mágicos con los cuales estamos tan acostumbrados en el área del hardware, existe ahora tanto una abundancia de buen trabajo en curso, como la promesa de un progreso sostenido, si bien poco espectacular.

Todos los ataques tecnológicos sobre los accidentes del proceso de software están esencialmente limitados por la ecuación de productividad:

**Tiempo de la tarea = Σᵢ (Frecuencia)ᵢ × (Tiempo)ᵢ**

Si, como creo, los componentes conceptuales de la tarea están ahora ocupando la mayor parte del tiempo, entonces ninguna cantidad de acciones sobre los componentes de la tarea que sean únicamente la expresión de los conceptos podrá generar grandes aumentos en la productividad.

Por lo tanto, debemos considerar aquellos ataques que abordan la esencia del problema del software, la formulación de estas estructuras conceptuales complejas. Afortunadamente, algunos de ellos son muy prometedores.

### Comprar en contra de construir

La solución más radical posible para construir software es definitivamente no hacerlo.

Cada día esto se vuelve más fácil, en tanto más y más vendedores ofrecen más y mejores productos de software para una impresionante variedad de aplicaciones. Mientras que nosotros, los ingenieros de software, hemos trabajado en la metodología de la producción, la revolución de las computadoras personales ha creado no uno, sino muchos mercados masivos para el software. En cada puesto de periódicos vemos revistas mensuales que anuncian y revisan docenas de productos, clasificadas por tipo de máquina, a precios que van desde unos cuantos dólares a unos cientos. Fuentes más especializadas ofrecen productos muy poderosos para estaciones de trabajo y otros mercados de Unix. Incluso ya podemos adquirir herramientas y ambientes de desarrollo de software. También he propuesto en otros foros un mercado para módulos individuales.

Es más barato comprar cualquiera de esos productos que construirlo de nuevo. Incluso a un precio de $100,000, una pieza de software comprada cuesta aproximadamente lo mismo que el salario anual de un programador. ¡Y la entrega es inmediata! Inmediata al menos para productos que realmente existen y de los cuales el desarrollador puede dar referencias de clientes satisfechos. Más aún, tales productos tienden a estar mucho mejor documentados y algo mejor mantenidos que el software desarrollado en casa.

Creo que el desarrollo de un mercado masivo es la tendencia más importante a largo plazo en la ingeniería de software. El costo del software ha sido siempre el costo de su desarrollo, no el costo de su replicación. Compartir estos costos incluso entre unos cuantos usuarios reduce radicalmente el costo por usuario. Otra forma de verlo es que el uso de *n* copias de un sistema de software en efecto multiplica la productividad de sus desarrolladores por *n*. Esto mejora la productividad de la disciplina y de la nación.

La cuestión clave, obviamente, es la aplicabilidad. ¿Puedo usar un paquete disponible ya desarrollado para hacer mi tarea? Aquí ha sucedido una cosa sorprendente. Durante los 50's y 60's, varios estudios mostraron que los usuarios no usarían paquetes ya desarrollados para nóminas, control de inventario, cuentas pendientes, etc. Los requisitos eran tan especializados, que la variación de caso a caso era muy alta. Durante los 80's, encontramos paquetes con una alta demanda y uso generalizado. ¿Qué ha cambiado?

En realidad no fueron los paquetes. Puede ser que sean más generalizados y un tanto más personalizables que los anteriores, pero no mucho. En realidad tampoco las aplicaciones. En todo caso, las necesidades científicas y de negocios actuales son más diversas, y más complicadas que las de hace 20 años.

El gran cambio ha estado en la relación de costo hardware/software. El comprador de una máquina de $2 millones en 1960 sentía que podía pagar $250,000 más por un programa de nómina personalizado, uno que se deslizara suavemente y sin alboroto dentro de un ambiente social hostil hacia las computadoras. Los compradores de máquinas de oficina de $50,000 hoy no pueden posiblemente pagar por programas de nómina personalizados, así que adaptan sus procedimientos de nómina a los paquetes disponibles. Las computadoras ahora son lugares comunes, si no es que muy amadas, tal que las adaptaciones son aceptadas como una cosa natural.

Existen excepciones dramáticas a mis argumentos de que la generalización de los paquetes de software ha cambiado poco a través de los años: las hojas de cálculo y los sistemas de bases de datos sencillos. Estas herramientas poderosas, en retrospectiva tan obvias y con todo de aparición tan tardía, se prestan a múltiples usos, algunos muy poco ortodoxos. Actualmente abundan artículos e incluso libros que muestran cómo abordar tareas inesperadas con las hojas de cálculo. Grandes cantidades de aplicaciones que anteriormente hubieran sido escritas como programas personalizados en Cobol o por un Programa Generador de Informes hoy son realizadas rutinariamente con estas herramientas.

Actualmente muchos usuarios manejan día tras día sus propias computadoras en una variedad de aplicaciones sin jamás haber escrito un programa. De hecho, muchos de ellos no saben escribir nuevos programas para sus computadoras, pero sin embargo son expertos en resolver nuevos problemas con ellas.

Creo que la estrategia de productividad del software más poderosa para muchas organizaciones hoy en día es equipar a trabajadores intelectuales inexpertos en computadoras que laboran en la línea de fuego con computadoras personales y buenos programas generalizados de edición de texto, dibujo, manejo de archivos y hojas de cálculo, y dejarlos libres. La misma estrategia funcionaría si se dotaran de paquetes generalizados de matemáticas y estadística y algunas simples capacidades de programación a cientos de científicos de laboratorio.

### Refinamiento de requisitos y prototipos rápidos

La parte más difícil de la construcción de los sistemas de software es precisamente decidir qué construir. No hay otra parte del trabajo conceptual que sea tan difícil como el establecimiento de requisitos técnicos detallados, incluyendo todas las interfaces tanto a los usuarios, como a las computadoras y a otros sistemas de software. O que perjudique tanto el sistema resultante si se hizo mal. Ni que sea más difícil de rectificar posteriormente.

Por lo tanto, la tarea más importante que los constructores de software hacen por sus clientes es la extracción y el refinamiento iterativo de los requisitos del producto. La verdad es que los clientes no saben lo que quieren. Generalmente no saben qué preguntas se deben responder, y casi nunca han pensado en el problema en esos detalles que deben especificarse. Incluso la respuesta sencilla —"Hacer que el nuevo sistema de software trabaje como nuestro viejo sistema manual de procesamiento de información"— es de hecho bastante simple. Los clientes jamás quieren exactamente eso. Más aún, los complejos sistemas de software son cosas que actúan, que mueven cosas y que funcionan. Las dinámicas de esa acción son difíciles de imaginar. Así que al planificar cualquier tarea de software, es necesario contar con una amplia iteración entre el cliente y el diseñador como parte de la definición del sistema.

Yo iría un paso más lejos y afirmaría que es realmente imposible para los clientes, incluso para aquellos que trabajan con los ingenieros de software, especificar completa y correctamente los requisitos exactos de un producto de software antes de construir y probar algunas versiones previas del producto que están especificando.

Por lo tanto, uno de los esfuerzos más prometedores de la tecnología actual, y que ataca la esencia, no los accidentes, del problema del software, es el desarrollo de estrategias y herramientas para la obtención rápida de prototipos de sistemas como parte de la especificación iterativa de requisitos.

Un prototipo de un sistema de software es aquel que simula las interfaces importantes y realiza las funciones principales del sistema previsto, sin estar necesariamente sujeto a las mismas restricciones de velocidad del hardware, el tamaño o el costo. Los prototipos generalmente realizan las tareas principales de la aplicación, aunque no intentan manejar excepciones, responder correctamente a entradas inválidas, abortar limpiamente, etc. El propósito del prototipo es hacer realidad la estructura conceptual especificada, de tal manera que el cliente pueda probar su coherencia y su facilidad de uso.

Actualmente gran parte de los procedimientos de adquisición de requisitos de software yacen en la suposición de que se puede especificar un sistema satisfactoriamente por adelantado, obtener ofertas para su construcción, construirlo e instalarlo. Creo que esta suposición está esencialmente errada, y que muchos de los problemas de adquisición de requisitos de software surgen de esa falacia. Por lo tanto, no pueden ser reparados sin una revisión fundamental, una que mantenga el desarrollo y la especificación iterativa de prototipos y productos.

### Desarrollo incremental — desarrolle software, no lo construya

Todavía recuerdo la impresión que sentí en 1958 cuando escuché por primera vez a un amigo hablar acerca de construir un programa, en oposición a escribirlo. En un destello ensanchó toda mi visión del proceso del software. El cambio de metáfora fue poderoso y exacto. Hoy entendemos en qué se parece la construcción del software a otros procesos de construcción, y abiertamente usamos otros elementos de la metáfora, tales como las especificaciones, el ensamblado de componentes y el andamiaje.

La metáfora de la construcción ha sobrevivido a su utilidad. Es tiempo de cambiar otra vez. Si, como creo, las estructuras conceptuales que construimos hoy en día son bastante complicadas para ser especificadas exactamente por adelantado, y muy complejas para ser construidas sin fallas, entonces debemos tomar un enfoque radicalmente diferente.

Volvamos nuestra mirada a la naturaleza y estudiemos la complejidad de las cosas vivas en lugar de solo la obra inerte del hombre. Aquí encontramos constructos cuyas complejidades nos estremecen de asombro. Solo el cerebro es intrincado por encima del mapeo, poderoso más allá de la imitación, rico y diverso, autoprotegido y autorenovado. El secreto es que se desarrolla, no se construye.

Así debe ser con nuestros sistemas de software. Hace algunos años Harlan Mills propuso que cualquier sistema de software debe desarrollarse a través de un desarrollo incremental. Es decir, primero debemos construir un sistema para ser ejecutado, aún cuando no haga nada útil excepto llamar al conjunto apropiado de subprogramas ficticios. Luego, se expande poco a poco con subprogramas que están siendo, a su vez, desarrollados dentro de acciones o llamadas a programas aún incompletos y vacíos de bajo nivel.

He visto el resultado más dramático desde que empecé a insistir en esta técnica de construcción de proyectos en mi clase de laboratorio de ingeniería de software. Nada en la década pasada ha cambiado tan radicalmente mi propia práctica o su eficacia. El enfoque necesita un diseño descendente, porque es un desarrollo descendente del software. Esto permite retroceder fácilmente. Se presta para prototipos tempranos. Cada función que se añade y nuevo suministro de datos o circunstancias más complejas nace orgánicamente a partir de lo que allí ya existe.

Los efectos morales son asombrosos. El entusiasmo irrumpe cuando hay un sistema funcionando, aunque sea uno simple. Los esfuerzos se redoblan cuando la primera imagen de un nuevo sistema de software gráfico aparece en la pantalla, aunque sea solo un rectángulo. En cada etapa del proceso, siempre se tiene un sistema funcionando. He hallado que los equipos pueden desarrollar entidades mucho más complejas en cuatro meses de las que pueden construir.

Se pueden obtener los mismos beneficios en proyectos grandes como en pequeños.

### Grandes diseñadores

La principal cuestión de cómo mejorar los centros de desarrollo de software ha sido, como siempre, el personal.

Podemos obtener buenos diseños siguiendo buenas prácticas en lugar de malas. Las buenas prácticas de diseño se pueden enseñar. Los programadores están entre la porción más inteligente de la población, así que pueden aprender las buenas prácticas. Es por eso que un impulso importante en los Estados Unidos ha sido promulgar buenas prácticas modernas. Nuevos planes de estudio, nueva literatura, nuevas organizaciones como el Instituto de Ingeniería de Software, todos ellos se han creado para mejorar el nivel de nuestra práctica, del nivel malo al bueno. Esto es totalmente apropiado.

Sin embargo, no creo que podamos dar el gran salto adelante de la misma forma. En tanto la diferencia entre los malos diseños conceptuales y buenos dependa de la solidez de los métodos de diseño, la diferencia entre los buenos diseños y los grandes seguramente no. Los grandes diseños provienen de grandes diseñadores. La construcción del software es un proceso creativo. Una sólida metodología puede facultar y liberar la mente creativa; no puede avivar o inspirar el trabajo rutinario.

Las diferencias no son menores: se parece mucho a Salieri y Mozart. Después de muchos estudios se ha demostrado que los mejores diseñadores producen estructuras que son más rápidas, más pequeñas, más simples, más limpias y se llevan a cabo con menor esfuerzo. Las diferencias entre el gran enfoque y el promedio son de un orden de magnitud.

Haciendo una pequeña retrospectiva vemos que aunque muchos sistemas de software finos y útiles han sido diseñados por comités y construidos por proyectos de diversas partes, los sistemas de software que han emocionado a apasionados admiradores son aquellos que han sido el producto de una o unas pocas grandes mentes diseñadoras. Considérese Unix, APL, Pascal, Modula, la interfaz de Smalltalk, incluso Fortran; y contrástese con Cobol, PL/I, Algol, MVS/370, y MS-DOS.

| Sí       | No      |
|----------|---------|
| Unix     | Cobol   |
| APL      | PL/I    |
| Pascal   | Algol   |
| Modula   | MVS/370 |
| Smalltalk| MS-DOS  |
| Fortran  |         |

*Fig. 16.1 Productos emocionantes*

Por lo tanto, aunque apoyo firmemente la transferencia de tecnología y los esfuerzos de desarrollo curricular actualmente en curso, creo que el esfuerzo individual más importante que podemos organizar es el desarrollo de formas de crecimiento de grandes diseñadores.

Ninguna organización de software puede soslayar este reto. Los buenos gestores, por escasos que sean, no son más escasos que los buenos diseñadores. Los grandes diseñadores como los grandes gestores son ambos muy raros. La mayoría de las organizaciones invierten un esfuerzo considerable en buscar y desarrollar a candidatos a gestores; no sé de ninguna que invierta el mismo esfuerzo en buscar y desarrollar a esos grandes diseñadores de los que finalmente dependerá la excelencia técnica de los productos.

Mi primera propuesta es que cada organización de software debe determinar y proclamar que los grandes diseñadores son tan importantes para su éxito como lo son los gestores, y que pueden esperar ser igualmente promovidos y recompensados. No solo el salario, sino los beneficios del reconocimiento —tamaño de oficina, mobiliario, equipamiento técnico personal, fondos de viaje y personal de apoyo— deben ser totalmente equivalentes.

¿Cómo se desarrolla un gran diseñador? El espacio no nos permite una discusión amplia, aunque algunos pasos son obvios:

- Identificar sistemáticamente a los mejores diseñadores tan pronto como sea posible. Los mejores generalmente no son los más experimentados.
- Asignar un tutor profesional como responsable del desarrollo del candidato, y mantener un meticuloso archivo profesional.
- Idear y mantener un plan de desarrollo profesional de cada candidato, incluyendo la formación cuidadosamente seleccionada con los mejores diseñadores, capítulos de educación formal avanzada y cursos cortos, todo entremezclado con un diseño individual y deberes de liderazgo técnico.
- Proporcionar oportunidades para que los diseñadores en desarrollo interactúen y se estimulen entre ellos.
