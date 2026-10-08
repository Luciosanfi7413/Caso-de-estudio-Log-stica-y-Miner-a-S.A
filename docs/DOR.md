# Definition of Ready (DoR)

_Antes de que una historia entre a desarrollo, tiene que pasar un filtro: el Definition of Ready. Es un acuerdo del equipo sobre qué condiciones mínimas debe cumplir una historia para considerarse "lista para trabajar". Si no las cumple, vuelve a refinamiento._

---
## Checklist del equipo

| # | Ítem | Justificación (qué problema evita, máximo 3 renglones) |
|---|------|----------------------------------------------------------|
| 1 | ¿Los criterios de aceptación describen resultados observables y verificables para que QA pueda comprobar si la historia cumple lo esperado? | Evita interpretaciones distintas sobre cuándo la funcionalidad está terminada y permite diseñar pruebas con resultados claros. |
| 2 | ¿Las reglas de negocio de la historia son consistentes con las vigentes y están documentadas? | Evita desarrollar comportamientos que contradigan reglas acordadas o que generen resultados inconsistentes. |
| 3 | ¿La necesidad y las reglas asociadas fueron validadas por el stakeholder responsable, y existe evidencia de esa validación? | Evita avanzar con necesidades que no fueron confirmadas por los interesados responsables. La evidencia permite rastrear la decisión. |
| 4 | ¿La historia identifica quién recibe el valor y qué beneficio concreto obtiene? | Evita trabajar en funcionalidades cuyo aporte al usuario o al negocio no está claro. |
| 5 | ¿La historia puede desarrollarse y probarse sin depender de otra historia que todavía no esté disponible en el sprint? | Evita bloqueos durante el sprint por dependencias pendientes. |
| 6 | ¿QA cuenta con los datos, accesos y entornos necesarios para probar la historia? | Evita que las pruebas se retrasen o no puedan ejecutarse por falta de recursos o información. |
| 7 | ¿La historia tiene una estimación y su esfuerzo es compatible con la capacidad del sprint previsto? | Evita comprometer en el sprint una historia que exceda la capacidad disponible del equipo. |
| 8 | ¿La historia contempla los flujos alternativos y las excepciones relevantes para su funcionamiento? | Evita que queden sin definir respuestas ante errores, datos inválidos o situaciones fuera del flujo principal. |
| 9 | ¿Los requisitos no funcionales aplicables están identificados y expresados de forma verificable, o se justifica que no aplican? | Evita omitir condiciones de calidad necesarias, como seguridad, rendimiento o compatibilidad. |

---

## Aplicación a tres historias propias

_Elegir TRES historias de usuario del trabajo del primer semestre y pasarlas por nuestro checklist. Es esperable —y deseable— que alguna no pase._

### Historia 1 — [HU-01 — Iniciar sesión según el perfil del usuario]

| Ítem (según checklist) | ¿Pasa? | Evidencia / qué le falta |
|-------------------------|--------|-----------------------------|
| 1 | Sí | Los criterios permiten comprobar el inicio de sesión con credenciales válidas, el acceso según perfil y el rechazo de credenciales inválidas. Evidencia: HU-01, criterios 1 a 3. |
| 2 | Sí | El acceso con credenciales individuales y las funciones habilitadas según el perfil son consistentes con RF-01. |
| 3 | Sí | La necesidad de autenticar usuarios autorizados y habilitar funciones según su perfil fue validada durante el relevamiento; consta en la minuta del equipo. |
| 4 | Sí | La historia expresa el beneficio para el usuario: acceder a las funciones habilitadas para su perfil. |
| 5 | Sí | La historia tiene un alcance delimitado a la autenticación y al acceso según perfil; puede desarrollarse y probarse como una capacidad independiente. |
| 6 | Sí | Se definieron pruebas con credenciales válidas e inválidas para los perfiles Solicitante, Responsable de Sistemas y Especialista Externo habilitado, verificando el acceso y las funciones disponibles para cada perfil. |
| 7 | Sí | El equipo estimó HU-01 en 3 puntos con la escala Fibonacci. La planificación de las tres historias suma 14 puntos, dentro de la capacidad de referencia de 16 puntos para el sprint. |
| 8 | Sí | HU-01 contempla el flujo alternativo de credenciales inválidas: impide el acceso e informa que no se pudo iniciar sesión. Evidencia: criterio de aceptación 3. |
| 9 | Sí | RNF-01 establece que las credenciales deben transmitirse mediante HTTPS con TLS 1.2 o superior, un requisito de seguridad aplicable al inicio de sesión. |

---

### Historia 2 — [HU-04 — Registrar una incidencia desde el formulario web]

| Ítem (según checklist) | ¿Pasa? | Evidencia / qué le falta |
|-------------------------|--------|--------------------------|
| 1 | Sí | HU-04 define los datos del registro y las condiciones de validación de campos, elemento afectado y archivos. Evidencia: criterios de aceptación de HU-04. |
| 2 | Sí | Las reglas de registro y adjuntos son consistentes con RF-04, RF-06 y CU-01. |
| 3 | Sí | El stakeholder validó la necesidad y las reglas del registro durante el relevamiento; consta en la minuta del equipo. |
| 4 | Sí | HU-04 identifica el beneficio: que Sistemas reciba la información necesaria para gestionar la falla o solicitud técnica. |
| 5 | Sí | HU-04 valida el identificador contra el registro de elementos existentes. La administración de ese registro no forma parte de esta historia ni la condiciona. |
| 6 | Sí | Se definieron pruebas con elementos registrados sin incidencias abiertas, elementos con incidencias abiertas e identificadores inexistentes. Para los adjuntos se probarán imágenes PNG y JPEG de hasta 15 MB, formatos no permitidos y archivos que superen el límite. |
| 7 | Sí | El equipo estimó HU-04 en 8 puntos con la escala Fibonacci. La planificación de las tres historias suma 14 puntos, dentro de la capacidad de referencia de 16 puntos para el sprint. |
| 8 | Sí | CU-01 contempla campos obligatorios incompletos, identificador inválido, incidencia abierta para el elemento y archivos no permitidos. Evidencia: excepciones E1-E4 de CU-01. |
| 9 | Sí | Los requisitos aplicables están definidos en RNF-06, RNF-08 y RNF-11: duración del registro, rendimiento y mensajes de validación. |

---

### Historia 3 — [HU-10 — Asignar prioridad a una incidencia]

| Ítem (según checklist) | ¿Pasa? | Evidencia / qué le falta |
|-------------------------|--------|--------------------------|
| 1 | Sí | Los criterios de aceptación de HU-10 permiten comprobar la selección y el guardado de una prioridad. Evidencia: `historias-de-usuario.md`, HU-10. |
| 2 | Sí | La asignación directa de prioridad es consistente con las opciones acordadas: Baja, Media, Alta y Vital. Evidencia: RF-11 y CU-04. |
| 3 | Sí | El stakeholder validó la necesidad y la regla de prioridad del RF-11 durante el relevamiento; consta en la minuta del equipo. |
| 4 | Sí | HU-10 identifica el beneficio: asignar prioridades ayuda a ordenar la atención de las incidencias. |
| 5 | Sí | La historia puede trabajarse sobre incidencias ya registradas y no depende de completar otra historia dentro del mismo sprint. |
| 6 | Sí | Se definieron pruebas con incidencias sin prioridad y con una prioridad previa, verificando la asignación de Baja, Media, Alta y Vital, la actualización de una prioridad y el intento de guardar sin seleccionar una opción. |
| 7 | Sí | El equipo estimó HU-10 en 3 puntos con la escala Fibonacci. La planificación de las tres historias suma 14 puntos, dentro de la capacidad de referencia de 16 puntos para el sprint. |
| 8 | Sí | HU-10 define que, si no se selecciona una prioridad, “Guardar” permanece deshabilitado y la incidencia no se modifica. Evidencia: criterios de aceptación de HU-10 y excepción E1 de CU-04. |
| 9 | Sí | RNF-08 y el campo Rendimiento de CU-04 definen el tiempo máximo para guardar cambios con hasta 50 usuarios conectados. |