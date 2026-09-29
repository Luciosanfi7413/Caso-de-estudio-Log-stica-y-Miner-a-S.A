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

## CU-02 — [Nombre]

| Campo | Detalle |
|-------|---------|
| Identificador | CU-02 |
| Nombre | |
| Descripción | |
| Actores | Principal: / Secundario: |
| Precondiciones | |
| Postcondiciones | Éxito: / Fallo: |

### Secuencia normal

| # | Acción (actor) | Reacción (sistema) |
|---|----------------|--------------------|
| 1 | | |
| 2 | | |

### Excepciones

| # | Situación | Respuesta del sistema |
|---|-----------|-----------------------|
| E1 | | |

| Campo | Detalle |
|-------|---------|
| Rendimiento | |
| Frecuencia | |
| Importancia | |
| Urgencia | |
