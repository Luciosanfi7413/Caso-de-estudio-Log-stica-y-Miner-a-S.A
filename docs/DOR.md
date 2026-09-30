# Definition of Ready (DoR)

_Antes de que una historia entre a desarrollo, tiene que pasar un filtro: el Definition of Ready. Es un acuerdo del equipo sobre qué condiciones mínimas debe cumplir una historia para considerarse "lista para trabajar". Si no las cumple, vuelve a refinamiento._

---

## Checklist del equipo

| # | Ítem | Justificación (qué problema evita, máx. 3 renglones) |
|---|------|--------------------------------------------------------|
| 1 | ¿Los criterios de aceptación brindan el detalle necesario para que QA verifique la calidad de la historia? | Evita ambigüedades durante las pruebas y permite determinar objetivamente si la funcionalidad cumple con lo esperado. |
| 2 | ¿La historia aporta reglas de negocio que sean inconsistentes con reglas de negocios actuales? | Evita desarrollar funcionalidades que contradigan procesos, restricciones o comportamientos ya definido. |
| 3 | La funcionalidad de la historia fue validada previamente por algun stakeholder?  | Evita avanzar con funcionalidades que no respondan a una necesidad real o que no hayan sido validadas por los interesados correspondientes.|
| 4 | ¿La historia aporta valor agregado? | Evita destinar capacidad del equipo a funcionalidades que no generen un beneficio concreto para el proyecto. |
| 5 |¿La historia es independiente de otras historias de un mismo sprint? | Evita bloqueos durante el sprint por depender de funcionalidades o tareas que todavía no se encuentran disponibles. |
| 6 | ¿El quipo de QA tiene lo necesario para realizar todas las pruebas? | Evita que una historia llegue a la etapa de pruebas sin poder ser verificada por falta de datos, accesos o información necesaria. |
| 7 | - ¿El tamaño de la historia se ajusta a la capacidad disponible por sprint? | Evita incorporar historias que no puedan completarse dentro del sprint por exceder la capacidad disponible del equipo. |

---

## Aplicación a tres historias propias

_Elegir TRES historias de usuario del trabajo del primer semestre y pasarlas por nuestro checklist. Es esperable —y deseable— que alguna no pase._

### Historia 1 — [HU-01 — Iniciar sesión según el perfil del usuario]

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
 1 | Sí | — |
| 2 | Sí | — |
| 3 | Pendiente | No se documenta la validación de la historia por parte de un stakeholder. |
| 4 | Sí | — |
| 5 | Sí | — |
| 6 | Pendiente | Identificar o preparar las cuentas de prueba para verificar credenciales válidas, inválidas y permisos por perfil. |
| 7 | Pendiente | Incorporar la estimación de esfuerzo y compararla con la capacidad del sprint. |

---

### Historia 2 — [HU-04 — Registrar una incidencia desde el formulario web]

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | No | Precisar los formatos y tamaños permitidos para los archivos adjuntos, para que QA pueda probarlos objetivamente. |
| 2 | Sí | La historia es consistente con RF-04 y RF-06, que contemplan el registro y los adjuntos. |
| 3 | Pendiente | No se documenta la validación de la funcionalidad por parte de un stakeholder. |
| 4 | Sí | — |
| 5 | Pendiente | Identificar cómo se obtiene y mantiene el registro de elementos afectados que se validan durante el alta. |
| 6 | No | Preparar datos de prueba para elementos registrados y no registrados, incidencias abiertas y archivos válidos e inválidos. |
| 7 | No | Revisar el tamaño de la historia: reúne varias validaciones y el manejo de adjuntos; falta estimar si entra en un sprint. |

---

### Historia 3 — [HU-10 — Asignar prioridad a una incidencia]

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | No | Definir los niveles de urgencia e impacto y los criterios concretos para asignar una prioridad. |
| 2 | No | Contrastar la regla de prioridad con las reglas de negocio vigentes; todavía no está especificada la relación entre urgencia, impacto y prioridad. |
| 3 | Pendiente | Validar la regla de prioridad con el stakeholder responsable de definirla. |
| 4 | Sí | Ayuda a ordenar la atención de las incidencias. |
| 5 | Sí | Puede desarrollarse como una funcionalidad delimitada; presupone que ya existen incidencias para priorizar. |
| 6 | No | Preparar casos de prueba que cubran las combinaciones de urgencia e impacto y la prioridad esperada para cada una. |
| 7 | No | Completar la regla de prioridad y estimar el esfuerzo antes de confirmar que la historia entra en el sprint. |