# Ejercicio: partir una épica en slices verticales

## La épica

> Ciclo completo de un ticket, desde apertura hasta cierre con derivación externa.

---

## Parte A — Historias verticales
1. HU-04 — Registrar una incidencia desde el formulario web.
2. HU-06 — Consultar las incidencias propias.
3. HU-12 — Asignar o reasignar el responsable.
4. HU-13 — Informar imposibilidad de atender una incidencia asignada.
5. HU-08 — Consultar incidencias asignadas al especialista externo.
6. HU-14 — Actualizar el estado como Especialista Externo.
7. HU-17 — Registrar la resolución final y cerrar una incidencia.

## HU-04 — Registrar una incidencia desde el formulario web

| Campo | Detalle |
|-------|---------|
| Historia | Como Solicitante, quiero registrar una falla o solicitud técnica con los datos del elemento afectado, para que el área de Sistemas pueda gestionarla. |
| Módulo |Módulo 2 — Registro de incidencias |
| Requisitos relacionados |RF-04, RF-06|

### Criterios de aceptación

1. El sistema deberá permitir informar el tipo de incidencia, el elemento afectado, su identificador y la descripción del problema.
2. El sistema deberá permitir adjuntar una o más imágenes relacionadas con la incidencia.
3. El sistema deberá validar que los campos obligatorios estén completos, que el elemento afectado esté registrado y que no tenga otra incidencia cuyo estado sea distinto de “Cerrado”. Si alguna validación falla, deberá impedir el registro e informar el motivo.
4. Al confirmar un registro válido, el sistema deberá asociar la incidencia al Solicitante, asignarle un identificador único y establecer su estado inicial como Nuevo.
5. Si un dato obligatorio o un archivo no cumple las condiciones definidas, el sistema deberá explicar el error y conservar los demás datos ingresados.
6. El sistema deberá permitir adjuntar imágenes en formato PNG o JPEG, con un tamaño máximo de 15 MB por archivo.
---

## HU-06 — Consultar las incidencias propias

| Campo | Detalle |
|-------|---------|
| Historia | Como Solicitante, quiero consultar mis incidencias y su estado, para conocer cómo avanza su atención y quién está a cargo. |
| Módulo |Módulo 3 — Consulta y seguimiento de incidencias|
| Requisitos relacionados |RF-07|

### Criterios de aceptación

1. El sistema deberá mostrar al Solicitante únicamente las incidencias asociadas a su identidad.
2. El listado deberá informar, como mínimo, el identificador, tipo, elemento afectado, estado y responsable asignado.
3. Al seleccionar una incidencia, el sistema deberá mostrar su detalle y estado actual.
4. Si el Solicitante no tiene incidencias registradas, el sistema deberá informarlo.

---
## HU-12 — Asignar o reasignar el responsable

| Campo | Detalle |
|-------|---------|
| Identificador | HU-12 |
| Historia | Como Responsable de Sistemas, quiero asignar o reasignar una incidencia a un responsable interno o a un Especialista Externo habilitado, para definir quién estará a cargo de su atención. |
| Módulo | Módulo 4 — Gestión y asignación de incidencias |
| Requisitos relacionados | RF-13 |

### Criterios de aceptación

1. El sistema deberá permitir seleccionar una incidencia y consultar su responsable actual, si lo tiene.
2. El sistema deberá permitir elegir entre un responsable interno y un Especialista Externo.
3. Si se elige un Especialista Externo, el sistema deberá mostrar únicamente especialistas habilitados para nuevas asignaciones.
4. Al confirmar, el sistema deberá asociar el nuevo responsable a la incidencia, registrar el cambio e informar al Solicitante.

---

## HU-13 — Informar imposibilidad de atender una incidencia asignada

| Campo | Detalle |
|-------|---------|
| Identificador | HU-13 |
| Historia | Como Especialista Externo, quiero informar que no podré hacerme cargo de una incidencia que tengo asignada, para que el Responsable de Sistemas pueda reasignarla. |
| Módulo | Módulo 4 — Gestión y asignación de incidencias |
| Requisitos relacionados | RF-14 |

### Criterios de aceptación

1. El sistema deberá permitir al Especialista Externo seleccionar una incidencia abierta que tenga asignada.
2. El sistema deberá ofrecer la opción “Informar que no podré hacerme cargo”.
3. Al confirmar el aviso, el sistema deberá registrar la información y asociarla a la incidencia y al Especialista Externo que la realizó.
4. El sistema deberá informar al Responsable de Sistemas que la incidencia requiere una nueva asignación.
5. El sistema no deberá reasignar automáticamente la incidencia; el Responsable de Sistemas deberá seleccionar al nuevo responsable.

---

## HU-08 — Consultar incidencias asignadas al especialista externo

| Campo | Detalle |
|-------|---------|
| Historia |Como Especialista Externo habilitado, quiero consultar las incidencias que me asignaron, para conocer la información necesaria para atenderlas. |
| Módulo |Módulo 3 — Consulta y seguimiento de incidencias|
| Requisitos relacionados |RF-09|

### Criterios de aceptación

1. El sistema deberá mostrar al Especialista Externo únicamente las incidencias que tenga asignadas.
2. El listado deberá informar el identificador, tipo, elemento afectado, estado y prioridad de cada incidencia.
3. Al seleccionar una incidencia, el sistema deberá mostrar la información necesaria para su atención, incluida su descripción y los archivos adjuntos disponibles.
4. El sistema no deberá permitir que un especialista consulte incidencias asignadas a otro responsable.

---

## HU-14 — Actualizar el estado como Especialista Externo

| Campo | Detalle |
|-------|---------|
| Identificador | HU-14 |
| Historia | Como Especialista Externo, quiero actualizar el estado de una incidencia que tengo asignada, para reflejar el avance de su atención. |
| Módulo | Módulo 4 — Gestión y asignación de incidencias |
| Requisitos relacionados | RF-12, CU-11 |

### Criterios de aceptación

1. El sistema deberá permitir al Especialista Externo modificar el estado únicamente de las incidencias que tenga asignadas.
2. El sistema deberá ofrecer los estados habilitados para este actor: “En curso”, “Pendiente” y “Resuelto”.
3. El sistema deberá permitir revisar el nuevo estado antes de guardar.
4. Al confirmar, el sistema deberá actualizar el estado de la incidencia, registrar el cambio en el historial y notificar al Solicitante.

---

## HU-17 — Registrar la resolución final y cerrar una incidencia

| Campo | Detalle |
|-------|---------|
| Identificador | HU-17 |
| Historia | Como Responsable de Sistemas, quiero registrar la resolución final de una incidencia y cerrarla, para dejar constancia de su solución y finalizar su gestión. |
| Módulo | Módulo 5 — Resolución e historial de intervenciones |
| Requisitos relacionados | RF-17 |

### Criterios de aceptación

1. El sistema deberá permitir registrar una resolución final cuando la incidencia se encuentre en estado “Resuelto”.
2. El sistema deberá exigir la descripción de la resolución final antes de confirmar.
3. La ausencia de acciones previas no deberá impedir registrar la resolución final.
4. Al confirmar, el sistema deberá incorporar la resolución al historial y establecer el estado de la incidencia como “Cerrado”.
5. El sistema deberá informar al Solicitante sobre el cierre de la incidencia.

---


## Parte B — Los caminos que no salen bien

_Elijan UNA de las historias de la Parte A. Las últimas tres preguntas son las importantes:
para cada una, indiquen qué debería hacer el sistema y quién tendría que decidirlo._

**Historia elegida:** ## HU-04 — [Registrar una incidencia desde el formulario web]

| Pregunta | Qué hace el sistema | Quién decide y por qué |
|----------|---------------------|-------------------------|
| ¿Qué pasa si el Solicitante intenta registrar la incidencia sin completar uno o más campos obligatorios? | Informa cuáles son los campos pendientes, los destaca e impide el registro, conservando los datos ingresados. | Analista: define cómo se expresa y se verifica la validación en la funcionalidad, de acuerdo con los campos obligatorios establecidos. |
| ¿Qué pasa si el Solicitante ingresa un identificador que no corresponde a un elemento registrado? | Informa que el identificador no pertenece a un elemento registrado e impide continuar hasta ingresar uno válido. | Negocio: define que solo se pueden registrar incidencias sobre elementos reconocidos por la organización. |
| ¿Qué pasa si el Solicitante ingresa el identificador de un elemento que ya posee una incidencia abierta? | Informa el identificador y el estado de la incidencia existente e impide crear otra para ese elemento mientras la anterior permanezca abierta. | Negocio: define la regla operativa para evitar que varias incidencias abiertas dupliquen el seguimiento de un mismo elemento. |
| ¿Qué pasa si el Solicitante intenta adjuntar una imagen que no cumple las condiciones de formato o tamaño? | Rechaza el archivo, informa las condiciones que incumple y conserva los demás datos ingresados. | Técnica: determina cómo validar y procesar los archivos de acuerdo con los formatos y el límite definidos en los requisitos. |
| ¿Qué pasa si ocurre una desconexión o un error del servidor al presionar “Confirmar”? | Informa que no pudo confirmar la operación. Si el Solicitante reintenta, verifica si la incidencia ya se registró y evita crear un duplicado. | Técnica: define cómo controlar la operación y los reintentos para evitar registros duplicados ante un error de comunicación. |
| ¿Qué pasa si el Solicitante hace doble clic en “Confirmar”? | Procesa una sola solicitud de registro. Deshabilita temporalmente el botón y, si recibe dos envíos, evita crear una segunda incidencia y muestra la confirmación del registro existente. | Técnica: define el control de envíos repetidos para que una doble interacción no genere registros duplicados. |

---

## Parte C — Defensa

_Se hace oral, en el plenario. No se documenta en este archivo_