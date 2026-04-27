# Introducción a la Teoría General de Sistemas
 
## 1.1 ¿Qué es un sistema?
 
Un **sistema** puede definirse como un conjunto de elementos organizados e interrelacionados que interactúan entre sí con el propósito de alcanzar un objetivo común (Bertalanffy, 1968). Estos elementos pueden ser **físicos**, como piezas mecánicas en una máquina, o **intangibles**, como procesos, reglas, ideas o flujos de información.
 
A lo largo de la historia de la disciplina, distintos autores han propuesto definiciones complementarias:
 
- **Bertalanffy (1968)** define un sistema como "un complejo de elementos en interacción", enfatizando que las relaciones entre partes son tan importantes como las partes mismas.
- **Ackoff (1971)** lo define como un conjunto de elementos interrelacionados donde *ningún subconjunto es independiente del resto*: cambiar una parte afecta inevitablemente a las demás.
- **Churchman (1968)** incorpora la dimensión teleológica: un sistema es "un conjunto de partes coordinadas para lograr un conjunto de objetivos".
 
Las tres definiciones convergen en dos ideas centrales: **interrelación** (las partes no funcionan aisladamente) y **propósito** (el sistema existe para algo). Para un ingeniero de software, ambas son fundamentales: los componentes de una aplicación interactúan entre sí (Bertalanffy), un cambio en cualquier módulo puede afectar al resto (Ackoff), y todo el conjunto existe para resolver un problema de negocio (Churchman).
 
La **Teoría General de Sistemas (TGS)**, desarrollada por Ludwig von Bertalanffy a mediados del siglo XX, plantea que todo sistema debe analizarse como una totalidad, más que como una simple suma de partes, ya que el comportamiento del conjunto difiere del de sus componentes aislados. Este principio se conoce como **totalidad** o **no-sumatividad**.
 
> "El todo es más que la suma de sus partes." (Bertalanffy, 1968)
 
Los sistemas existen en un **entorno determinado** con el que interactúan, y dentro del cual sus componentes internos deben funcionar de manera integrada. La forma en que están organizados, así como la naturaleza de sus relaciones internas, determina su eficiencia y estabilidad.
 
## 1.2 ¿Por qué estudiar sistemas?
 
Comprender los sistemas es esencial en múltiples disciplinas, especialmente en la ingeniería, la informática y las ciencias sociales. El enfoque sistémico permite **analizar la complejidad**, anticipar el comportamiento de los componentes, diseñar soluciones integradas y mejorar procesos de forma continua (Checkland, 1999).
 
Senge (1990) identifica el pensamiento sistémico como la disciplina integradora que permite ver *patrones* donde otros ven *eventos aislados*, y *estructuras* donde otros ven *cadenas lineales de causa y efecto*. En el contexto del desarrollo de software, esto es particularmente relevante: los problemas más difíciles —la deuda técnica que se acumula, los proyectos que se atrasan al agregar más personas, las integraciones que fallan de maneras imprevistas— son fenómenos *sistémicos* que requieren pensamiento sistémico, no solo habilidad técnica.
 
Consideremos un ejemplo concreto: un sistema de software puede estar compuesto por un **frontend** (interfaz de usuario), un **backend** (lógica de negocio) y una **base de datos** (almacenamiento). Si alguno de estos componentes falla, se compromete el funcionamiento de todo el sistema. Pero más importante aún: propiedades como el *rendimiento*, la *seguridad* y la *experiencia de usuario* no residen en ningún componente individual — **emergen** de la interacción entre todos ellos.
 
## 1.3 Subsistemas y supersistemas
 
En muchos casos, los elementos que componen un sistema también pueden considerarse **subsistemas**. Un subsistema tiene cierta autonomía funcional pero opera dentro del marco del sistema mayor. Por ejemplo, un **sistema operativo** puede contener subsistemas como el de gestión de memoria, el de archivos o el de control de dispositivos. Cada uno de ellos realiza funciones específicas y tiene una estructura propia.
 
A su vez, todo sistema puede ser visto como parte de un **supersistema** más amplio. El sistema operativo es subsistema de la computadora; la computadora es subsistema de la red institucional; la red es subsistema de Internet. Ackoff (1971) formalizó esta jerarquía y enfatizó que la definición de los límites entre sistema, subsistema y supersistema depende del *punto de vista del observador*.
 
Sin embargo, no todos los componentes de un sistema califican como subsistemas. Elementos simples, como un archivo de texto o un cable, aunque esenciales, no poseen la complejidad o autonomía necesaria para considerarse sistemas por sí mismos (Ackoff, 1971).
 
---
 
## 1.4 Clasificación de los sistemas
 
Los sistemas pueden clasificarse según distintos criterios. Es importante señalar que las categorías no son mutuamente excluyentes: un mismo sistema puede clasificarse simultáneamente según todos los criterios presentados.
 
### 1.4.1 Según su origen
 
- **Sistemas naturales:** Se originan sin intervención humana. Ejemplo: el ciclo del agua, un ecosistema.
- **Sistemas artificiales:** Son creados por el ser humano con un propósito específico. Ejemplo: una computadora, una red vial.
 
(Skyttner, 2005)
 
### 1.4.2 Según su composición
 
- **Sistemas físicos:** Formados por elementos tangibles. Ejemplo: un avión, una impresora.
- **Sistemas abstractos:** Constituidos por ideas, reglas o símbolos. Ejemplo: un sistema legal, un lenguaje de programación.
- **Sistemas mixtos:** Combinan componentes físicos y abstractos. Ejemplo: un teléfono celular (hardware + software).
 
(Churchman, 1968)
 
### 1.4.3 Según su relación con el entorno
 
- **Sistemas abiertos:** Intercambian materia, energía o información con su entorno, manteniendo un estado estacionario lejos del equilibrio. Ejemplo: el cuerpo humano, una aplicación web en producción.
- **Sistemas cerrados:** No tienen intercambio significativo con el entorno y tienden hacia la entropía máxima. Ejemplo: un reloj mecánico (idealización).
 
Bertalanffy (1968) demostró que los sistemas abiertos pueden mantener su organización interna importando orden desde el entorno y exportando desorden (entropía). En la práctica, los sistemas completamente cerrados son una idealización teórica: casi todo sistema real tiene algún grado de intercambio con su entorno. Todo software en producción es un sistema abierto: recibe datos de usuarios, interactúa con redes, consume recursos computacionales y produce resultados hacia el exterior.
 
### 1.4.4 Según su complejidad
 
- **Sistemas simples:** Pocos componentes e interacciones predecibles. Ejemplo: un interruptor eléctrico.
- **Sistemas complejos:** Muchos elementos con relaciones no lineales, donde las propiedades del todo no se deducen trivialmente de las partes. Ejemplo: una red informática, un sistema de comercio electrónico.
 
Simon (1962) define un sistema complejo como aquel compuesto por un gran número de partes que interactúan de manera "no simple", donde inferir las propiedades del todo a partir de las partes individuales no es trivial. Simon propuso que los sistemas complejos exitosos se organizan en **jerarquías cuasi-descomponibles**: las conexiones *dentro* de cada módulo son mucho más fuertes que las conexiones *entre* módulos. Este principio fundamenta directamente la arquitectura modular del software.
 
### 1.4.5 Según su dinámica
 
- **Sistemas estáticos:** Su estructura no cambia en el tiempo. Ejemplo: un diagrama de clases, una estructura arquitectónica.
- **Sistemas dinámicos:** Evolucionan o se transforman con el tiempo en función de interacciones internas y externas. Ejemplo: un ecosistema, un sistema de software en producción.
 
Forrester (1961) fundó la disciplina de **Dinámica de Sistemas** con la premisa de que el comportamiento de un sistema surge de su *estructura* interna de bucles de retroalimentación, acumulaciones y retardos, no exclusivamente de perturbaciones externas. Todo sistema de software en producción es dinámico; los diagramas y modelos son representaciones estáticas de una realidad intrínsecamente dinámica.
 
### 1.4.6 Según su control
 
- **Sistemas determinísticos:** Su comportamiento es predecible: ante la misma entrada producen siempre la misma salida. Ejemplo: una calculadora.
- **Sistemas probabilísticos:** Su comportamiento incluye incertidumbre o componentes aleatorios. Ejemplo: la bolsa de valores, un sistema de recomendaciones con machine learning.
 
Von Foerster (1974) profundizó esta distinción diferenciando **máquinas triviales** (determinísticas, sin memoria de estado) de **máquinas no-triviales** (cuya salida depende del historial del sistema, haciéndolo analíticamente indeterminado). La mayoría del software con estado es una máquina no-trivial: su comportamiento depende no solo de la entrada actual sino de toda su historia de ejecución previa.
 
### 1.4.7 Según su naturaleza
 
- **Sistemas mecánicos:** Basados en mecanismos físicos. Ejemplo: un motor de combustión.
- **Sistemas biológicos:** Compuestos por organismos vivos. Ejemplo: el sistema digestivo.
- **Sistemas sociales:** Integrados por personas y relaciones humanas. Ejemplo: una empresa, una cooperativa.
- **Sistemas informáticos:** Diseñados para procesar información. Ejemplo: un sistema operativo, un ERP.
 
Boulding (1956) organizó estos tipos en una **jerarquía de nueve niveles** de complejidad creciente, donde cada nivel contiene todas las propiedades de los niveles inferiores más al menos una propiedad emergente nueva. Desde los *marcos* (estructuras estáticas, nivel 1) hasta los *sistemas sociales* (nivel 8), la jerarquía enseña que no se puede comprender un sistema sociotécnico usando únicamente los conceptos válidos para un mecanismo simple.
 
---
 
## 1.5 Componentes funcionales de un sistema
 
Todo sistema puede analizarse en función de cinco componentes funcionales básicos:
 
### 1.5.1. Entrada
 
Es el insumo que inicia o alimenta el funcionamiento del sistema. Puede ser información, energía o materia. Por ejemplo, en un sistema educativo, los estudiantes, profesores y materiales de estudio son entradas clave. En un compilador, el código fuente es la entrada.
 
(Morin, 1990)
 
### 1.5.2. Proceso
 
Es el conjunto de transformaciones que el sistema realiza con las entradas para generar un resultado. En una escuela, este proceso es la enseñanza y el aprendizaje. En un compilador, es el análisis léxico, sintáctico y la generación de código.
 
(Checkland, 1999)
 
### 1.5.3. Salida
 
Es el resultado del procesamiento. En el caso del sistema educativo, serían los egresados o el conocimiento adquirido. En el compilador, es el archivo ejecutable o los mensajes de error.
 
(Skyttner, 2005)
 
### 1.5.4. Retroalimentación (feedback)
 
Es el mecanismo por el cual el sistema evalúa sus propios resultados y ajusta su comportamiento. Ashby (1956) formalizó la retroalimentación como mecanismo esencial de regulación en la cibernética. Existen dos tipos fundamentales:
 
- **Retroalimentación negativa** (bucle balanceador): corrige desviaciones y busca estabilidad. Ejemplo: un termostato que apaga la calefacción cuando se alcanza la temperatura deseada, o un auto-scaler que reduce instancias de servidor cuando baja la demanda.
- **Retroalimentación positiva** (bucle reforzador): amplifica el cambio, generando crecimiento o declive acelerado. Ejemplo: el crecimiento viral de una aplicación donde más usuarios atraen más usuarios, o un ciclo de deuda técnica donde cada parche rápido genera más complejidad.
 
Meadows (2008) denomina a estos mecanismos *bucles balanceadores* y *bucles reforzadores*, y señala que la interacción entre ambos tipos de bucles es lo que genera los patrones de comportamiento característicos de cada sistema.
 
En software, la retroalimentación puede manifestarse en el análisis de errores reportados por usuarios, en las métricas de rendimiento que disparan alertas, o en los ciclos de retrospectiva de un equipo ágil.
 
### 1.5.5. Límites
 
Delimitan lo que forma parte del sistema y lo que queda fuera. Estos pueden ser físicos (un firewall, las paredes de un edificio) o conceptuales (las responsabilidades de un módulo, los alcances de un contrato).
 
Meadows (2008) señala que los límites son construcciones del observador, no propiedades intrínsecas de la realidad. Churchman (1968) advirtió sobre la **falacia ambiental**: la tendencia peligrosa a dibujar los límites del sistema demasiado estrechamente, tratando factores externos como "dados" cuando en realidad deberían examinarse. En un hospital, por ejemplo, los límites incluyen a los servicios médicos internos, pero un análisis sistémico completo debería considerar también la relación con farmacias, obras sociales y el sistema de salud público.
 
En ingeniería de software, definir correctamente los límites del sistema es una de las decisiones de diseño más importantes y más difíciles: ¿dónde termina "mi sistema" y empieza el de otro equipo?
 
---
 
## 1.6 Propiedades fundamentales de los sistemas
 
Más allá de los componentes funcionales, los sistemas exhiben propiedades que surgen de su organización interna y que son esenciales para comprenderlos:
 
### 1.6.1 Emergencia
 
Las **propiedades emergentes** son características del sistema que no existen en ninguna de sus partes individuales y que solo aparecen cuando el sistema está ensamblado y funcionando (Skyttner, 2005). El rendimiento de una aplicación, su seguridad y la experiencia de usuario son propiedades emergentes: ningún componente individual las "posee"; surgen de la interacción entre todos los componentes.
 
La emergencia puede ser beneficiosa (una orquesta produce música que ningún instrumento individual puede producir) o destructiva (una combinación imprevista de módulos produce un comportamiento catastrófico que ningún módulo exhibe por separado).
 
### 1.6.2 Entropía y negentropía
 
La **entropía** es la tendencia de todo sistema hacia el desorden y la degradación. En sistemas cerrados, la entropía solo puede aumentar (segunda ley de la termodinámica). Los sistemas abiertos pueden contrarrestar esta tendencia importando orden desde su entorno, proceso que se denomina **negentropía** (Skyttner, 2005).
 
En software, esto se manifiesta como las *Leyes de Lehman de Evolución del Software*: la complejidad de un programa crece continuamente a menos que se trabaje activamente para mantenerla o reducirla. La refactorización, las revisiones de código, las pruebas automatizadas y la documentación son las fuerzas negentrópicas que combaten la entropía del software. Sin mantenimiento activo, todo código tiende al desorden.
 
### 1.6.3 Equifinalidad
 
En sistemas abiertos, el mismo estado final puede alcanzarse desde condiciones iniciales distintas y por caminos diferentes (Bertalanffy, 1968). No existe "la única solución correcta". Una aplicación web puede construirse como monolito, como microservicios, como serverless o como event-driven: todas pueden cumplir los mismos requisitos funcionales. La elección depende del contexto (equipo, presupuesto, escala esperada, experiencia técnica). La equifinalidad enseña a evaluar alternativas en lugar de buscar una respuesta única.
 
### 1.6.4 Sinergia
 
La **sinergia** es el efecto por el cual la cooperación entre las partes produce resultados superiores a los que obtendrían trabajando aisladamente. Es la manifestación positiva de la totalidad de Bertalanffy. En software, la *filosofía Unix* es un ejemplo clásico de sinergia: herramientas simples que hacen una sola cosa bien, combinadas mediante pipes, crean capacidades que ninguna herramienta individual posee.
 
### 1.6.5 Isomorfismo
 
El **isomorfismo** describe correspondencias estructurales entre sistemas de distintos dominios (Bertalanffy, 1968). No se trata de simples analogías sino de patrones estructurales que reaparecen en contextos diferentes. Los *patrones de diseño* del software (Observer, Strategy, Factory) son ejemplos de isomorfismo: soluciones estructuralmente idénticas que funcionan en dominios completamente distintos.
 
### 1.6.6 Homeostasis
 
La **homeostasis** es la capacidad de un sistema de mantener sus variables esenciales dentro de límites aceptables mediante mecanismos de retroalimentación negativa, a pesar de perturbaciones externas (Ashby, 1956). El término fue acuñado originalmente por Walter Cannon en fisiología para describir cómo el cuerpo humano mantiene la temperatura, el pH sanguíneo o los niveles de glucosa dentro de rangos estrechos. Ashby lo generalizó: cualquier sistema que mantiene estabilidad frente a perturbaciones es homeostático.
 
Aunque la homeostasis se asocia tradicionalmente con sistemas biológicos, el concepto se aplica con igual rigor a sistemas artificiales. Un termostato es un dispositivo homeostático elemental. En ingeniería de software, la homeostasis se implementa de múltiples formas: los *reconciliation loops* de Kubernetes comparan continuamente el estado deseado con el estado actual y corrigen desviaciones; los *circuit breakers* aíslan componentes fallidos para preservar la estabilidad del sistema global; los *health checks* y *auto-scaling groups* ajustan recursos computacionales para mantener el rendimiento dentro de umbrales aceptables. Todos estos mecanismos operan según el mismo principio: detectar desviación → corregir → verificar.
 
### 1.6.7 Autopoiesis
 
La **autopoiesis** (del griego *auto*: a sí mismo, *poiesis*: creación) es la capacidad de un sistema de producir y reproducir continuamente sus propios componentes, manteniendo su organización e identidad a lo largo del tiempo. El concepto fue propuesto por los biólogos chilenos Humberto Maturana y Francisco Varela (1972) para definir la organización de los seres vivos: una célula es autopoiética porque sus procesos metabólicos producen los mismos componentes (enzimas, membrana) que hacen posible ese metabolismo.
 
¿Aplica la autopoiesis fuera de la biología? El debate es significativo. Los propios autores discreparon: Maturana aceptó extensiones al dominio social; Varela las consideró infructíferas más allá de la vida celular. El sociólogo Niklas Luhmann adoptó el concepto para describir los sistemas sociales como redes autopoiéticas de *comunicaciones* (no de moléculas): una organización produce las comunicaciones que la constituyen como organización.
 
En ingeniería de software, la autopoiesis ofrece una metáfora potente aunque no una equivalencia estricta. Los sistemas de software no se autoproducen en sentido literal, pero los ecosistemas de desarrollo sí exhiben características autopoiéticas: un pipeline de CI/CD produce los artefactos (builds, tests, deploys) que a su vez mantienen y reproducen el pipeline mismo; una comunidad open-source produce el código, la documentación y las normas de contribución que sostienen a la comunidad. Lo importante pedagógicamente es distinguir la autopoiesis como propiedad estricta de los sistemas vivos de sus extensiones metafóricas a otros dominios, y reconocer que la frontera entre "sistema que se automantiene" (homeostasis) y "sistema que se autoproduce" (autopoiesis) marca una diferencia cualitativa fundamental en la jerarquía de Boulding.
 
---
 
## 1.7 El pensamiento sistémico
 
El **pensamiento sistémico** es la capacidad de ver el todo, comprender las interrelaciones entre las partes y reconocer los patrones de comportamiento que emergen de la estructura del sistema. Senge (1990) lo identifica como la disciplina fundamental para comprender organizaciones complejas.
 
Cuatro principios guían el pensamiento sistémico:
 
1. **Mirar relaciones, no solo partes.** Un bug puede no ser un problema del módulo donde se manifiesta sino del flujo de datos que lo alimenta.
2. **Buscar patrones recurrentes, no solo eventos.** Si los deploys fallan todos los viernes, la pregunta no es "¿qué salió mal este viernes?" sino "¿qué estructura produce este patrón?"
3. **Considerar efectos de segundo orden.** Agregar caché mejora la velocidad (efecto directo) pero introduce problemas de consistencia (efecto de segundo orden).
4. **Identificar dónde intervenir con mayor apalancamiento.** Meadows (2008) demostró que la mayoría de las personas interviene donde el apalancamiento es menor (ajustar parámetros) cuando cambiar las reglas del sistema o las metas produce efectos mucho más profundos.
 
### 1.7.1 Arquetipos sistémicos
 
Senge (1990) documentó **arquetipos sistémicos**: patrones estructurales recurrentes que generan comportamientos problemáticos predecibles. Tres son particularmente relevantes en ingeniería de software:
 
- **"Soluciones que fallan":** Un parche rápido (hotfix) resuelve un síntoma pero genera complejidad adicional, que produce más bugs, que requieren más hotfixes. Es el ciclo vicioso de la deuda técnica.
- **"Límites al crecimiento":** El desarrollo rápido de funcionalidades (bucle reforzador) choca con cuellos de botella arquitectónicos (bucle balanceador). Un monolito crece hasta que los cambios se vuelven imposibles de implementar.
- **"Desplazamiento de la carga":** En lugar de arreglar problemas de proceso (solución fundamental), los equipos adoptan más herramientas (solución sintomática), generando proliferación de herramientas y complejidad de integración.
 
Reconocer estos arquetipos permite anticipar problemas y romper ciclos destructivos antes de que escalen.
 
---
 
## 1.8 Conexiones con la ingeniería de software
 
La TGS no es un tema abstracto desconectado de la práctica. Los siguientes conceptos muestran cómo los principios sistémicos se manifiestan concretamente en el desarrollo de software:
 
### 1.8.1 La Ley de Conway (1967) 
Establece que las organizaciones que diseñan sistemas producen diseños que son copias de sus estructuras de comunicación. Si hay tres equipos, el sistema tendrá tres componentes principales, no porque sea la mejor arquitectura sino porque es la que la organización puede producir. La *maniobra inversa de Conway* consiste en reestructurar deliberadamente los equipos para producir la arquitectura deseada.
 
### 1.8.2 La Parábola de los Relojeros (Simon, 1962)
Demuestra que los sistemas complejos que poseen formas intermedias estables evolucionan mucho más rápido que los que no las tienen. El desarrollo iterativo e incremental (construir y validar incrementos pequeños que funcionan por sí solos) es radicalmente más eficiente que el desarrollo secuencial donde cualquier interrupción destruye el avance parcial.
 
### 1.8.3 La Ley de Variedad Requerida (Ashby, 1956)
Dice que un regulador debe tener al menos tanta variedad como el sistema que intenta controlar. Si un sistema puede fallar de 500 formas distintas pero la suite de tests solo cubre 50 escenarios, es matemáticamente imposible garantizar estabilidad. Esto fundamenta la necesidad de técnicas complementarias de testing: pruebas basadas en propiedades, fuzzing, chaos engineering.
 
### La cibernética de segundo orden (von Foerster, 1974)
Nos recuerda que el observador siempre es participante del sistema que estudia. En software, esto se manifiesta en los *Heisenbugs*: errores que desaparecen al intentar observarlos, porque el propio código de depuración altera el comportamiento del sistema. Nunca estamos completamente "fuera" del sistema que construimos.
 
### La Ley de Gall (Gall, 1975)
Establece que "un sistema complejo que funciona se encuentra invariablemente que ha evolucionado a partir de un sistema simple que funcionaba. Un sistema complejo diseñado desde cero nunca funciona y no puede ser reparado para que funcione. Hay que empezar de nuevo con un sistema simple que funcione." Esta ley, formulada en *The Systems Bible*, complementa la Parábola de los Relojeros de Simon con una advertencia más contundente: no solo es *más eficiente* construir incrementalmente, sino que es la *única forma* de lograr un sistema complejo funcional. La Ley de Gall fundamenta desde la teoría de sistemas las prácticas de desarrollo iterativo, los prototipos evolutivos, y la estrategia de MVP (Producto Mínimo Viable): comenzar con algo simple que funcione y evolucionar desde ahí, en lugar de diseñar la complejidad final desde el inicio. Gall también enuncia la Primera Ley de Supervivencia de Sistemas: "un sistema que ignora la retroalimentación ya ha iniciado el proceso de inestabilidad terminal", conectando directamente con los conceptos de retroalimentación y homeostasis vistos anteriormente.
 
---
 
## Bibliografía
 
- Ackoff, R. L. (1971). *Towards a System of Systems Concepts*. Management Science, 17(11), 661–671.
- Ashby, W. R. (1956). *An Introduction to Cybernetics*. Chapman & Hall.
- Bertalanffy, L. von. (1968). *General System Theory: Foundations, Development, Applications*. George Braziller.
- Boulding, K. E. (1956). *General Systems Theory — The Skeleton of Science*. Management Science, 2(3), 197–208.
- Checkland, P. (1999). *Systems Thinking, Systems Practice*. Wiley.
- Churchman, C. W. (1968). *The Systems Approach*. Dell Publishing.
- Conway, M. (1967). *How Do Committees Invent?* Datamation, 14(5), 28–31.
- Forrester, J. W. (1961). *Industrial Dynamics*. MIT Press.
- Gall, J. (2002). *The Systems Bible: The Beginner's Guide to Systems Large and Small* (3rd ed.). General Systemantics Press. (Original: *General Systemantics*, 1975).
- Maturana, H. R. y Varela, F. J. (1972). *De máquinas y seres vivos: Autopoiesis — La organización de lo vivo*. Editorial Universitaria. (Edición en inglés: *Autopoiesis and Cognition: The Realization of the Living*. D. Reidel, 1980).
- Meadows, D. H. (2008). *Thinking in Systems: A Primer*. Chelsea Green Publishing.
- Morin, E. (1990). *Introducción al pensamiento complejo*. Gedisa.
- Senge, P. M. (1990). *The Fifth Discipline: The Art and Practice of the Learning Organization*. Doubleday.
- Simon, H. A. (1962). *The Architecture of Complexity*. Proceedings of the American Philosophical Society, 106(6), 467–482.
- Skyttner, L. (2005). *General Systems Theory: Problems, Perspectives, Practice* (2nd ed.). World Scientific.
- von Foerster, H. (1974). *Cybernetics of Cybernetics*. University of Illinois.
