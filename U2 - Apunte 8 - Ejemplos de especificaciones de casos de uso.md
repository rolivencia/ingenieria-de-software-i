# Especificaciones de ejemplo, un caso por nivel

### Traducción al español de tres casos de uso de Alistair Cockburn, *The Mini-Book on Use Cases* (2025)

> Los tres ejemplos siguientes son **traducciones fieles** de casos de uso del libro, elegidos para mostrar cómo luce una especificación formal en cada altitud. Se conservan el encabezado, el escenario principal de éxito y las extensiones, incluidas las notas y preguntas abiertas que el autor deja a propósito (*"¿qué hace el sistema aquí?"*) para mostrar el trabajo "en vuelo".

---

## Nivel KITE (cometa / resumen de negocio)

### Caso de uso 7: `+Cobrar por un accidente de automóvil` *(estilo formal)*

```
Sistema:        Compañía de seguros
Actor primario: Reclamante
Nivel de meta:  Resumen de negocio (kite)

Escenario principal de éxito:
1. El reclamante presenta el reclamo con datos que lo respaldan.
2. La compañía de seguros verifica que el reclamante posee una póliza válida.
3. La compañía de seguros asigna un perito para examinar el caso.
4. La compañía de seguros verifica que todos los detalles se ajustan a las
   condiciones de la póliza.
5. La compañía de seguros paga al reclamante y cierra el expediente.

Extensiones:
1a. Los datos presentados están incompletos:
      .1 La compañía solicita la información faltante.
      .2 El reclamante aporta la información faltante.

2a. El reclamante no posee una póliza válida:
      La compañía rechaza el reclamo, notifica al reclamante, registra todo
      esto y da por terminadas las actuaciones.

3a. No hay peritos disponibles en este momento.
      (¿Qué hace la compañía de seguros aquí?)

4a. El accidente infringe condiciones básicas de la póliza:
      La compañía rechaza el reclamo, notifica al reclamante, registra todo
      esto y da por terminadas las actuaciones.

4b. El accidente infringe algunas condiciones menores de la póliza:
      La compañía inicia una negociación con el reclamante sobre el monto a pagar.
```

**Por qué es kite:** describe el **flujo de negocio completo** de extremo a extremo (de presentar el reclamo a cobrar y cerrar el expediente). El "sistema" es **toda la compañía**, y su propósito es dar **contexto** del macroproceso, no enlazar casos de bajo nivel. Transcurre a lo largo de días o semanas. El prefijo `+` señala el nivel de un vistazo. Nótese la pregunta abierta en la extensión 3a: una marca deliberada de algo que todavía hay que investigar.

---

## Nivel del mar / SEA-LEVEL (tarea de usuario)

### Caso de uso 4: `Inscribirse en materias` *(estilo formal)*

```
Sistema:        Sistema de Inscripción a Materias (SIM)
Actor primario: Estudiante
Nivel de meta:  Nivel del mar (tarea de usuario)

Escenario principal de éxito:
1. El estudiante solicita armar un plan de cursada.
2. El SIM prepara un formulario de cursada en blanco.
3. El SIM obtiene las materias disponibles del Sistema de Catálogo de Materias.
4. El estudiante selecciona hasta cuatro materias principales y dos alternativas.
5. Para cada materia, el SIM verifica que el estudiante tenga las correlativas
   necesarias y lo agrega a la materia, marcándolo como "inscripto" en esa
   materia dentro del plan.
6. El estudiante indica que el plan está completo; el SIM lo guarda.

Extensiones:
1a. El estudiante ya tiene un plan de cursada:
      El SIM abre la versión actual del plan para editarla, en lugar de crear
      uno nuevo.

1b. El cuatrimestre actual está cerrado y el siguiente aún no abrió:
      El SIM permite al estudiante mirar las materias, pero no crear un plan nuevo.

3a. El Sistema de Catálogo de Materias no responde:
      El SIM notifica al estudiante y el caso de uso termina.

5a. La materia está llena o el estudiante no cumple todas las correlativas:
      El SIM deshabilita la selección de esa materia y notifica al estudiante.
```

**Por qué es nivel del mar:** es una **tarea de usuario** que se completa **de una sentada** (minutos), con una meta concreta y atómica para el actor primario. El "sistema" es **una aplicación específica** (el SIM). Aparecen actores secundarios (el Sistema de Catálogo de Materias) que el caso nombra sin desarrollar. Este es el nivel **por defecto** y el más abundante en un proyecto.

> *Nota de traducción:* se adaptó el vocabulario al contexto universitario argentino —*"course" → materia*, *"prerequisites" → correlativas*, *"semester" → cuatrimestre*, *"schedule" → plan de cursada*— para que el ejemplo resulte inmediato a los estudiantes. La estructura del caso es idéntica a la del original.

---

## Nivel FISH (pez / subfunción)

### Caso de uso 11: `–Iniciar sesión con email/contraseña` *(estilo formal)*

```
Sistema:        OurApp (nuestra aplicación)
Actor primario: Cualquier usuario
Nivel de meta:  Fish (subfunción)
Disparador:     Se solicitó iniciar sesión usando email y contraseña.

Escenario principal de éxito:
1. El sistema recoge el email y la contraseña del usuario.
2. El sistema valida que el email y la contraseña sean correctos.
3. El sistema marca el inicio de sesión como exitoso.

Extensiones:
1a. El sistema detecta que la cuenta fue bloqueada por intentos fallidos previos:
      .1 El sistema pide al usuario restablecer la contraseña o contactar a
         atención al cliente.

2a. La combinación email/contraseña no es correcta:
      El sistema concede al usuario dos intentos más.

2b. Se agotaron todos los intentos y siguen sin ser correctos:
      .1 El sistema marca la cuenta como bloqueada.
      .2 El sistema notifica al usuario que la cuenta se está bloqueando y que
         contacte a atención al cliente.
      .3 El sistema termina este caso de uso con el inicio de sesión marcado
         como fallido.

2c. En cualquier momento, el usuario puede pedir restablecer su contraseña:
      El sistema permite al usuario restablecer la contraseña.
```

**Por qué es fish:** *Iniciar sesión* **no aporta valor de negocio por sí mismo**, pero el flujo es complejo (muchos modos de fallo y recuperación) y se **reutiliza** en varios casos de nivel del mar, así que se escribe aparte. El prefijo `–` lo marca como subfunción. Cockburn ofrece esta variante (email/contraseña) **como modelo**, sugiriendo escribir cada vía de login —*Single Sign-On*, Google, Facebook, Apple— como su propio caso fish. Nótese también el campo `Disparador`, útil cuando se quiere que la escritura arranque después de que el caso ya fue activado.

---

## Resumen de los ejemplos

| Nivel | Caso de ejemplo | Sistema | Señal distintiva |
|---|---|---|---|
| **Kite** `+` | Cobrar por un accidente de automóvil | Toda la compañía | Macroproceso de días/semanas; da contexto |
| **Sea-level** | Inscribirse en materias | Una aplicación (SIM) | Tarea de una sentada; el nivel por defecto |
| **Fish** `–` | Iniciar sesión con email/contraseña | Una aplicación (OurApp) | Subfunción compleja y/o reutilizada |

> Recordatorio: el nivel **clam** (almeja) no se ilustra porque, por definición, **no se escribe** como caso de uso. Ejemplos de clam serían *"hacer clic en Guardar"* o *"validar que el campo email tenga formato válido"*.

---

## Referencia

- Cockburn, A. (2025). *The Mini-Book on Use Cases* (The Simplifying Series). Humans and Technology Press. Casos de uso 7, 4 y 11. El caso 4 está adaptado por Cockburn de Adolph, S. & Bramble, P., *Patterns for Effective Use Cases*; el caso 11 es de un proyecto real referido en *Writing Effective Use Cases* (2000).
