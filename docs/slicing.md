# Ejercicio: partir una épica en slices verticales

## La épica

> Ciclo completo de un ticket, desde apertura hasta cierre con derivación externa.




---

## Parte A — Historias verticales

1. Reportar una incidencia.
2. Lista de incidencias reportadas por parte del solicitante.
3. Asignación de un ticket a un responsable.
4. Derivación del ticket a otro responsable.
5. Lista de incidencias asignadas a uno mismo.
6. Cambiar estado de ticket a "en curso".
7. Cambiar estado de ticket a "cerrada".

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
6. Se deberá adjuntar archivos solo en formato PNG, PGJ y JPEG.

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

---

## Parte B — Los caminos que no salen bien

_Elijan UNA de las historias de la Parte A. Las últimas tres preguntas son las importantes:
para cada una, indiquen qué debería hacer el sistema y quién tendría que decidirlo._

**Historia elegida:** ## HU-04 — [Registrar una incidencia desde el formulario web]

| Pregunta | Qué hace el sistema | Quién decide (analista / negocio / técnica) |
|----------|---------------------|--------------------------------------------|
| ¿Qué pasa si el Solicitante intenta registrar la incidencia sin completar uno o más campos obligatorios? | Informa cuáles son los campos obligatorios que falta completar, los destaca en la pantalla e impide el registro de la incidencia manteniendo la información tipeada. | Analista |
| ¿Qué pasa si el Solicitante ingresa un identificador que no corresponde a un elemento registrado? | Notifica que el identificador ingresado no existe en el catálogo, impide continuar con el registro y solicita corregir el código o número de serie para proceder. | Negocio |
| ¿Qué pasa si el Solicitante ingresa el identificador de un elemento que ya posee una incidencia abierta? | Informa que el elemento ya tiene una incidencia abierta, muestra el identificador y estado de dicha incidencia, e impide registrar un nuevo ticket mientras la anterior siga en curso. | Negocio |
| ¿Qué pasa si el Solicitante intenta adjuntar una imagen que no cumple las condiciones establecidas de formato o tamaño? | Rechaza el archivo subido, muestra un mensaje indicando el motivo del rechazo y conserva intactos todos los demás datos ingresados. | Técnica / Analista |
| ¿Qué pasa si ocurre una desconexión de red o error de servidor al momento de presionar "Confirmar"? | Detecta el fallo de comunicación, no genera el ticket ni asigna el identificador único (aplica rollback) y notifica al usuario el error de red manteniendo la información en el formulario para reintentar. | Técnica |

---

## Parte C — Defensa

_Se hace oral, en el plenario. No se documenta en este archivo_