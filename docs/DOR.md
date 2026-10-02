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
| 1 | Sí | Cumple: los criterios permiten probar credenciales válidas e inválidas, además de los permisos por perfil. |
| 2 | Sí | Cumple: el acceso según el perfil coincide con el alcance de RF-01. |
| 3 | Sí | La minuta documenta la validación del requisito RF-01 por parte de un stakeholder. |
| 4 | Sí | Cumple: permite que cada usuario acceda a las funciones correspondientes a su perfil. |
| 5 | Sí | Cumple: puede desarrollarse como una capacidad delimitada de acceso al sistema. |
| 6 | Sí | Si tenemos armados los datos de prueba necesarios. |
| 7 | Sí | Si, está contempleado el tiempo de desarrollo y la capacidad del equipo. |

---

### Historia 2 — [HU-04 — Registrar una incidencia desde el formulario web]

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | No | Especificar los formatos y tamaños permitidos para imágenes y documentos adjuntos, para que QA pueda comprobarlos. |
| 2 | Sí | Cumple: RF-04 y RF-06 contemplan el registro de incidencias y el uso de adjuntos. |
| 3 | Sí | La minuta documenta la validación de los requisitos RF-04 y RF-06 por parte de un stakeholder. |
| 4 | Sí | Cumple: permite al Solicitante reportar fallas o solicitudes técnicas para su gestión. |
| 5 | Sí | Si cumple. La historia tiene independencia al menos con historias del mismo sprint. |
| 6 | Sí | Si tenemos armados los datos de prueba necesarios. |
| 7 | Sí | Se estimó el flujo completo, incluidas sus validaciones y adjuntos, y se comprobó que entra en la capacidad del sprint. |

---

### Historia 3 — [HU-10 — Asignar prioridad a una incidencia]

| Ítem (según checklist) | ¿Pasa? | Qué le falta (si no pasa) |
|-------------------------|--------|-----------------------------|
| 1 | Sí | Brindan el detalle necesario según los casos de uso.
| 2 | Sí | Si cumple, las reglas de negocio son claras. |
| 3 | Sí | La minuta documenta la validación del requisito RF-11 por parte de un stakeholder. |
| 4 | Sí | Cumple: asignar prioridades ayuda a ordenar la atención de las incidencias. |
| 5 | Sí | Cumple: la asignación de prioridad es una capacidad delimitada y puede tratarse sobre incidencias ya registradas. |
| 6 | Sí | Si tenemos armados los datos de prueba necesarios.|
| 7 | Sí  | Se estimó el flujo completo y se comprobó que entra en la capacidad del sprint. |