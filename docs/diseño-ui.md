# Diseño UI

_Presentar al menos un wireframe por pantalla o módulo relevante._
_Los wireframes en imagen o PDF van en `diagramas/wireframes/`; acá se documenta la justificación de cada uno._

---

## Pantalla / Módulo 1 — CU-01 — Registro de incidencia

**Wireframe:** [`diagramas/wireframes/CU001-registro-de-incidencia.pdf`](diagramas/wireframes/CU001-registro-de-incidencia.pdf)

**Patrones de diseño utilizados:** Formulario con campos dependientes, validación junto al campo y pantalla de confirmación.

**Justificación:** El formulario guía al Solicitante durante el registro. El campo de identificación se adapta al elemento afectado que selecciona, lo que ayuda a ingresar el dato correspondiente. Las validaciones muestran los errores durante la carga y la confirmación informa que la incidencia fue registrada.

**Formulario (si aplica):**
- Cantidad de campos: 5; cuatro obligatorios y uno opcional.
- Flujo (todo en una pantalla / por pasos): En una pantalla, con campos que cambian según la selección. Al finalizar, se muestra la confirmación.
- Validaciones relevantes: campos obligatorios, identificador asociado a un elemento registrado, ausencia de otra incidencia abierta para ese elemento y formato y tamaño permitidos para las imágenes.
---
## Pantalla / Módulo 2 — CU-02 — Detalle de incidencia

**Wireframe:** [`diagramas/wireframes/CU002-consulta-de-incidencias.pdf`](diagramas/wireframes/CU002-consulta-de-incidencias.pdf)

**Patrones de diseño utilizados:** Vista de detalle organizada por bloques y visualización del archivo adjunto.

**Justificación:** La vista reúne los datos principales, el estado, el responsable y la descripción completa de la incidencia. También permite consultar la imagen adjunta desde el mismo contexto, sin modificar la información.

**Formulario (si aplica):** No aplica. Es una pantalla de consulta.

---

## Consideraciones de accesibilidad

- El estado de cada incidencia se presenta con texto —por ejemplo, “Nuevo”, “En curso” o “Resuelto”— para que la información no dependa únicamente del color. Los encabezados de la tabla identifican qué dato contiene cada columna.

---
## Pantalla / Módulo 1 — CU-03 — Opciones de soporte

**Wireframe:** [`diagramas/wireframes/CU003-consultar-incidencias-registradas.pdf`](diagramas/wireframes/CU003-consultar-incidencias-registradas.pdf) (pág. 1)

**Patrones de diseño utilizados:** Tarjetas de navegación con accesos directos.

**Justificación:** Las opciones separan las funciones disponibles en Soporte. La tarjeta “Gestionar incidencias” permite que el Responsable de Sistemas acceda al listado de incidencias que debe consultar y gestionar.

**Formulario (si aplica):** No aplica.

---

## Pantalla / Módulo 2 — CU-03 — Listado de incidencias registradas

**Wireframe:** [`diagramas/wireframes/CU003-consultar-incidencias-registradas.pdf`](diagramas/wireframes/CU003-consultar-incidencias-registradas.pdf) (pág. 2)

**Patrones de diseño utilizados:** Tabla con paginación.

**Justificación:** La tabla permite revisar y comparar las incidencias por identificador, tipo, elemento afectado, estado, responsable y prioridad. La paginación facilita recorrer el listado si hay más registros de los que entran en una página.

**Formulario (si aplica):** No aplica.

---

## Pantalla / Módulo 3 — CU-03 — Detalle de incidencia

**Wireframe:** [`diagramas/wireframes/CU003-consultar-incidencias-registradas.pdf`](diagramas/wireframes/CU003-consultar-incidencias-registradas.pdf) (pág. 3)

**Patrones de diseño utilizados:** Vista de detalle organizada por bloques y visualización del archivo adjunto.

**Justificación:** La vista reúne la información necesaria para comprender la incidencia seleccionada: sus datos principales, estado, responsable, solicitante, descripción e imagen adjunta. También presenta accesos a funciones relacionadas, como gestionar la incidencia o registrar información.

**Formulario (si aplica):** No aplica.

- En las tablas, los encabezados identifican claramente cada columna y los estados se muestran con texto, para que la información no dependa únicamente del color.
---

## Consideraciones de accesibilidad

- En las tablas, los encabezados identifican claramente cada columna y los estados se muestran con texto, para que la información no dependa únicamente del color.

---

### Pantalla / Módulo 1 — CU-04 — Seleccionar prioridad de la incidencia

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 1)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Formulario contextual, listas desplegables y acciones explícitas para guardar o cancelar.

**Justificación:** La prioridad se asigna desde los datos de una incidencia concreta, por eso el formulario presenta su identificador y la información necesaria para reconocerla. El desplegable permite elegir entre valores definidos y evita diferencias de escritura. Las acciones Guardar cambios y Cancelar dejan claro cómo confirmar o descartar la operación.

**Formulario (si aplica):**
- Campos relevantes: urgencia, impacto y prioridad. Estado y responsable se muestran como información de la incidencia, sin modificarlos en este caso.
- Flujo: en una pantalla; el Responsable de Sistemas selecciona los valores y luego guarda o cancela los cambios.
- Validaciones relevantes: se deben completar los valores obligatorios antes de guardar.

### Pantalla / Módulo 2 — CU-04 — Desplegar las opciones de prioridad

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 2)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Lista desplegable con opciones predefinidas y selección visible.

**Justificación:** Presentar las opciones disponibles —Baja, Media, Alta y Vital— ayuda a que el Responsable de Sistemas use los niveles definidos por el sistema y reduce errores al asignar la prioridad.

**Formulario (si aplica):**
- Campos relevantes: prioridad; también deberían figurar urgencia e impacto, de acuerdo con la descripción del caso.
- Flujo: el usuario abre el selector y elige una opción.
- Validaciones relevantes: se debe seleccionar una prioridad antes de confirmar.

### Pantalla / Módulo 3 — CU-04 — Revisar la prioridad seleccionada

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 3)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Vista previa de los cambios y confirmación explícita.

**Justificación:** Mostrar la prioridad elegida antes de guardar permite revisar la decisión y corregirla si hace falta. Las opciones Guardar cambios y Cancelar hacen explícito que la selección todavía puede confirmarse o descartarse.

**Formulario (si aplica):**
- Campos relevantes: urgencia, impacto y prioridad seleccionados.
- Flujo: el Responsable de Sistemas revisa los valores y confirma o cancela.
- Validaciones relevantes: no se debe guardar si falta alguno de los valores obligatorios.

### Pantalla / Módulo 4 — CU-04 — Consultar la incidencia con la prioridad asignada

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 4)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Vista de detalle y presentación textual del estado de la incidencia.

**Justificación:** El detalle permite comprobar que la prioridad quedó asociada a la incidencia correcta y consultar el resto de su información en contexto.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos de la incidencia.