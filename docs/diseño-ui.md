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

-
