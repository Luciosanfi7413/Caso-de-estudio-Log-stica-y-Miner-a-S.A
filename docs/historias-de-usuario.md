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


## HU-03 — [Revocar el acceso de un especialista externo]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero revocar el acceso de un Especialista Externo, para impedir que siga participando en nuevas asignaciones cuando ya no esté autorizado. |
| Módulo |Módulo 1 — Acceso y gestión de usuarios |
| Requisitos relacionados |RF-03|

### Criterios de aceptación

1. El sistema deberá permitir al Responsable de Sistemas revocar el acceso de un especialista registrado.
2. Antes de aplicar el cambio, el sistema deberá mostrar qué especialista será afectado y el cambio de estado previsto.
3. Una vez revocado el acceso, el especialista no deberá estar disponible para nuevas asignaciones.
4. El sistema deberá mostrar el estado de acceso actualizado en la gestión de especialistas.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |La revocación es una acción diferenciada del registro del especialista. |
| Negociable |Si | El resultado está definido; la interacción puede ajustarse.|
| Valiosa |Si |Permite retirar el acceso cuando el especialista deja de estar autorizado. |
| Estimable |Si |La acción y su efecto sobre nuevas asignaciones están delimitados. |
| Pequeña |Si | No contempla la eliminación del especialista ni la gestión de incidencias.|
| Verificable |Si | Se comprueba el cambio de estado y que ya no figure disponible para nuevas asignaciones.|

---

## HU-04 — [Registrar una incidencia desde el formulario web]

| Campo | Detalle |
|-------|---------|
| Historia | Como Solicitante, quiero registrar una falla o solicitud técnica con los datos del elemento afectado, para que el área de Sistemas pueda gestionarla. |
| Módulo |Módulo 2 — Registro de incidencias |
| Requisitos relacionados |RF-04, RF-06|

### Criterios de aceptación

1. El sistema deberá permitir informar el tipo de incidencia, el elemento afectado, su identificador y la descripción del problema.
2. El sistema deberá permitir adjuntar imágenes o documentos como información complementaria.
3. El sistema deberá validar los campos obligatorios y que el elemento afectado esté registrado y no tenga otra incidencia abierta.
4. Al confirmar un registro válido, el sistema deberá asociar la incidencia al Solicitante, asignarle un identificador único y establecer su estado inicial como Nuevo.
5. Si un dato obligatorio o un archivo no cumple las condiciones definidas, el sistema deberá explicar el error y conservar los demás datos ingresados.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |El registro se puede entregar como flujo funcional propio.|
| Negociable |Si | Los campos y reglas están identificados; el diseño puede acordarse.|
| Valiosa |Si |Permite formalizar y dar seguimiento a los pedidos de soporte.|
| Estimable |Si |El formulario y sus validaciones tienen un alcance delimitado.
Pequeña	Parcial	El flujo incluye varias validaciones y adjuntos; revisar si el equipo lo estima grande.
Verificable	Sí	Se prueban el registro, las validaciones, el identificador y el estado inicial.|
| Pequeña |Si | No incluye la revocación de acceso, que se trata en otra historia.|
| Verificable |Si | Se prueban el registro, las validaciones, el identificador y el estado inicial.|

---

## HU-05 — [Registrar una incidencia desde un dispositivo móvil]

| Campo | Detalle |
|-------|---------|
| Historia |Como Chofer, quiero registrar una incidencia desde mi dispositivo móvil durante un recorrido, para informar un problema sin tener que volver a las instalaciones.|
| Módulo |Módulo 2 — Registro de incidencias|
| Requisitos relacionados |RF-05, RF-06, RNF-07|

### Criterios de aceptación

1. El sistema deberá permitir al Chofer indicar el elemento afectado, sus datos identificatorios y una descripción de la situación.
2. El sistema deberá permitir adjuntar una fotografía u otro documento permitido como información complementaria.
3. En una pantalla de 360 px de ancho o superior, el Chofer deberá poder completar el registro y acceder a las acciones necesarias sin desplazamiento horizontal.
4. Al confirmar un registro válido, el sistema deberá conservar la incidencia y asociarla al Chofer que la registró.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |Es un flujo móvil separado del registro web del Solicitante.|
| Negociable |Si |La necesidad está definida; los detalles de interacción móvil pueden acordarse.|
| Valiosa |Si |Permite reportar problemas durante los recorridos.|
| Estimable |Si |Se limita al registro móvil y su adaptación de interfaz.|
| Pequeña |Si |La adaptación móvil y los adjuntos pueden ampliar el alcance.|
| Verificable |Si |Se prueba el registro y la visualización en el ancho indicado.|

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
| Pequeña |Si | La conservación por dos años puede involucrar decisiones técnicas adicionales.|
| Verificable |Si | Se comprueba el orden, los datos visibles, el detalle y la retención indicada.|

---

## HU-10 — [Asignar prioridad a una incidencia]

| Campo | Detalle |
|-------|---------|
| Historia | Como Responsable de Sistemas, quiero asignar una prioridad a una incidencia según su urgencia e impacto, para ordenar su atención. |
| Módulo 4 — Gestión y asignación de incidencias |
| Requisitos relacionados |RF-11|

### Criterios de aceptación

1. El sistema deberá permitir indicar los valores de urgencia e impacto definidos para la incidencia.
2. El sistema deberá permitir asignar una prioridad de acuerdo con los criterios definidos para combinar urgencia e impacto.
3. Antes de guardar, el sistema deberá mostrar los valores seleccionados para su revisión.
4. El sistema deberá guardar la prioridad asociada a la incidencia y mostrar el resultado actualizado.

### Validación INVEST

| Criterio | ¿Se cumple? | Observación |
|----------|-------------|-------------|
| Independiente |Si |Puede implementarse aparte de la asignación de responsable y del cambio de estado. |
| Negociable |Si | El flujo está definido; los detalles de interfaz pueden acordarse.|
| Valiosa |Si |Ayuda a ordenar la atención de las incidencias. |
| Estimable |Si |Falta definir la matriz o regla que relaciona urgencia, impacto y prioridad. |
| Pequeña |Si |Se limita a registrar los valores y la prioridad.|
| Verificable |Si | Se prueba que los valores se guardan según la regla definida.|

---

## HU-11 — [Registrar y habilitar un especialista externo]

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

## HU-12 — [Registrar y habilitar un especialista externo]

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

## HU-13 — [Registrar y habilitar un especialista externo]

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

## HU-14 — [Registrar y habilitar un especialista externo]

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

## HU-15 — [Registrar y habilitar un especialista externo]

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

## HU-16 — [Registrar y habilitar un especialista externo]

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

## HU-17 — [Registrar y habilitar un especialista externo]

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