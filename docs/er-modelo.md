# Modelo Entidad-Relación

## Diagrama

@startuml
' Configuración visual del diagrama
hide circle
skinparam linetype ortho
skinparam EntityBackgroundColor #F9F9F9

' --- Entidades y Atributos ---

entity "PERSONA" {
  * id_persona : PK
}

entity "EMPLEADO" {
  * id_persona : PK, FK
}

entity "ESPECIALISTA_EXTERNO" {
  * id_persona : PK, FK
  --
  id_especialidad : FK
}

entity "ROL" {
  * id_rol : PK
}

entity "EMPLEADO_ROL" {
  * id_persona : PK, FK
  * id_rol : PK, FK
}

entity "ESPECIALIDAD" {
  * id_especialidad : PK
}

entity "INCIDENCIA" {
  * id_incidencia : PK
  --
  id_empleado_solicitante : FK
  elemento_identificador : FK
}

entity "ELEMENTO" {
  * identificador_elemento : PK
}

entity "ADJUNTO" {
  --
  id_incidencia : FK
}

entity "HISTORIAL" {
  --
  id_incidencia : FK
  id_persona : FK
}

entity "ASIGNACION" {
  --
  id_incidencia : FK
  id_persona_asignada : FK
}

' --- Relaciones ---

' Herencia de Persona (1 a 1)
PERSONA ||--|| EMPLEADO 
PERSONA ||--|| ESPECIALISTA_EXTERNO 

' Relación de Especialista con Especialidad
ESPECIALIDAD ||--o{ ESPECIALISTA_EXTERNO}

' Relación de muchos a muchos resuelta con tabla intermedia (Empleado - Rol)
EMPLEADO ||--o{ EMPLEADO_ROL}
ROL ||--o{ EMPLEADO_ROL}

' Relaciones principales de la Incidencia
EMPLEADO ||--o{ INCIDENCIA} 
ELEMENTO ||--o{ INCIDENCIA}

' Tablas dependientes de la Incidencia (transfieren el ID como FK)
INCIDENCIA ||--o{ ADJUNTO}
INCIDENCIA ||--o{ HISTORIAL}
INCIDENCIA ||--o{ ASIGNACION}

' Conexiones de Historial y Asignación con las personas involucradas
PERSONA ||--o{ HISTORIAL}
PERSONA ||--o{ ASIGNACION}

@enduml

## Entidades

| Entidad                  | Descripción                                                                                               | Relaciones clave                                                                                                                                                                                           |
|--------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **PERSONA**              | Tabla principal que almacena los datos básicos. Su clave primaria (PK) es `id_persona`.          | Es la tabla "padre". Su PK es utilizada como clave foránea (FK) en `EMPLEADO` y `ESPECIALISTA_EXTERNO`.                                                                                           |
| **EMPLEADO**             | Tabla que representa al empleado, heredando de `PERSONA`.                                        | Su `id_persona` actúa como PK y FK al mismo tiempo. Se relaciona con `ROL` mediante la tabla intermedia `EMPLEADO_ROL` y con `INCIDENCIA` como solicitante.                              |
| **ESPECIALISTA_EXTERNO** | Tabla que representa al técnico externo, heredando de `PERSONA`.                                 | Su `id_persona` es PK y FK[cite: 3]. Posee una clave foránea (`id_especialidad`) que lo conecta directamente con `ESPECIALIDAD`.                                                                  |
| **ROL**                  | Catálogo de roles del sistema. Su PK es `id_rol`.                                                | Se vincula a los empleados a través de la tabla `EMPLEADO_ROL`.                                                                                                                                   |
| **EMPLEADO_ROL**         | Tabla intermedia para resolver la relación de muchos a muchos entre empleados y roles.           | Su clave primaria compuesta está formada por dos claves foráneas: `id_persona` e `id_rol`.                                                                                                        |
| **ESPECIALIDAD**         | Catálogo de especialidades. Su PK es `id_especialidad`.                                          | Es referenciada mediante una clave foránea (FK) desde la tabla `ESPECIALISTA_EXTERNO`.                                                                                                            |
| **INCIDENCIA**           | Tabla central del sistema. Su PK es `id_incidencia`.                                             | Posee claves foráneas hacia `EMPLEADO` (`id_empleado_solicitante`) y `ELEMENTO` (`elemento_identificador`). Su ID se transfiere como FK a `ASIGNACION`, `ADJUNTO` e `HISTORIAL`.           |
| **ELEMENTO**             | Catálogo de elementos que pueden fallar. Su PK es `identificador_elemento`.                      | Es referenciada directamente por la tabla `INCIDENCIA` mediante una FK.                                                                                                                           |
| **ADJUNTO**              | Almacena los archivos del reporte.                                                               | Se vincula a una incidencia específica mediante la clave foránea `id_incidencia`.                                                                                                                 |
| **HISTORIAL**            | Tabla de registro de eventos.                                                                    | Se vincula a una incidencia mediante `id_incidencia` (FK) y a la persona involucrada mediante `id_persona` (FK).                                                                                  |
| **ASIGNACION**           | Tabla que registra la derivación del problema (en el diagrama original dice ASGINACION).         | Contiene claves foráneas que la vinculan a la incidencia (`id_incidencia`) y a la persona encargada (`id_persona_asignada`).                                                                      |


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

### Decisión 1 — [Transformación de "Especialidad" en entidad independiente]
Inicialmente, se consideró modelar la especialidad simplemente como un atributo dentro de la entidad ESPECIALISTA_EXTERNO. Esta alternativa se descartó porque limitaba a cada especialista externo a poseer una sola especialidad. En su lugar, se decidió que ESPECIALIDAD sea una entidad en sí misma, estableciendo una relación de muchos a muchos (N a N) con ESPECIALISTA_EXTERNO. Esta decisión de diseño permite que un mismo especialista pueda tener más de una especialidad asociada en el sistema.
### Decisión 2 — [Eliminación de atributos redundantes en "Incidencia"Título]
En una primera versión del diagrama, se habían incluido los atributos de fecha de resolución y descripción de resolución directamente en la entidad INCIDENCIA. Se descartó mantenerlos allí al detectar que se estaban duplicando datos que ya estaban presentes en la entidad HISTORIAL. Por lo tanto, se tomó la decisión de sacar esos atributos de INCIDENCIA y dejarlos exclusivamente en HISTORIAL, evitando así la redundancia de información en la base de datos.
