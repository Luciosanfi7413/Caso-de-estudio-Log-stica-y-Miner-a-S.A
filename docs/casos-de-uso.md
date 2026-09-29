# Casos de uso

## Diagrama general

_Incluir el código PlantUML en `diagramas/casos-de-uso.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

_Describir brevemente los actores identificados y las relaciones principales (include, extend)._

---

## CU-01 — [Registro de incidencia.]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-01 |
| Nombre | Registro de incidencia |
| Descripción | Permite al Solicitante reportar una falla o solicitud técnica mediante un formulario estandarizado que asocia la incidencia a su identidad. |
| Actores | Principal: Solicitante (Empleado) / Secundario: Ninguno |
| Precondiciones | El Solicitante inició sesión en el sistema. |
| Postcondiciones | Éxito: la incidencia queda registrada, asociada al Solicitante, con un identificador único y estado “Nuevo”, disponible para su gestión. / Fallo: la incidencia no se registra y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Solicitante accede a la funcionalidad de registro de incidencias. | El sistema presenta el formulario con los campos Tipo de incidencia, Elemento afectado, Identificador del elemento, Descripción del problema y Adjunto de imágenes (opcional). Para Tipo de incidencia, presenta las opciones “Falla técnica” y “Solicitud técnica”. Para Elemento afectado, presenta las opciones “Equipo informático”, “Dispositivo móvil”, “Vehículo” y “Software / Aplicación”. |
| 2 | El Solicitante selecciona una opción de Tipo de incidencia. | El sistema registra la opción seleccionada. |
| 3 | El Solicitante selecciona una opción de Elemento afectado. | El sistema registra la selección y habilita el campo de identificación correspondiente: código o número de serie para Equipo informático; IMEI o identificador para Dispositivo móvil; patente para Vehículo; y nombre o código de aplicación para Software / Aplicación. |
| 4 | El Solicitante ingresa el identificador del elemento afectado. | El sistema verifica que el identificador corresponda a un elemento registrado y que no exista una incidencia abierta asociada a ese elemento. Si ambas validaciones son correctas, muestra la información correspondiente al elemento y permite continuar. |
| 5 | El Solicitante completa la descripción del problema. | El sistema registra la descripción ingresada en el formulario. |
| 6 | Opcionalmente, el Solicitante adjunta una o más imágenes relacionadas con la incidencia. | El sistema valida el formato y tamaño de los archivos. Si cumplen las condiciones establecidas, los incorpora al formulario e informa que se adjuntaron correctamente. |
| 7 | El Solicitante confirma el registro de la incidencia. | El sistema valida los campos obligatorios y, si la información es correcta, registra la incidencia, la asocia al Solicitante autenticado, le asigna un identificador único, establece el estado “Nuevo” y la deja disponible para su gestión. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Solicitante intenta registrar la incidencia sin completar uno o más campos obligatorios. | El sistema informa cuáles son los campos obligatorios que faltan completar e impide el registro de la incidencia. |
| E2 | El Solicitante ingresa un identificador que no corresponde a un elemento registrado. | El sistema informa que el identificador ingresado no corresponde a un elemento registrado e impide continuar hasta que se ingrese un identificador válido. |
| E3 | El Solicitante ingresa el identificador de un elemento que ya posee una incidencia abierta. | El sistema informa que ya existe una incidencia abierta asociada al elemento, muestra su identificador y estado, e impide registrar una nueva incidencia para el mismo elemento mientras la anterior permanezca abierta. |
| E4 | El Solicitante intenta adjuntar una imagen que no cumple las condiciones establecidas de formato o tamaño. | El sistema rechaza el archivo, informa el motivo y mantiene disponible la información previamente ingresada en el formulario. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El sistema deberá registrar la incidencia y confirmar la operación en un máximo de 3 segundos en al menos el 95 % de los casos, excluyendo el tiempo de transferencia de archivos adjuntos. |
| Frecuencia | Cada vez que un Solicitante necesite reportar una falla o solicitud técnica. La frecuencia dependerá de las incidencias que se produzcan. |
| Importancia | Vital |
| Urgencia | Inmediata |
---

## CU-02 — [Consultar Incidencias Registradas]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-02 |
| Nombre | Consulta de incidencia |
| Descripción | Permite al Solicitante consultar la información de una incidencia registrada y conocer su estado actual y responsable asignado. |
| Actores | Principal: Solicitante (Empleado) / Secundario: Ninguno |
| Precondiciones | Ninguna. |
| Postcondiciones | Éxito: la información de la incidencia queda disponible para su consulta sin modificar su estado ni sus datos. / Fallo: la información solicitada no se muestra y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Solicitante accede a la funcionalidad de consulta de incidencias. | El sistema muestra las incidencias asociadas al Solicitante e informa para cada una su identificador, tipo de incidencia, elemento afectado, estado y responsable asignado. |
| 2 | El Solicitante selecciona una de las incidencias disponibles. | El sistema muestra el detalle de la incidencia seleccionada, incluyendo identificador, tipo de incidencia, elemento afectado, descripción del problema, estado actual y responsable asignado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Solicitante accede a la funcionalidad de consulta y no posee incidencias registradas. | El sistema informa que no existen incidencias asociadas al Solicitante. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La apertura del listado y la consulta del detalle de una incidencia deberán completarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que un Solicitante necesite consultar el estado o el responsable asignado de una incidencia registrada. |
| Importancia | Vital |
| Urgencia | Inmediata |

---
## CU-03 — [Consultar Incidencia ]
| Campo | Detalle |
|-------|---------|
| Identificador | CU-03 |
| Nombre | Consultar incidencias registradas |
| Descripción | Permite al Responsable de Sistemas consultar las incidencias registradas y acceder a la información necesaria para su gestión. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Ninguna. |
| Postcondiciones | Éxito: la información de las incidencias queda disponible para su consulta sin modificar sus datos. / Fallo: la información solicitada no se muestra y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede a la funcionalidad de consulta de incidencias registradas. | El sistema muestra las incidencias registradas e informa para cada una su identificador, tipo de incidencia, elemento afectado, estado, prioridad y responsable asignado. |
| 2 | El Responsable de Sistemas selecciona una de las incidencias disponibles. | El sistema muestra el detalle de la incidencia seleccionada, incluyendo identificador, Solicitante, tipo de incidencia, elemento afectado, descripción del problema, prioridad, estado actual y responsable asignado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Responsable de Sistemas accede a la funcionalidad de consulta y no existen incidencias registradas. | El sistema informa que no existen incidencias registradas para consultar. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La apertura del listado y la consulta del detalle de una incidencia deberán completarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite consultar las incidencias registradas para realizar su gestión. |
| Importancia | Importante |
| Urgencia | Media |
---
## CU-04 — Asignar prioridad a incidencia

| Campo | Detalle |
|-------|---------|
| Identificador | CU-04 |
| Nombre | Asignar prioridad a incidencia |
| Descripción | Permite al Responsable de Sistemas asignar una prioridad a una incidencia registrada considerando su urgencia e impacto. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Debe existir al menos una incidencia registrada. |
| Postcondiciones | Éxito: la incidencia queda registrada con la prioridad asignada. / Fallo: la prioridad no se modifica y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede a la funcionalidad de asignación de prioridad. | El sistema muestra las incidencias registradas e informa para cada una su identificador, Solicitante, tipo de incidencia, elemento afectado, estado y prioridad actual, si posee una. |
| 2 | El Responsable de Sistemas selecciona una de las incidencias disponibles. | El sistema muestra el detalle de la incidencia seleccionada y presenta las opciones disponibles para establecer su urgencia, impacto y prioridad. |
| 3 | El Responsable de Sistemas selecciona el nivel de urgencia correspondiente a la incidencia. | El sistema registra el nivel de urgencia seleccionado. |
| 4 | El Responsable de Sistemas selecciona el nivel de impacto correspondiente a la incidencia. | El sistema registra el nivel de impacto seleccionado. |
| 5 | El Responsable de Sistemas selecciona la prioridad correspondiente considerando la urgencia y el impacto definidos. | El sistema registra la prioridad seleccionada y muestra los valores de urgencia, impacto y prioridad antes de su confirmación. |
| 6 | El Responsable de Sistemas confirma la asignación de prioridad. | El sistema guarda la prioridad en la incidencia y muestra una confirmación de la operación realizada. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Responsable de Sistemas intenta confirmar la asignación sin seleccionar alguno de los valores obligatorios de urgencia, impacto o prioridad. | El sistema informa cuáles son los valores que faltan seleccionar e impide confirmar la asignación. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El guardado de la prioridad deberá completarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite asignar o actualizar la prioridad de una incidencia registrada. |
| Importancia | Importante |
| Urgencia | Vital |
---
## CU-05 — Actualizar estado de incidencia

| Campo | Detalle |
|-------|---------|
| Identificador | CU-05 |
| Nombre | Actualizar estado de incidencia |
| Descripción | Permite al Responsable de Sistemas actualizar el estado de una incidencia registrada de acuerdo con su evolución. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Debe existir al menos una incidencia registrada. |
| Postcondiciones | Éxito: la incidencia queda actualizada con el nuevo estado y el Solicitante es informado del cambio. / Fallo: el estado de la incidencia no se modifica y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede a la funcionalidad de actualización de estado de incidencias. | El sistema muestra las incidencias registradas e informa para cada una su identificador, Solicitante, tipo de incidencia, elemento afectado, prioridad y estado actual. |
| 2 | El Responsable de Sistemas selecciona una de las incidencias disponibles. | El sistema muestra el detalle de la incidencia seleccionada, informa su estado actual y presenta los estados disponibles: “Nuevo”, “En curso”, “Pendiente” y “Resuelto”. |
| 3 | El Responsable de Sistemas selecciona uno de los estados disponibles. | El sistema registra la selección y muestra el estado actual y el nuevo estado seleccionado antes de confirmar el cambio. |
| 4 | El Responsable de Sistemas confirma la actualización del estado. | El sistema actualiza el estado de la incidencia, registra el cambio y notifica al Solicitante informando el nuevo estado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Responsable de Sistemas intenta confirmar la actualización sin seleccionar un nuevo estado. | El sistema informa que debe seleccionar un estado e impide confirmar la actualización. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La actualización del estado deberá guardarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite actualizar el estado de una incidencia de acuerdo con su evolución. |
| Importancia | Importante |
| Urgencia | Vital |
---
## CU-06 — Asignar o reasignar responsable

| Campo | Detalle |
|-------|---------|
| Identificador | CU-06 |
| Nombre | Asignar o reasignar responsable |
| Descripción | Permite al Responsable de Sistemas asignar o reasignar una incidencia a un responsable interno o a un Especialista Externo habilitado. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Debe existir al menos una incidencia registrada. |
| Postcondiciones | Éxito: la incidencia queda asociada al responsable seleccionado y el Solicitante es informado del cambio de asignación. / Fallo: el responsable de la incidencia no se modifica y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede a la funcionalidad de asignación de responsables. | El sistema muestra las incidencias registradas e informa para cada una su identificador, Solicitante, tipo de incidencia, elemento afectado, estado y responsable actual, si posee uno asignado. |
| 2 | El Responsable de Sistemas selecciona una de las incidencias disponibles. | El sistema muestra el detalle de la incidencia, informa el responsable actual, si posee uno, y presenta las opciones “Responsable interno” y “Especialista externo”. |
| 3 | El Responsable de Sistemas selecciona el tipo de responsable. | El sistema muestra los responsables disponibles correspondientes al tipo seleccionado. Si selecciona “Especialista externo”, presenta únicamente los especialistas que se encuentren habilitados. |
| 4 | El Responsable de Sistemas selecciona uno de los responsables disponibles. | El sistema registra la selección y muestra el responsable actual, si corresponde, y el nuevo responsable seleccionado antes de confirmar la asignación. |
| 5 | El Responsable de Sistemas confirma la asignación o reasignación. | El sistema actualiza el responsable de la incidencia, registra el cambio y notifica al Solicitante informando el nuevo responsable asignado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Responsable de Sistemas intenta confirmar la asignación sin seleccionar un responsable. | El sistema informa que debe seleccionar un responsable e impide confirmar la asignación. |
| E2 | El Responsable de Sistemas selecciona la opción “Especialista externo” y no existen especialistas externos habilitados. | El sistema informa que no existen especialistas externos habilitados disponibles para la asignación e impide continuar con esa opción. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La actualización del responsable deberá guardarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite asignar o reasignar una incidencia a un responsable interno o a un Especialista Externo habilitado. |
| Importancia | Importante |
| Urgencia | Vital |

---
## CU-07 — Gestionar especialistas externos

| Campo | Detalle |
|-------|---------|
| Identificador | CU-07 |
| Nombre | Gestionar especialistas externos |
| Descripción | Permite al Responsable de Sistemas registrar especialistas externos y administrar su habilitación para participar en la gestión de incidencias. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Ninguna. |
| Postcondiciones | Éxito: la información y el estado de acceso del Especialista Externo quedan registrados según la operación realizada. / Fallo: la información y el estado de acceso no se modifican y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede a la funcionalidad de gestión de especialistas externos. | El sistema muestra los especialistas externos registrados e informa para cada uno nombre, especialidad, correo electrónico y estado de acceso. Además, presenta la opción “Registrar especialista externo”. |
| 2 | El Responsable de Sistemas selecciona la opción “Registrar especialista externo”. | El sistema presenta un formulario e identifica como campos obligatorios nombre, especialidad y correo electrónico, y como opcional teléfono. |
| 3 | El Responsable de Sistemas completa los datos solicitados. | El sistema muestra la información ingresada en cada campo. |
| 4 | El Responsable de Sistemas confirma el registro del Especialista Externo. | El sistema valida los campos obligatorios, registra al Especialista Externo, establece su estado como “Habilitado” y lo deja disponible para ser asignado a incidencias. |
| 5 | El Responsable de Sistemas selecciona a uno de los especialistas externos registrados. | El sistema muestra su información, su estado de acceso actual y las acciones disponibles según ese estado: “Habilitar acceso” o “Revocar acceso”. |
| 6 | El Responsable de Sistemas selecciona una de las acciones de acceso disponibles. | El sistema registra la selección y muestra el cambio de estado que se realizará antes de confirmarlo. |
| 7 | El Responsable de Sistemas confirma el cambio de acceso. | El sistema actualiza el estado de acceso del especialista. Si queda habilitado, puede ser seleccionado para nuevas asignaciones; si se revoca su acceso, deja de estar disponible para nuevas asignaciones. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Responsable de Sistemas intenta confirmar el registro sin completar uno o más campos obligatorios. | El sistema informa cuáles son los campos que faltan completar e impide registrar al Especialista Externo. |
| E2 | El Responsable de Sistemas ingresa un correo electrónico que ya se encuentra asociado a otro Especialista Externo registrado. | El sistema informa que el correo electrónico ya se encuentra registrado e impide confirmar un nuevo registro con el mismo correo. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El registro del Especialista Externo y la actualización de su estado de acceso deberán guardarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite registrar un Especialista Externo, habilitar su acceso o revocarlo. |
| Importancia | Importante |
| Urgencia | Vital |

---
## CU-08 — Gestionar incidencia como Especialista Externo

| Campo | Detalle |
|-------|---------|
| Identificador | CU-08 |
| Nombre | Gestionar incidencia como Especialista Externo |
| Descripción | Permite al Especialista Externo consultar las incidencias que le fueron asignadas y registrar información relacionada con su tratamiento. |
| Actores | Principal: Especialista Externo / Secundario: Ninguno |
| Precondiciones | El Especialista Externo debe encontrarse habilitado y poseer al menos una incidencia asignada. |
| Postcondiciones | Éxito: la información registrada por el Especialista Externo queda incorporada a la incidencia y disponible para su seguimiento. / Fallo: la información no se incorpora y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Especialista Externo accede a la funcionalidad de incidencias asignadas. | El sistema muestra únicamente las incidencias asignadas al Especialista Externo e informa para cada una su identificador, tipo de incidencia, elemento afectado, prioridad y estado actual. |
| 2 | El Especialista Externo selecciona una de las incidencias disponibles. | El sistema muestra la información necesaria para su tratamiento, incluyendo identificador, tipo de incidencia, elemento afectado, identificador del elemento, descripción del problema, imágenes adjuntas, prioridad y estado actual. Además, presenta la opción “Registrar seguimiento”. |
| 3 | El Especialista Externo selecciona la opción “Registrar seguimiento”. | El sistema presenta un formulario con los tipos de registro disponibles: “Avance”, “Diagnóstico”, “Acción realizada” y “Solución propuesta”, junto con un campo para ingresar la descripción correspondiente. |
| 4 | El Especialista Externo selecciona uno de los tipos de registro disponibles. | El sistema registra la opción seleccionada y habilita el campo “Descripción”. |
| 5 | El Especialista Externo completa la descripción con la información correspondiente al tratamiento de la incidencia. | El sistema muestra la información ingresada y la mantiene disponible para su confirmación. |
| 6 | El Especialista Externo confirma el registro del seguimiento. | El sistema valida la información ingresada, incorpora el registro a la incidencia indicando su tipo y registra al Especialista Externo como responsable de la información incorporada. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Especialista Externo intenta confirmar el seguimiento sin seleccionar un tipo de registro o sin completar la descripción. | El sistema informa cuáles son los datos obligatorios que faltan completar e impide registrar el seguimiento. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La consulta de incidencias asignadas y el registro del seguimiento deberán completarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Especialista Externo necesite consultar una incidencia asignada o registrar información sobre su tratamiento. |
| Importancia | Importante |
| Urgencia | Vital |

---

## CU-09 — Registrar seguimiento y resolución de incidencia

| Campo | Detalle |
|-------|---------|
| Identificador | CU-09 |
| Nombre | Registrar seguimiento y resolución de incidencia |
| Descripción | Permite al Responsable de Sistemas registrar las acciones realizadas durante el tratamiento de una incidencia y registrar su resolución final cuando corresponda. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Debe existir al menos una incidencia registrada que no se encuentre cerrada. |
| Postcondiciones | Éxito: la información ingresada queda registrada en la incidencia. Si se registra la resolución final, la incidencia queda con estado “Cerrado”. / Fallo: la información no se registra y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede al listado de incidencias registradas. | El sistema muestra las incidencias registradas e informa para cada una su identificador, Solicitante, tipo de incidencia, elemento afectado, prioridad, estado y responsable asignado. |
| 2 | El Responsable de Sistemas selecciona el identificador de una incidencia. | El sistema muestra el detalle de la incidencia. Si no se encuentra en estado “Cerrado”, presenta la opción “Registrar información”. |
| 3 | El Responsable de Sistemas selecciona la opción “Registrar información”. | El sistema presenta los tipos de registro disponibles según el estado de la incidencia. Para incidencias en estado “Nuevo”, “En curso” o “Pendiente”, presenta “Acción realizada”. Si la incidencia se encuentra en estado “Resuelto”, presenta además “Resolución final”. |
| 4 | El Responsable de Sistemas selecciona uno de los tipos de registro disponibles. | El sistema registra la opción seleccionada y habilita el campo de descripción correspondiente. |
| 5 | El Responsable de Sistemas completa la descripción de la acción realizada o de la resolución final. | El sistema muestra la información ingresada y la mantiene disponible para su confirmación. |
| 6 | El Responsable de Sistemas confirma el registro de la información. | El sistema valida la información ingresada y la incorpora a la incidencia. Si corresponde a una acción realizada, mantiene el estado actual de la incidencia. Si corresponde a una resolución final, registra la resolución, establece el estado “Cerrado” y notifica al Solicitante sobre el cierre de la incidencia. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Responsable de Sistemas intenta confirmar el registro sin completar la descripción. | El sistema informa que la descripción es obligatoria e impide registrar la información. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | La consulta de incidencias y el registro de la información deberán completarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite registrar una acción realizada o, cuando la incidencia esté en estado “Resuelto”, registrar su resolución final. |
| Importancia | Importante |
| Urgencia | Vital |

---

## CU-10 — Consultar historial de incidencias

| Campo | Detalle |
|-------|---------|
| Identificador | CU-10 |
| Nombre | Consultar historial de incidencias |
| Descripción | Permite al Responsable de Sistemas consultar el historial de una incidencia y visualizar la información registrada durante su gestión. |
| Actores | Principal: Responsable de Sistemas / Secundario: Ninguno |
| Precondiciones | Debe existir al menos una incidencia registrada. |
| Postcondiciones | Éxito: el historial de la incidencia queda disponible para su consulta sin modificar la información registrada. / Fallo: el historial no se muestra y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Responsable de Sistemas accede a la funcionalidad de consulta de historial de incidencias. | El sistema muestra las incidencias registradas e informa para cada una su identificador, Solicitante, tipo de incidencia, elemento afectado, estado y responsable asignado. |
| 2 | El Responsable de Sistemas selecciona una de las incidencias disponibles. | El sistema muestra el detalle de la incidencia y presenta la opción “Consultar historial”. |
| 3 | El Responsable de Sistemas selecciona la opción “Consultar historial”. | El sistema muestra, en orden cronológico, los registros asociados a la gestión de la incidencia, indicando para cada uno fecha y hora, tipo de registro, actor responsable y detalle de la información registrada. |
| 4 | El Responsable de Sistemas selecciona uno de los registros del historial. | El sistema muestra el detalle completo del registro seleccionado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|

| Campo | Detalle |
|-------|---------|
| Rendimiento | La apertura del listado y la consulta del historial y sus registros deberán completarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Responsable de Sistemas necesite consultar los registros de gestión de una incidencia. |
| Importancia | Importante |
| Urgencia | Vital |

---
## CU-11 — Actualizar estado de incidencia asignada

| Campo | Detalle |
|-------|---------|
| Identificador | CU-11 |
| Nombre | Actualizar estado de incidencia asignada |
| Descripción | Permite al Especialista Externo actualizar el estado de una incidencia que tiene asignada durante su gestión. |
| Actores | Principal: Especialista Externo / Secundario: Ninguno |
| Precondiciones | El Especialista Externo debe tener al menos una incidencia asignada. |
| Postcondiciones | Éxito: el nuevo estado de la incidencia queda registrado y visible para el usuario. / Fallo: el estado no se modifica y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Especialista Externo accede al detalle de una incidencia que tiene asignada. | El sistema muestra el detalle de la incidencia y presenta la opción “Gestionar incidencia”. |
| 2 | El Especialista Externo selecciona la opción “Gestionar incidencia”. | El sistema muestra la información de gestión de la incidencia y permite modificar únicamente su estado. La prioridad y el responsable asignado se muestran sin posibilidad de modificación. |
| 3 | El Especialista Externo despliega los estados disponibles. | El sistema muestra los estados habilitados para la incidencia: “En curso”, “Pendiente” y “Resuelto”. |
| 4 | El Especialista Externo selecciona un nuevo estado. | El sistema muestra el estado seleccionado y mantiene disponibles las opciones para guardar o cancelar los cambios. |
| 5 | El Especialista Externo selecciona “Guardar cambios”. | El sistema actualiza el estado de la incidencia y registra el cambio realizado. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|

| Campo | Detalle |
|-------|---------|
| Rendimiento | La actualización del estado deberá guardarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Especialista Externo necesite actualizar el estado de una incidencia que tiene asignada durante su gestión. |
| Importancia | Importante |
| Urgencia | Vital |

---
## CU-12 — Registrar acción realizada sobre una incidencia

| Campo | Detalle |
|-------|---------|
| Identificador | CU-12 |
| Nombre | Registrar acción realizada sobre una incidencia |
| Descripción | Permite al Especialista Externo registrar las acciones realizadas durante la gestión de una incidencia que tiene asignada. |
| Actores | Principal: Especialista Externo / Secundario: Ninguno |
| Precondiciones | El Especialista Externo debe tener una incidencia asignada. |
| Postcondiciones | Éxito: la acción realizada queda registrada y asociada a la incidencia. / Fallo: la acción no se registra y el sistema informa el motivo. |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | El Especialista Externo accede al detalle de una incidencia que tiene asignada. | El sistema muestra el detalle de la incidencia y presenta la opción “Registrar información”. |
| 2 | El Especialista Externo selecciona la opción “Registrar información”. | El sistema presenta los tipos de registro disponibles para el Especialista Externo. |
| 3 | El Especialista Externo selecciona el tipo de registro “Acción realizada”. | El sistema habilita el ingreso de la descripción de la acción realizada. |
| 4 | El Especialista Externo ingresa la descripción de la acción realizada. | El sistema muestra la información ingresada y habilita la opción “Confirmar”. |
| 5 | El Especialista Externo selecciona “Confirmar”. | El sistema registra la acción realizada, asociándola a la incidencia y al Especialista Externo que realizó el registro, e informa que la acción fue registrada correctamente. |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | El Especialista Externo intenta confirmar el registro sin completar la descripción. | El sistema informa que la descripción es obligatoria e impide registrar la acción. |

| Campo | Detalle |
|-------|---------|
| Rendimiento | El registro de la acción deberá guardarse en un máximo de 3 segundos en al menos el 95 % de las operaciones, con hasta 50 usuarios conectados simultáneamente. |
| Frecuencia | Cada vez que el Especialista Externo necesite registrar una acción realizada durante la gestión de una incidencia asignada. |
| Importancia | Importante |
| Urgencia | Vital |