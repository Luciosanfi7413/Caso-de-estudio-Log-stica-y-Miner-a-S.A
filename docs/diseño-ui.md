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

### Pantalla / Módulo 1 — CU-04 — Seleccionar prioridad de la incidencia

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 1)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Formulario contextual, listas desplegables y acciones explícitas para guardar o cancelar.

**Justificación:** La prioridad se asigna desde los datos de una incidencia concreta, por eso el formulario presenta su identificador y la información necesaria para reconocerla. El desplegable permite elegir entre valores definidos y evita diferencias de escritura. Las acciones Guardar cambios y Cancelar dejan claro cómo confirmar o descartar la operación.

**Formulario (si aplica):**
- Campos relevantes: identificador de la incidencia, prioridad actual (si posee una) y prioridad seleccionada.
- Flujo: en una pantalla, el Responsable de Sistemas selecciona una prioridad —Baja, Media, Alta o Vital— y luego guarda o cancela.
- Validaciones relevantes: se debe seleccionar una prioridad antes de guardar.

### Pantalla / Módulo 2 — CU-04 — Desplegar las opciones de prioridad

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 2)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Lista desplegable con opciones predefinidas y selección visible.

**Justificación:** Presentar las opciones disponibles —Baja, Media, Alta y Vital— ayuda a que el Responsable de Sistemas use los niveles definidos por el sistema y reduce errores al asignar la prioridad.

**Formulario (si aplica):**
- Campo relevante: prioridad.
- Opciones disponibles: Baja, Media, Alta y Vital.
- Flujo: el Responsable de Sistemas abre el selector y elige una opción.
- Validaciones relevantes: se debe seleccionar una prioridad antes de confirmar.

### Pantalla / Módulo 3 — CU-04 — Revisar la prioridad seleccionada

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 3)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Vista previa de los cambios y confirmación explícita.

**Justificación:** Mostrar la prioridad elegida antes de guardar permite revisar la decisión y corregirla si hace falta. Las opciones Guardar cambios y Cancelar hacen explícito que la selección todavía puede confirmarse o descartarse.

**Formulario (si aplica):**
- Campo relevante: prioridad seleccionada.
- Flujo: el Responsable de Sistemas revisa la prioridad y confirma o cancela la operación.
- Validaciones relevantes: no se debe guardar si no se seleccionó una prioridad.

### Pantalla / Módulo 4 — CU-04 — Consultar la incidencia con la prioridad asignada

**Wireframe:** [diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf (pág. 4)](diagramas/wireframes/CU004-asignar-prioridad-incidencia.pdf)

**Patrones de diseño utilizados:** Vista de detalle y presentación textual del estado de la incidencia.

**Justificación:** El detalle permite comprobar que la prioridad quedó asociada a la incidencia correcta y consultar el resto de su información en contexto.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos de la incidencia.

---

### Pantalla / Módulo 1 — CU-05 — Seleccionar un nuevo estado

**Wireframe:** [diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf (pág. 1)](diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Formulario contextual, campos desplegables y acciones explícitas para guardar o cancelar.

**Justificación:** El formulario presenta los datos de la incidencia junto con el estado actual, para que el Responsable de Sistemas confirme que está modificando la incidencia correcta. Las acciones Guardar cambios y Cancelar hacen explícito cómo confirmar o descartar la modificación.

**Formulario (si aplica):**
- Campos relevantes: Estado editable; prioridad y responsable como datos de consulta, sin posibilidad de modificarlos en este caso.
- Flujo: en una pantalla, el Responsable de Sistemas selecciona un nuevo estado y guarda o cancela el cambio.
- Validaciones relevantes: se debe seleccionar un nuevo estado antes de guardar.

### Pantalla / Módulo 2 — CU-05 — Desplegar los estados disponibles

**Wireframe:** [diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf (pág. 2)](diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Lista desplegable con opciones predefinidas.

**Justificación:** La lista presenta los estados habilitados —Nuevo, En curso, Pendiente y Resuelto— y ayuda a evitar valores escritos de distintas maneras.

**Formulario (si aplica):**
- Campo relevante: Estado.
- Flujo: el usuario abre el selector y elige una opción.
- Validaciones relevantes: solo se pueden seleccionar los estados disponibles.

### Pantalla / Módulo 3 — CU-05 — Revisar el estado seleccionado

**Wireframe:** [diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf (pág. 3)](diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Vista previa del cambio y confirmación explícita.

**Justificación:** El estado seleccionado queda visible antes de guardar, de modo que el Responsable de Sistemas pueda revisarlo y corregirlo si es necesario.

**Formulario (si aplica):**
- Campo relevante: Estado seleccionado.
- Flujo: el usuario revisa el nuevo valor y confirma o cancela la actualización.
- Validaciones relevantes: el cambio se aplica solo al seleccionar Guardar cambios.

### Pantalla / Módulo 4 — CU-05 — Consultar la incidencia con el estado actualizado

**Wireframe:** [diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf (pág. 4)](diagramas/wireframes/CU005-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Vista de detalle y presentación textual del estado actualizado.

**Justificación:** Mostrar el nuevo estado en el detalle permite verificar que la actualización quedó reflejada en la incidencia.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos de la incidencia.

---

### Pantalla / Módulo 1 — CU-06 — Seleccionar responsable

**Wireframe:** [diagramas/wireframes/CU006-asignar-responsable.pdf (pág. 1)](diagramas/wireframes/CU006-asignar-responsable.pdf)

**Patrones de diseño utilizados:** Formulario contextual, lista desplegable y acciones explícitas para guardar o cancelar.

**Justificación:** El formulario muestra los datos básicos de la incidencia junto con su responsable actual, si lo tiene. Así, el Responsable de Sistemas puede verificar que está trabajando sobre la incidencia correcta y ver a quién se reemplazará, si corresponde.

**Formulario (si aplica):**
- Campos relevantes: tipo de responsable —interno o especialista externo— y responsable disponible.
- Flujo: en una pantalla, se selecciona el tipo de responsable y luego una persona de la lista.
- Validaciones relevantes: se debe seleccionar un responsable antes de confirmar la asignación.

### Pantalla / Módulo 2 — CU-06 — Revisar la asignación

**Wireframe:** [diagramas/wireframes/CU006-asignar-responsable.pdf (pág. 2)](diagramas/wireframes/CU006-asignar-responsable.pdf)

**Patrones de diseño utilizados:** Vista previa del cambio y confirmación explícita.

**Justificación:** Mostrar el responsable elegido antes de guardar permite revisar la asignación y comparar el nuevo responsable con el actual. Las acciones Guardar cambios y Cancelar permiten confirmar o descartar el cambio.

**Formulario (si aplica):**
- Campos relevantes: tipo de responsable y nuevo responsable seleccionado.
- Flujo: el Responsable de Sistemas revisa la selección y guarda o cancela.
- Validaciones relevantes: se debe seleccionar un responsable disponible antes de guardar.

### Pantalla / Módulo 3 — CU-06 — Consultar la incidencia con el responsable asignado

**Wireframe:** [diagramas/wireframes/CU006-asignar-responsable.pdf (pág. 3)](diagramas/wireframes/CU006-asignar-responsable.pdf)

**Patrones de diseño utilizados:** Vista de detalle y presentación textual de la asignación actualizada.

**Justificación:** Mostrar el nombre del nuevo responsable en el detalle permite comprobar que la asignación quedó asociada a la incidencia correcta.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos de la incidencia.

---

### Pantalla / Módulo 1 — CU-07 — Acceder a la gestión de especialistas externos

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (págs. 1 y 2)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Panel de opciones organizado por áreas funcionales y acceso mediante una acción identificable.

**Justificación:** La opción “Gestionar especialistas externos” está ubicada junto a las funciones de gestión de incidencias, lo que ayuda al Responsable de Sistemas a encontrarla dentro del área de soporte.

**Formulario (si aplica):** No aplica. Es una pantalla de navegación.

### Pantalla / Módulo 2 — CU-07 — Consultar especialistas externos registrados

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (pág. 3)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Tabla de datos y acción principal para registrar un especialista.

**Justificación:** La tabla permite comparar en un mismo lugar los datos y el estado de acceso de cada especialista. La acción “Registrar Especialista Externo” está disponible desde el listado para iniciar el alta.

**Formulario (si aplica):** No aplica. Esta pantalla muestra el listado de especialistas.

### Pantalla / Módulo 3 — CU-07 — Registrar especialista externo

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (págs. 4, 5 y 6)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Formulario con campos obligatorios identificados y confirmación mediante una acción explícita.

**Justificación:** El formulario reúne los datos necesarios para registrar al especialista y diferencia los campos obligatorios del teléfono opcional. Completar los datos antes de confirmar permite revisar la información ingresada.

**Formulario (si aplica):**
- Campos: nombre, apellido, especialidad, correo electrónico y teléfono opcional.
- Flujo: en una pantalla; el Responsable de Sistemas completa los datos y confirma el registro.
- Validaciones relevantes: nombre, apellido, especialidad y correo electrónico deben completarse; el teléfono es opcional.

### Pantalla / Módulo 4 — CU-07 — Consultar el listado después del registro

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (pág. 7)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Tabla con actualización visible y estado textual.

**Justificación:** La inclusión del nuevo especialista en el listado permite comprobar que el registro se realizó y que quedó habilitado para futuras asignaciones.

**Formulario (si aplica):** No aplica. Esta pantalla muestra el listado actualizado.

### Pantalla / Módulo 5 — CU-07 — Consultar y cambiar el estado de acceso

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (pág. 8)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Vista de detalle, estado actual visible y acción contextual.

**Justificación:** Presentar los datos del especialista junto con su estado actual permite verificar que se seleccionó el registro correcto. La acción disponible depende de ese estado: en este ejemplo, “Habilitar acceso”.

**Formulario (si aplica):**
- Datos mostrados: nombre, apellido, especialidad, correo electrónico, teléfono y estado de acceso.
- Flujo: se selecciona la acción habilitada o revocada que corresponda al estado actual.
- Validaciones relevantes: solo se debe ofrecer la acción válida para el estado actual del especialista.

### Pantalla / Módulo 6 — CU-07 — Confirmar el cambio de acceso

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (pág. 9)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Diálogo de confirmación que resume el cambio antes de aplicarlo.

**Justificación:** Informar quién cambiará de estado y mostrar el estado anterior y el nuevo reduce el riesgo de confirmar el cambio sobre el especialista equivocado.

**Formulario (si aplica):** No aplica. El diálogo permite confirmar o cancelar la operación.

### Pantalla / Módulo 7 — CU-07 — Consultar el listado después del cambio de acceso

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (pág. 10)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Tabla actualizada y estado textual.

**Justificación:** El estado “Habilitado” queda visible en el listado, lo que permite verificar el resultado de la operación.

**Formulario (si aplica):** No aplica. Esta pantalla muestra el listado actualizado.

### Pantalla / Módulo 8 — CU-07 — Validar los datos del registro

**Wireframe:** [diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf (págs. 11, 12, 13 y 14)](diagramas/wireframes/CU007-gestionar-especialistas-externos.pdf)

**Patrones de diseño utilizados:** Validación junto al campo y conservación de los datos ingresados ante un error.

**Justificación:** Mostrar el motivo del error junto al campo permite identificar qué debe corregirse. Mantener los demás datos en el formulario evita que el usuario tenga que volver a cargarlos.

**Formulario (si aplica):**
- Campos: nombre, apellido, especialidad, correo electrónico y teléfono opcional.
- Validaciones relevantes: se informa si falta completar la especialidad o si el correo electrónico ya está registrado.

---

### Pantalla / Módulo 1 — CU-08 — Consultar incidencias asignadas

**Wireframe:** [diagramas/wireframes/CU008-gestionar-incidencia-especialista-externo.pdf (pág. 1)](diagramas/wireframes/CU008-gestionar-incidencia-especialista-externo.pdf)

**Patrones de diseño utilizados:** Tabla de datos y navegación por páginas.

**Justificación:** El listado muestra las incidencias asignadas al Especialista Externo y permite comparar su identificador, tipo, elemento afectado, estado, responsable y prioridad. La paginación permite recorrer los resultados sin mostrar todos los registros a la vez.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar y seleccionar una incidencia.

### Pantalla / Módulo 2 — CU-08 — Consultar el detalle de la incidencia

**Wireframe:** [diagramas/wireframes/CU008-gestionar-incidencia-especialista-externo.pdf (pág. 2)](diagramas/wireframes/CU008-gestionar-incidencia-especialista-externo.pdf)

**Patrones de diseño utilizados:** Vista de detalle y acciones contextuales.

**Justificación:** El detalle reúne la información necesaria para comprender la incidencia asignada, incluyendo su descripción y archivo adjunto. Las acciones “Gestionar incidencia” y “Registrar información” están disponibles desde el contexto de esa incidencia.

**Formulario (si aplica):** No aplica en esta pantalla. Desde “Registrar información” se inicia el registro del seguimiento.

---

### Pantalla / Módulo 1 — CU-09 — Consultar incidencias registradas

**Wireframe:** [diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf (pág. 1)](diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf)

**Patrones de diseño utilizados:** Tabla de datos y navegación por páginas.

**Justificación:** El listado permite al Responsable de Sistemas revisar las incidencias registradas y reconocerlas por su identificador, tipo, elemento afectado, estado, responsable y prioridad.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar y seleccionar una incidencia.

### Pantalla / Módulo 2 — CU-09 — Consultar el detalle de la incidencia

**Wireframe:** [diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf (pág. 2)](diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf)

**Patrones de diseño utilizados:** Vista de detalle y acciones contextuales.

**Justificación:** El detalle reúne la información necesaria para revisar la incidencia antes de registrar información sobre su tratamiento. La acción “Registrar información” permite iniciar el registro desde la incidencia correspondiente.

**Formulario (si aplica):** No aplica en esta pantalla.

### Pantalla / Módulo 3 — CU-09 — Registrar una acción realizada

**Wireframe:** [diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf (págs. 3, 4 y 5)](diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf)

**Patrones de diseño utilizados:** Formulario contextual, selección del tipo de registro y descripción con confirmación explícita.

**Justificación:** El formulario se abre desde el detalle de la incidencia y permite registrar la acción realizada en ese contexto. El Responsable de Sistemas puede revisar la descripción antes de confirmarla.

**Formulario (si aplica):**
- Campos relevantes: tipo de registro y descripción de la acción realizada.
- Flujo: se selecciona “Acción realizada”, se completa la descripción y se confirma.
- Validaciones relevantes: la descripción es obligatoria.

### Pantalla / Módulo 4 — CU-09 — Confirmar el registro de una acción realizada

**Wireframe:** [diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf (págs. 6 y 7)](diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf)

**Patrones de diseño utilizados:** Mensaje de confirmación y actualización visible en el detalle.

**Justificación:** El mensaje informa que la acción se registró correctamente y el detalle permite continuar consultando la incidencia.

**Formulario (si aplica):** No aplica. Estas pantallas muestran la confirmación del registro.

### Pantalla / Módulo 5 — CU-09 — Validar la descripción de una acción realizada

**Wireframe:** [diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf (pág. 8)](diagramas/wireframes/CU009-seguimiento-y-resolucion-incidencia.pdf)

**Patrones de diseño utilizados:** Mensaje de error visible cuando falta un dato obligatorio.

**Justificación:** Informar que la descripción es obligatoria ayuda a corregir el formulario antes de registrar la acción.

**Formulario (si aplica):**
- Campo relevante: descripción de la acción realizada.
- Validaciones relevantes: no se permite confirmar si la descripción está vacía.

### Pantalla / Módulo 6 — CU-09 — Registrar la resolución final

**Wireframe:** [diagramas/wireframes/CU009-secuencia-2-resolucion-final.pdf (págs. 3, 4 y 5)](diagramas/wireframes/CU009-secuencia-2-resolucion-final.pdf)

**Patrones de diseño utilizados:** Formulario contextual, selección del tipo de registro y descripción con confirmación explícita.

**Justificación:** El formulario permite registrar la resolución final desde la incidencia. Mostrar la descripción antes de confirmar ayuda a revisar la información que se incorporará al historial.

**Formulario (si aplica):**
- Campos relevantes: tipo de registro y descripción de la resolución final.
- Flujo: se selecciona “Resolución final”, se completa la descripción y se confirma.
- Validaciones relevantes: la descripción es obligatoria.

### Pantalla / Módulo 7 — CU-09 — Confirmar el cierre de la incidencia

**Wireframe:** [diagramas/wireframes/CU009-secuencia-2-resolucion-final.pdf (págs. 6 y 7)](diagramas/wireframes/CU009-secuencia-2-resolucion-final.pdf)

**Patrones de diseño utilizados:** Mensaje de confirmación y estado actualizado en el detalle.

**Justificación:** La confirmación informa que la resolución final fue registrada y el detalle muestra la incidencia con estado “Cerrado”.

**Formulario (si aplica):** No aplica. Estas pantallas muestran la confirmación y el resultado del cierre.

### Pantalla / Módulo 8 — CU-09 — Validar la descripción de la resolución final

**Wireframe:** [diagramas/wireframes/CU009-secuencia-2-resolucion-final.pdf (pág. 8)](diagramas/wireframes/CU009-secuencia-2-resolucion-final.pdf)

**Patrones de diseño utilizados:** Mensaje de error asociado al campo obligatorio.

**Justificación:** El mensaje permite identificar que falta la descripción de la resolución antes de confirmar el registro.

**Formulario (si aplica):**
- Campo relevante: descripción de la resolución final.
- Validaciones relevantes: no se permite confirmar si la descripción está vacía.

---

### Pantalla / Módulo 1 — CU-10 — Acceder a la gestión de incidencias

**Wireframe:** [diagramas/wireframes/CU010-consultar-historial-incidencias.pdf (pág. 1)](diagramas/wireframes/CU010-consultar-historial-incidencias.pdf)

**Patrones de diseño utilizados:** Panel de opciones organizado por áreas funcionales.

**Justificación:** La opción de gestión de incidencias está ubicada junto a las demás funciones de soporte, lo que ayuda al Responsable de Sistemas a encontrar el módulo correspondiente.

**Formulario (si aplica):** No aplica. Es una pantalla de navegación.

### Pantalla / Módulo 2 — CU-10 — Consultar incidencias registradas

**Wireframe:** [diagramas/wireframes/CU010-consultar-historial-incidencias.pdf (pág. 2)](diagramas/wireframes/CU010-consultar-historial-incidencias.pdf)

**Patrones de diseño utilizados:** Tabla de datos y navegación por páginas.

**Justificación:** El listado permite identificar y seleccionar la incidencia cuyo historial se quiere consultar, mostrando datos como identificador, tipo, estado, responsable y prioridad.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar y seleccionar una incidencia.

### Pantalla / Módulo 3 — CU-10 — Consultar el detalle de la incidencia

**Wireframe:** [diagramas/wireframes/CU010-consultar-historial-incidencias.pdf (pág. 3)](diagramas/wireframes/CU010-consultar-historial-incidencias.pdf)

**Patrones de diseño utilizados:** Vista de detalle y acción contextual.

**Justificación:** El detalle permite confirmar que se seleccionó la incidencia correcta antes de abrir su historial. La acción “Consultar historial” está disponible junto a la información de esa incidencia.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos de la incidencia.

### Pantalla / Módulo 4 — CU-10 — Consultar el historial

**Wireframe:** [diagramas/wireframes/CU010-consultar-historial-incidencias.pdf (pág. 4)](diagramas/wireframes/CU010-consultar-historial-incidencias.pdf)

**Patrones de diseño utilizados:** Tabla cronológica en una ventana sobre el detalle de la incidencia.

**Justificación:** El historial reúne los cambios y registros en orden cronológico, con fecha, hora, tipo, responsable y detalle. De este modo, el Responsable de Sistemas puede revisar la evolución de la incidencia desde una misma vista.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar y seleccionar un registro del historial.

### Pantalla / Módulo 5 — CU-10 — Consultar el detalle de un registro del historial

**Wireframe:** [diagramas/wireframes/CU010-consultar-historial-incidencias.pdf (págs. 5 y 7)](diagramas/wireframes/CU010-consultar-historial-incidencias.pdf)

**Patrones de diseño utilizados:** Detalle contextual del registro seleccionado.

**Justificación:** Mostrar el contenido completo del registro seleccionado permite entender qué ocurrió, quién fue responsable y cuándo se realizó. Las páginas muestran ejemplos de un cambio de estado y de una resolución final.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar información registrada.

### Pantalla / Módulo 6 — CU-10 — Volver al detalle de la incidencia

**Wireframe:** [diagramas/wireframes/CU010-consultar-historial-incidencias.pdf (pág. 6)](diagramas/wireframes/CU010-consultar-historial-incidencias.pdf)

**Patrones de diseño utilizados:** Cierre de ventana superpuesta y retorno a la pantalla de origen.

**Justificación:** Al cerrar la ventana del historial, el Responsable de Sistemas vuelve al detalle de la incidencia que estaba consultando

---

### Pantalla / Módulo 1 — CU-11 — Acceder a la gestión de la incidencia

**Wireframe:** [diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf (pág. 1)](diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Vista de detalle y acción contextual.

**Justificación:** El detalle reúne los datos de la incidencia asignada. La acción “Gestionar incidencia” permite iniciar la actualización del estado desde el contexto de esa incidencia.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos de la incidencia y acceder a su gestión.

### Pantalla / Módulo 2 — CU-11 — Desplegar los estados disponibles

**Wireframe:** [diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf (pág. 2)](diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Formulario contextual y lista desplegable con opciones predefinidas.

**Justificación:** El selector muestra los estados que puede elegir el Especialista Externo: En curso, Pendiente y Resuelto. Presentar las opciones disponibles ayuda a evitar valores inválidos.

**Formulario (si aplica):**
- Campo relevante: Estado.
- Flujo: el Especialista Externo abre el selector y elige un estado.
- Validaciones relevantes: solo se pueden seleccionar los estados habilitados para la incidencia.

### Pantalla / Módulo 3 — CU-11 — Revisar el nuevo estado

**Wireframe:** [diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf (pág. 3)](diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Vista previa del cambio y acciones para guardar o cancelar.

**Justificación:** El nuevo estado queda visible antes de guardar, para que el Especialista Externo pueda revisar su selección. Las acciones Guardar cambios y Cancelar hacen explícito cómo confirmar o descartar la actualización.

**Formulario (si aplica):**
- Campo relevante: Estado seleccionado.
- Flujo: el Especialista Externo revisa el valor y guarda o cancela.
- Validaciones relevantes: se debe seleccionar un estado antes de guardar.

### Pantalla / Módulo 4 — CU-11 — Consultar la incidencia con el estado actualizado

**Wireframe:** [diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf (pág. 4)](diagramas/wireframes/CU011-actualizar-estado-incidencia.pdf)

**Patrones de diseño utilizados:** Vista de detalle y presentación textual del estado actualizado.

**Justificación:** Mostrar el nuevo estado en el detalle permite comprobar que el cambio quedó registrado en la incidencia.

**Formulario (si aplica):** No aplica. Esta pantalla permite consultar los datos actualizados.

---

### Pantalla / Módulo 1 — CU-12 — Acceder al registro de una acción

**Wireframe:** [diagramas/wireframes/CU012-registrar-accion-realizada.pdf (pág. 1)](diagramas/wireframes/CU012-registrar-accion-realizada.pdf)

**Patrones de diseño utilizados:** Vista de detalle y acción contextual.

**Justificación:** El detalle permite al Especialista Externo revisar la incidencia asignada antes de registrar una acción. La opción “Registrar información” inicia el registro desde el contexto de esa incidencia.

**Formulario (si aplica):** No aplica en esta pantalla.

### Pantalla / Módulo 2 — CU-12 — Seleccionar el tipo de registro

**Wireframe:** [diagramas/wireframes/CU012-registrar-accion-realizada.pdf (pág. 2)](diagramas/wireframes/CU012-registrar-accion-realizada.pdf)

**Patrones de diseño utilizados:** Ventana contextual y lista desplegable con tipos de registro disponibles.

**Justificación:** La ventana mantiene visible la incidencia asociada y permite seleccionar el tipo de información que se va a registrar.

**Formulario (si aplica):**
- Campo relevante: Tipo de registro.
- Flujo: el Especialista Externo despliega las opciones y selecciona “Acción realizada”.

### Pantalla / Módulo 3 — CU-12 — Confirmar el tipo de registro

**Wireframe:** [diagramas/wireframes/CU012-registrar-accion-realizada.pdf (pág. 3)](diagramas/wireframes/CU012-registrar-accion-realizada.pdf)

**Patrones de diseño utilizados:** Selección visible y avance por pasos.

**Justificación:** El tipo elegido queda visible antes de continuar, lo que permite verificar que se registrará la información con la categoría correcta.

**Formulario (si aplica):**
- Campo relevante: Tipo de registro.
- Flujo: el Especialista Externo revisa “Acción realizada” y continúa.

### Pantalla / Módulo 4 — CU-12 — Ingresar la descripción de la acción realizada

**Wireframe:** [diagramas/wireframes/CU012-registrar-accion-realizada.pdf (pág. 4)](diagramas/wireframes/CU012-registrar-accion-realizada.pdf)

**Patrones de diseño utilizados:** Formulario contextual, campo de descripción y confirmación explícita.

**Justificación:** El campo permite registrar el trabajo realizado en la incidencia. La acción “Confirmar” deja claro cuándo se incorpora la descripción.

**Formulario (si aplica):**
- Campo relevante: Descripción de la acción realizada.
- Flujo: el Especialista Externo escribe la descripción y confirma el registro.
- Validaciones relevantes: la descripción es obligatoria.

---

## Consideraciones de accesibilidad

- En las tablas, los encabezados identifican claramente cada columna. En el historial, los registros incluyen mediante texto la fecha, hora, tipo, responsable y detalle.
- Los estados de las incidencias y de acceso se muestran con texto —por ejemplo, “En curso”, “Resuelto”, “Habilitado” o “Revocado”— y las prioridades se identifican como “Baja”, “Media”, “Alta” o “Vital”; la información no depende únicamente del color.
- El tipo de responsable y el nombre de la persona asignada se identifican mediante texto.
- Los campos de los formularios tienen etiquetas textuales y los mensajes de validación indican qué dato falta o debe corregirse, junto al campo correspondiente.
- Los mensajes de confirmación y error explican mediante texto el resultado de la operación.