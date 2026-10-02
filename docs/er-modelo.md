# Modelo Entidad-Relación

## Diagrama

_Incluir el código PlantUML en `diagramas/er.puml`._
_Visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/)._

## Entidades

|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|                    Entidad                 |                                Descripción                      |                                              Relaciones clave                                        |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|                **PERSONA**                 | Tabla principal que almacena los datos básicos.                 | Es la tabla "padre". Su PK es utilizada como clave foránea (FK).                                     |
|                                            | Su clave primaria (PK) es `id_persona.                          | en `EMPLEADO` y `ESPECIALISTA_EXTERNO                                                                |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|               **EMPLEADO**                 | Tabla que representa al empleado,                               | Su `id_persona` actúa como PK y FK al mismo tiempo.                                                  |
|                                            | heredando de `PERSONA                                           | Se relaciona con `ROL` mediante la tabla intermedia `EMPLEADO_ROL`                                   |
|                                            |                                                                 | y con `INCIDENCIA` como solicitante.                                                                 |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|         **ESPECIALISTA_EXTERNO**           | Tabla que representa al técnico externo,                        | Su `id_persona` es PK y FK. Posee una clave foránea                                                  |
|                                            | heredando de `PERSONA`.                                         |(`id_especialidad`) que lo conecta directamente con `ESPECIALIDAD`.                                   |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|                **ROL**                     | Catálogo de roles del sistema. Su PK es `id_rol`.               | Se vincula a los empleados a través de la tabla `EMPLEADO_ROL`.                                      |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|            **EMPLEADO_ROL**                | Tabla intermedia para resolver la relación de                   | Su clave primaria compuesta está formada                                                             |
|                                            | muchos a muchos entre empleados y roles.                        | por dos claves foráneas: `id_persona` e `id_rol`.                                                    |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|             **ESPECIALIDAD**               | Catálogo de especialidades.                                     | Es referenciada mediante una clave foránea (FK)                                                      |
|                                            | Su PK es `id_especialidad`.                                     | desde la tabla `ESPECIALISTA_EXTERNO`.                                                               |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|               **INCIDENCIA**               | Tabla central del sistema.                                      | Posee claves foráneas hacia `EMPLEADO` (`id_empleado_solicitante`)                                   |
|                                            | Su PK es `id_incidencia`.                                       | y `ELEMENTO` (`elemento_identificador`). Su ID se transfiere como                                    |
|                                            |                                                                 | FK a `ASIGNACION`, `ADJUNTO` e `HISTORIAL`.                                                          |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|               **ELEMENTO**                 | Catálogo de elementos que pueden fallar.                        | Es referenciada directamente por la tabla `INCIDENCIA` mediante una FK.                              |
|                                            | Su PK es identificador_elemento`.                               |                                                                                                      |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|                 **ADJUNTO**                | Almacena los archivos del reporte.                              | Se vincula a una incidencia específica mediante                                                      |
|                                            |                                                                 | la clave foránea `id_incidencia`.                                                                    |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|               **HISTORIAL**                | Tabla de registro de eventos.                                   | Se vincula a una incidencia mediante `id_incidencia` (FK)                                            |
|                                            |                                                                 | y a la persona involucrada mediante `id_persona` (FK).                                               |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|             **ASIGNACION**                 | Tabla que registra la derivación del problema.                  | Contiene claves foráneas que la vinculan a la incidencia (`id_incidencia`)                           |
|                                            |                                                                 | y a la persona encargada (`id_persona_asignada`).                                                    |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|


## Descripción de atributos principales

### PERSONA
- `id_persona` (PK): Identificador único de cada persona registrada en el sistema.
- `dni` (UQ): Documento Nacional de Identidad, debe ser un valor único.
- `nombre`: Nombre de la persona.
- `apellido`: Apellido de la persona.
- `correo`: Dirección de correo electrónico de contacto.

### EMPLEADO
- `id_persona` (PK, FK): Identificador que hereda de la entidad PERSONA, actuando como clave primaria y foránea.

### ESPECIALISTA_EXTERNO
- `id_persona` (PK, FK): Identificador que hereda de la entidad PERSONA.
- `id_especialidad` (FK): Referencia a la especialidad técnica del profesional.
- `telefono`: Número de contacto del especialista.
- `estado_habilitacion`: Indica si el técnico está activo o habilitado para operar.

### ROL
- `id_rol` (PK): Identificador único del rol en el sistema.
- `nombre` (UQ): Denominación del perfil o cargo, el cual no puede repetirse.

### EMPLEADO_ROL
- `id_persona` (PK, FK): Referencia al empleado al que se le asigna el rol.
- `id_rol` (PK, FK): Referencia al rol asignado al empleado.

### ESPECIALIDAD
- `id_especialidad` (PK): Identificador único de la especialidad técnica.

### INCIDENCIA
- `id_incidencia` (PK): Identificador único del ticket o reporte de incidencia.
- `id_empleado_solicitante` (FK): Referencia al empleado que registró el reporte.
- `elemento_identificador` (FK): Referencia al elemento u objeto afectado por la falla.
- `fecha_hora_creacion`: Sello de tiempo del momento exacto del reporte.
- `tipo_incidencia`: Categorización general del problema reportado.
- `descripcion`: Detalle textual de la falla reportada.
- `prioridad`: Nivel de urgencia asignado para su resolución.
- `estado_actual`: Situación en la que se encuentra el ciclo de vida de la incidencia.

### ELEMENTO
- `identificador_elemento` (PK): Código o ID único del componente, equipo o servicio afectado.
- `tipo_elemento`: Clasificación o categoría del elemento.
- `descripcion`: Nombre o detalles técnicos del elemento.

### ADJUNTO
- `id_adjunto` (PK): Identificador único del archivo subido.
- `id_incidencia` (FK): Referencia a la incidencia a la que pertenece el documento o imagen.
- `nombre_archivo`: Nombre del archivo original.
- `tipo_archivo`: Extensión o formato (ej. jpg, pdf).
- `ubicacion`: Ruta de almacenamiento o enlace de acceso al archivo.

### HISTORIAL
- `id_historial` (PK): Identificador único del registro de evento.
- `id_incidencia` (FK): Referencia a la incidencia que sufrió un cambio o actualización.
- `id_persona` (FK): Referencia al usuario que ejecutó la acción.
- `fecha_hora`: Momento exacto en que ocurrió el evento.
- `tipo_evento`: Clasificación de la acción (ej. cambio de estado, comentario).
- `descripcion`: Notas o justificación del cambio realizado.

### ASIGNACION
- `id_asignacion` (PK): Identificador único de la tarea o derivación.
- `id_incidencia` (FK): Referencia a la incidencia que debe ser resuelta.
- `id_persona_asignada` (FK): Referencia a la persona encargada de solucionar el problema.
- `fecha_hora`: Momento en que se asignó la tarea.
- `estado_asignacion`: Situación de la tarea (ej. pendiente, en progreso).
- `motivo_rechazo`: Justificación en caso de que la persona asignada no acepte la tarea.

## Decisiones de diseño

_Justificar al menos dos decisiones de diseño relevantes: por qué se modeló de esa manera,
qué alternativas se consideraron y por qué se descartaron._

### Decisión 1 — [Título]

### Decisión 2 — [Título]
