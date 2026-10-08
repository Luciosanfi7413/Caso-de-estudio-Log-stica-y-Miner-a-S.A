# Historias de usuario

_Presentar al menos una historia de usuario representativa por módulo._
_Cada historia debe incluir formato clásico, criterios de aceptación y validación INVEST._

---

## HU-01 — [Iniciar sesión según el perfil del usuario]

| Campo | Detalle |
|-------|---------|
| Historia | Como usuario autorizado, quiero iniciar sesión con mis credenciales individuales, para acceder a las funciones habilitadas para mi perfil. |
| Módulo |Módulo 1 — Acceso y gestión de usuarios |
| Requisitos relacionados |RF-01 |

### Criterios de aceptación

1. El sistema deberá permitir el ingreso con credenciales individuales válidas.
2. El sistema deberá habilitar únicamente las funciones correspondientes al perfil del usuario autenticado.
3. Si las credenciales no son válidas, el sistema deberá impedir el acceso e informar que no pudo iniciar sesión.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |El acceso puede desarrollarse y probarse como una capacidad delimitada. |
| Negociable |Si |El requisito define el resultado, no el diseño de la pantalla. |
| Valiosa |Si |Permite acceder al sistema de forma individual y según el perfil. |
| Estimable |Si |El alcance se limita a autenticación y acceso por perfil. |
| Pequeña |Si |No incluye la administración de especialistas ni otras funciones. |
| Verificable |Si |Se prueban credenciales válidas, inválidas y permisos por perfil. |

---

## HU-02 — [Registrar y habilitar un especialista externo]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero registrar y habilitar a un Especialista Externo, para que pueda ser asignado a la gestión de incidencias. |
| Módulo |Módulo 1 — Acceso y gestión de usuarios |
| Requisitos relacionados |RF-02|

### Criterios de aceptación

1. El sistema deberá permitir registrar los datos requeridos del Especialista Externo.
2. El sistema deberá validar que el correo electrónico no esté asociado a otro especialista registrado.
3. Al confirmar el registro, el sistema deberá dejar al especialista habilitado y disponible para nuevas asignaciones.
4. El sistema deberá permitir que haya varios Especialistas Externos habilitados simultáneamente.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |Puede implementarse aparte del flujo de atención de una incidencia. |
| Negociable |Si | El resultado está definido y los detalles de implementación pueden acordarse.|
| Valiosa |Si |Incorpora especialistas que pueden atender incidencias. |
| Estimable |Si |El alcance se limita al registro y habilitación. |
| Pequeña |Si | No incluye la revocación de acceso, que se trata en otra historia.|
| Verificable |Si | Se comprueban el registro, la validación del correo y la disponibilidad para asignación.|

---


## HU-03 — Revocar el acceso de un Especialista Externo

| Campo | Detalle |
|-------|---------|
| Identificador | HU-03 |
| Historia | Como Responsable de Sistemas, quiero revocar el acceso de un Especialista Externo, para impedir que siga participando en nuevas asignaciones cuando ya no esté autorizado. |
| Módulo | Módulo 1 — Acceso y gestión de usuarios |
| Requisitos relacionados | RF-03 |

### Criterios de aceptación

1. El sistema deberá permitir al Responsable de Sistemas seleccionar un Especialista Externo registrado y revocar su acceso.
2. Antes de confirmar, el sistema deberá mostrar el especialista seleccionado y las incidencias abiertas que tiene asignadas, si las hubiera.
3. Al confirmar, el sistema deberá revocar el acceso del especialista e impedir que quede disponible para nuevas asignaciones.
4. Si el especialista tiene incidencias abiertas asignadas, el sistema deberá identificarlas como pendientes de reasignación, sin cambiar automáticamente el responsable.
5. El sistema deberá mostrar el estado de acceso actualizado del especialista.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | La revocación es una acción diferenciada del registro y la habilitación del especialista. |
| Negociable | Sí | El resultado de la revocación está definido; los detalles de presentación pueden acordarse. |
| Valiosa | Sí | Permite retirar el acceso cuando el especialista deja de estar autorizado. |
| Estimable | Sí | Están definidos el cambio de acceso y el tratamiento de sus incidencias abiertas. |
| Pequeña | Sí | Se limita a revocar el acceso e identificar las incidencias que requieren reasignación; la reasignación se realiza en otra historia. |
| Verificable | Sí | Se pueden comprobar la revocación, la indisponibilidad para nuevas asignaciones y la identificación de incidencias pendientes de reasignación. |

---

## HU-04 — Registrar una incidencia desde el formulario web

| Campo | Detalle |
|-------|---------|
| Identificador | HU-04 |
| Historia | Como Solicitante, quiero registrar una falla o solicitud técnica con los datos del elemento afectado, para que el área de Sistemas pueda gestionarla. |
| Módulo | Módulo 2 — Registro de incidencias |
| Requisitos relacionados | RF-04, RF-06 |

### Criterios de aceptación

1. El sistema deberá permitir informar el tipo de incidencia, el elemento afectado, su identificador y la descripción del problema.
2. El sistema deberá permitir adjuntar una o más imágenes relacionadas con la incidencia.
3. El sistema deberá validar que los campos obligatorios estén completos, que el elemento afectado esté registrado y que no tenga otra incidencia cuyo estado sea distinto de “Cerrado”. Si alguna validación falla, deberá impedir el registro e informar el motivo.
4. Al confirmar un registro válido, el sistema deberá asociar la incidencia al Solicitante, asignarle un identificador único y establecer su estado inicial como “Nuevo”.
5. Si faltan datos obligatorios o una imagen no cumple las condiciones permitidas, el sistema deberá informar el error y conservar los demás datos ingresados.
6. El sistema deberá aceptar imágenes en formato PNG o JPEG que no superen los 15 MB por archivo.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | El registro se puede desarrollar y probar como un flujo funcional propio. |
| Negociable | Sí | El objetivo y las reglas principales están definidos; los detalles de interacción pueden acordarse. |
| Valiosa | Sí | Permite que el Solicitante registre problemas para que Sistemas los gestione. |
| Estimable | Sí | Están definidos los datos, las validaciones, los formatos y el límite de tamaño de las imágenes. |
| Pequeña | Parcial | El alcance reúne el formulario, varias validaciones y la carga de imágenes; el equipo deberá considerar esa complejidad al estimarlo. |
| Verificable | Sí | Se pueden probar los campos, las validaciones, el registro, los formatos admitidos y el límite de 15 MB por imagen. |

---

## HU-05 — Registrar una incidencia desde un dispositivo móvil

| Campo | Detalle |
|-------|---------|
| Identificador | HU-05 |
| Historia | Como Solicitante que se encuentra realizando un recorrido, quiero registrar una incidencia desde mi dispositivo móvil, para informar el problema sin tener que volver a las instalaciones. |
| Módulo | Módulo 2 — Registro de incidencias |
| Requisitos relacionados | RF-05, RF-06, RNF-07 |

### Criterios de aceptación

1. El sistema deberá permitir al Solicitante acceder al formulario de registro desde un dispositivo móvil.
2. El formulario deberá permitir informar el tipo de incidencia, el elemento afectado, su identificador y la descripción del problema.
3. El sistema deberá permitir adjuntar, opcionalmente, una o más imágenes en formato PNG o JPEG, de hasta 15 MB por archivo.
4. En una pantalla de 360 px de ancho o superior, el Solicitante deberá poder completar el registro y utilizar sus acciones sin desplazamiento horizontal.
5. Al confirmar un registro válido, el sistema deberá asociar la incidencia al Solicitante, asignarle un identificador único y establecer su estado inicial como “Nuevo”.
6. Si faltan datos obligatorios o una imagen no cumple las condiciones permitidas, el sistema deberá informar el error y conservar los demás datos ingresados.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | El flujo móvil permite completar y registrar una incidencia sin depender de la pantalla web. |
| Negociable | Sí | El registro desde el dispositivo móvil está definido; los detalles de interacción pueden acordarse. |
| Valiosa | Sí | Permite informar problemas durante los recorridos sin volver a las instalaciones. |
| Estimable | Sí | Se especifican los campos, las condiciones de las imágenes y el ancho mínimo de pantalla. |
| Pequeña | Parcial | Combina el registro con la adaptación móvil y la carga de imágenes; el equipo deberá considerar ese alcance al estimarlo. |
| Verificable | Sí | Se pueden probar el registro, las imágenes permitidas y el uso del formulario en una pantalla de 360 px sin desplazamiento horizontal. |

---

## HU-06 — [Consultar las incidencias propias]

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

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |Es una consulta separada de la gestión interna. |
| Negociable |Si | El alcance de la consulta está definido y la presentación puede acordarse.|
| Valiosa |Si |Permite conocer el estado y responsable de las solicitudes propias. |
| Estimable |Si |Incluye listado, detalle y estado sin modificar datos.|
| Pequeña |Si | Se limita a la consulta de incidencias del Solicitante.|
| Verificable |Si | Se prueba el filtrado por Solicitante, el detalle y el caso sin resultados.|

---

## HU-07 — [Consultar incidencias para su gestión]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero consultar las incidencias registradas y sus datos, para contar con la información necesaria para gestionarlas. |
| Módulo |Módulo 3 — Consulta y seguimiento de incidencias |
| Requisitos relacionados |RF-08|

### Criterios de aceptación

1. El sistema deberá mostrar al Responsable de Sistemas las incidencias registradas con identificador, tipo, elemento afectado, estado, prioridad y responsable asignado.
2. Al seleccionar una incidencia, el sistema deberá mostrar su detalle, incluyendo Solicitante, descripción e información complementaria disponible.
3. Si no existen incidencias registradas, el sistema deberá informar que no hay incidencias para consultar.
4. La consulta no deberá modificar los datos de la incidencia.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |La consulta puede desarrollarse antes o aparte de las acciones de gestión |
| Negociable |Si |La información requerida está definida; la presentación puede acordarse.|
| Valiosa |Si Proporciona contexto para gestionar las incidencias |
| Estimable |Si |El alcance se limita al listado y detalle de incidencias.|
| Pequeña |Si | No incluye modificar estado, prioridad ni responsable.|
| Verificable |Si | Se comprueban los datos del listado, el detalle y la consulta sin resultados.|

---

## HU-08 — [Consultar incidencias asignadas al especialista externo]

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

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |La consulta del especialista es un flujo propio. |
| Negociable |Si | Los datos necesarios están definidos y su presentación puede acordarse.|
| Valiosa |Si |Permite al especialista conocer las tareas que tiene asignadas. |
| Estimable |Si |Incluye listado, detalle y restricción por asignación. |
| Pequeña |Si | No incluye registrar acciones ni actualizar estados.|
| Verificable |Si | Se comprueba el filtrado por responsable y la restricción de acceso.|

---

## HU-09 — [Consultar el historial de una incidencia]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero consultar el historial de una incidencia, para revisar las acciones y cambios realizados durante su gestión. |
| Módulo |Módulo 3 — Consulta y seguimiento de incidencias|
| Requisitos relacionados |RF-10, RNF-04|

### Criterios de aceptación

1. El sistema deberá mostrar los registros del historial en orden cronológico.
2. Cada registro deberá informar fecha, hora, tipo, actor responsable y detalle de la información registrada.
3. Al seleccionar un registro, el sistema deberá mostrar su detalle completo.
4. El sistema deberá conservar el historial completo durante dos años desde el cierre de la incidencia.
5. La consulta del historial no deberá modificar los registros existentes.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |Es una capacidad de consulta diferenciada del registro de intervenciones. |
| Negociable |Si | El contenido mínimo está definido; la presentación puede acordarse.|
| Valiosa |Si |Aporta antecedentes para analizar incidencias similares.|
| Estimable |Si |Se delimitan la consulta, el orden y el detalle de registros. |
| Pequeña | Sí | La historia se limita a consultar y mostrar el historial de una incidencia. La conservación durante dos años está definida en RNF-04 y se verifica mediante el criterio de aceptación 4. |
| Verificable |Si | Se comprueba el orden, los datos visibles, el detalle y la retención indicada.|

---

## HU-10 — Asignar prioridad a una incidencia

| Campo | Detalle |
|-------|---------|
| Identificador | HU-10 |
| Historia | Como Responsable de Sistemas, quiero asignar o actualizar la prioridad de una incidencia registrada, para ordenar su atención. |
| Módulo | Módulo 4 — Gestión y asignación de incidencias |
| Requisitos relacionados | RF-11 |

### Criterios de aceptación

1. El sistema deberá permitir al Responsable de Sistemas seleccionar una incidencia registrada.
2. El sistema deberá mostrar la prioridad actual de la incidencia, si posee una, y las opciones disponibles: Baja, Media, Alta y Vital.
3. El sistema deberá permitir seleccionar una prioridad y mostrarla antes de confirmar la operación.
4. Al confirmar, el sistema deberá guardar la prioridad seleccionada y mostrar una confirmación de la operación realizada.
5. Si no se selecciona una prioridad, el sistema deberá mantener deshabilitado el botón “Guardar”, indicar que debe seleccionarse una opción y no modificar la incidencia.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | La asignación de prioridad es una acción diferenciada de la actualización del estado y de la asignación del responsable. |
| Negociable | Sí | Las prioridades disponibles y el resultado están definidos; los detalles de interacción pueden acordarse. |
| Valiosa | Sí | Permite al Responsable de Sistemas ordenar la atención de las incidencias. |
| Estimable | Sí | Las opciones de prioridad y el flujo de selección, confirmación y guardado están definidos; no se requiere una matriz de urgencia e impacto. |
| Pequeña | Sí | Se limita a seleccionar y guardar la prioridad de una incidencia. |
| Verificable | Sí | Se puede comprobar la selección de cada prioridad, su guardado y la validación si no se selecciona una opción. |

---

## HU-11 — [Actualizar el estado de una incidencia como responsable de sistemas]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero actualizar el estado de una incidencia, para reflejar su evolución e informar al Solicitante. |
| Módulo |Módulo 4 — Gestión y asignación de incidencias|
| Requisitos relacionados |RF-12|

### Criterios de aceptación

1. El sistema deberá permitir al Responsable de Sistemas seleccionar un estado habilitado para la incidencia.
2. Antes de guardar, el sistema deberá mostrar el estado actual y el nuevo estado seleccionado.
3. Al confirmar, el sistema deberá actualizar la incidencia y registrar el cambio en su historial.
4. El sistema deberá informar al Solicitante sobre el nuevo estado.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |El cambio de estado es distinto de priorizar o asignar una incidencia. |
| Negociable |Si | La necesidad está definida; el mecanismo de notificación puede acordarse.|
| Valiosa |Si |Mantiene actualizado el seguimiento e informa al Solicitante. |
| Estimable |Si |Incluye selección, registro del cambio y notificación.|
| Pequeña |Si |No incluye asignación ni registro de una resolución final.|
| Verificable |Si | Se comprueban el nuevo estado, el historial y la notificación.|

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

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | La asignación o reasignación es una operación diferenciada de la actualización del estado y de la prioridad. |
| Negociable | Sí | El resultado está definido; la presentación de las opciones puede acordarse. |
| Valiosa | Sí | Permite identificar quién estará a cargo de atender cada incidencia. |
| Estimable | Sí | Están definidos los tipos de responsable, la restricción para especialistas externos y las acciones posteriores a la confirmación. |
| Pequeña | Sí | Se limita a una operación: seleccionar un responsable, asociarlo a la incidencia, registrar el cambio e informar al Solicitante. |
| Verificable | Sí | Se pueden comprobar la asignación, la reasignación, el filtro de especialistas habilitados y la notificación. |

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

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | El Especialista Externo puede informar que no podrá atender la incidencia sin que la reasignación se realice como parte de esta acción. |
| Negociable | Sí | El resultado del aviso está definido; los detalles de cómo se presenta pueden acordarse. |
| Valiosa | Sí | Permite que el Responsable de Sistemas se entere de que debe reasignar la incidencia. |
| Estimable | Sí | Están definidos quién informa, sobre qué incidencia y qué ocurre después del aviso. |
| Pequeña | Sí | Se limita a registrar el aviso y comunicarlo al Responsable de Sistemas. |
| Verificable | Sí | Se comprueba que el aviso quede asociado a la incidencia y al especialista, que se informe a Sistemas y que no haya reasignación automática. |
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

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | Es una acción del Especialista Externo diferenciada de la actualización realizada por el Responsable de Sistemas. |
| Negociable | Sí | El objetivo y los estados disponibles están definidos; los detalles de interacción pueden acordarse. |
| Valiosa | Sí | Permite reflejar el avance de la atención externa e informar al Solicitante. |
| Estimable | Sí | Se limita a incidencias asignadas, estados habilitados, registro del cambio y notificación. |
| Pequeña | Sí | No incluye cambiar el responsable ni la prioridad de la incidencia. |
| Verificable | Sí | Se pueden comprobar los permisos, los estados disponibles, el registro en el historial y la notificación al Solicitante. |

---

## HU-15 — [Registrar acciones realizadas por el responsable de sistemas]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero registrar las acciones realizadas durante la atención, para conservarlas en el historial de la incidencia.|
| Módulo |Módulo 5 — Resolución e historial de intervenciones |
| Requisitos relacionados |RF-15|

### Criterios de aceptación

1. El sistema deberá permitir al Responsable de Sistemas registrar una descripción de la acción realizada en una incidencia no cerrada.
2. El sistema deberá impedir la confirmación si la descripción está vacía.
3. Al confirmar, el sistema deberá asociar el registro a la incidencia y al Responsable de Sistemas que lo realizó.
4. El sistema deberá incorporar la acción al historial sin cambiar el estado de la incidencia.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |El registro de acciones puede desarrollarse aparte del cierre de la incidencia. |
| Negociable |Si | El objetivo y los datos mínimos están definidos.|
| Valiosa |Si |Conserva las intervenciones realizadas para el seguimiento. |
| Estimable |Si |Incluye descripción, validación y asociación al historial.|
| Pequeña |Si | Se limita a registrar una acción realizada.|
| Verificable |Si | Se comprueba la validación, la asociación y que el estado no cambie.|

---

## HU-16 — Registrar intervenciones del Especialista Externo

| Campo | Detalle |
|-------|---------|
| Identificador | HU-16 |
| Historia | Como Especialista Externo, quiero registrar avances, diagnósticos, acciones realizadas o soluciones propuestas en las incidencias que tengo asignadas, para documentar su tratamiento. |
| Módulo | Módulo 5 — Resolución e historial de intervenciones |
| Requisitos relacionados | RF-16 |

### Criterios de aceptación

1. El sistema deberá permitir al Especialista Externo registrar información únicamente en incidencias que tenga asignadas.
2. El sistema deberá permitir clasificar el registro como “Avance”, “Diagnóstico”, “Acción realizada” o “Solución propuesta”.
3. El sistema deberá exigir una descripción antes de confirmar el registro.
4. Al confirmar, el sistema deberá asociar el tipo de registro, la descripción, la incidencia y el Especialista Externo al historial, sin modificar el estado de la incidencia.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | El registro de intervenciones externas es una acción diferenciada de las intervenciones registradas por Sistemas. |
| Negociable | Sí | Los tipos de registro están definidos; los detalles de presentación pueden acordarse. |
| Valiosa | Sí | Permite dar seguimiento al trabajo realizado por especialistas externos. |
| Estimable | Sí | Están definidos los tipos, la descripción obligatoria y la asociación al historial. |
| Pequeña | Sí | Aunque hay varios tipos de registro, todos siguen el mismo flujo: seleccionar un tipo, ingresar una descripción y confirmarla. |
| Verificable | Sí | Se pueden probar los tipos disponibles, la obligatoriedad de la descripción, la asociación del registro a la incidencia y al especialista, y que el estado de la incidencia no cambie. |

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

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente | Sí | El registro de la resolución final y el cierre son una acción diferenciada del registro de acciones intermedias. |
| Negociable | Sí | El resultado está definido; los detalles de presentación y confirmación pueden acordarse. |
| Valiosa | Sí | Finaliza formalmente la gestión y conserva la resolución en el historial. |
| Estimable | Sí | Están definidos el estado requerido, la descripción, el cierre y la notificación al Solicitante. |
| Pequeña | Sí | Se limita a registrar una resolución final, cerrar la incidencia e informar al Solicitante. |
| Verificable | Sí | Se pueden probar el estado “Resuelto”, la descripción obligatoria, el cierre, la notificación y el caso sin acciones previas. |