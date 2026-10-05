## Descripción del sistema

El sistema tiene como objetivo centralizar y organizar la gestión de incidencias técnicas de Logística y Minería S.A. Actualmente, las solicitudes de soporte se comunican mediante distintos canales, como teléfono, WhatsApp, correo electrónico o comunicación personal, y parte de la información se registra manualmente en planillas, lo que dificulta el seguimiento de los incidentes y la conservación de un historial completo.

La solución permitirá registrar, consultar, asignar, priorizar y realizar el seguimiento de las incidencias desde su creación hasta su resolución y cierre. También contemplará la participación de especialistas externos cuando una incidencia no pueda ser resuelta internamente y permitirá el registro de incidencias desde dispositivos móviles para aquellos usuarios que desarrollan sus tareas fuera de las instalaciones de la empresa.

## Requisitos funcionales

### Módulo 1 — Acceso y gestión de usuarios

| ID | Requisito |
|----|-----------|
| RF-01 | El sistema debe permitir a todo usuario autorizado iniciar sesión mediante credenciales individuales y acceder a las funciones habilitadas para su perfil. |
| RF-02 | El sistema debe permitir al Responsable de Sistemas registrar y habilitar a un Especialista Externo para participar en la atención de incidencias. El sistema deberá admitir múltiples especialistas externos habilitados de manera simultánea. |
| RF-03 | El sistema debe permitir al Responsable de Sistemas revocar el acceso de un Especialista Externo cuando deje de encontrarse autorizado. Una vez revocado el acceso, el especialista no deberá estar disponible para nuevas asignaciones. Si tiene incidencias abiertas asignadas, estas deberán quedar identificadas para su reasignación manual por parte del Responsable de Sistemas; el sistema no deberá reasignarlas automáticamente. |

### Módulo 2 — Registro de incidencias

| ID | Requisito |
|----|-----------|
| RF-04 | El sistema debe permitir al Solicitante registrar una incidencia mediante un formulario estandarizado con la información necesaria para su atención. Al confirmar el registro, la incidencia deberá quedar asociada al Solicitante, identificada de manera única, con estado “Nuevo” y disponible para su gestión. |
| RF-05 | El sistema debe permitir al Solicitante que realiza recorridos registrar una incidencia desde un dispositivo móvil, indicando el elemento afectado, sus datos identificatorios y una descripción de la situación. |
| RF-06 | El sistema debe permitir al Solicitante adjuntar imágenes como información complementaria de una incidencia. Se admitirán imágenes en formato PNG o JPEG de hasta 15 MB por archivo. |

### Módulo 3 — Consulta y seguimiento de incidencias

| ID | Requisito |
|----|-----------|
| RF-07 | El sistema debe permitir al Solicitante consultar el estado de sus incidencias y conocer quién se encuentra a cargo de su resolución. |
| RF-08 | El sistema debe permitir al Responsable de Sistemas consultar las incidencias registradas y acceder a la información asociada a cada una para realizar su gestión. |
| RF-09 | El sistema debe permitir al Especialista Externo consultar las incidencias que le hayan sido asignadas y acceder únicamente a la información necesaria para su atención. |
| RF-10 | El sistema debe permitir al Responsable de Sistemas consultar el historial de cada incidencia, incluyendo acciones realizadas, intervenciones externas y resoluciones registradas, para utilizar esa información como antecedente ante problemas similares. |

### Módulo 4 — Gestión y asignación de incidencias

| ID | Requisito |
|----|-----------|
| RF-11 | El sistema debe permitir al Responsable de Sistemas asignar o actualizar directamente la prioridad de una incidencia, seleccionando una de las siguientes opciones: Baja, Media, Alta o Vital. |
| RF-12 | El sistema debe permitir al Responsable de Sistemas actualizar el estado de una incidencia durante su gestión y al Especialista Externo actualizar el estado de las incidencias que tenga asignadas. Ante un cambio de estado, el sistema deberá informar al Solicitante. |
| RF-13 | El sistema debe permitir al Responsable de Sistemas asignar o reasignar la responsabilidad de una incidencia a un responsable interno o a un Especialista Externo habilitado. Cuando cambie el responsable, el sistema deberá informar al Solicitante. |
| RF-14 | El sistema debe permitir al Especialista Externo informar que no podrá hacerse cargo de una incidencia que tiene asignada. El sistema deberá registrar el aviso, informar al Responsable de Sistemas e identificar la incidencia para su reasignación manual. El sistema no deberá realizar la reasignación automáticamente. |

### Módulo 5 — Resolución e historial de intervenciones

| ID | Requisito |
|----|-----------|
| RF-15 | El sistema debe permitir al Responsable de Sistemas registrar las acciones realizadas durante la atención de una incidencia y conservarlas como parte de su historial, sin modificar el estado de la incidencia por ese solo registro. |
| RF-16 | El sistema debe permitir al Especialista Externo registrar avances, diagnósticos, acciones realizadas y soluciones propuestas en las incidencias que tenga asignadas. Estos registros deberán incorporarse al historial sin modificar el estado de la incidencia. |
| RF-17 | El sistema debe permitir al Responsable de Sistemas registrar la resolución final y cerrar una incidencia que se encuentre en estado “Resuelto”. No será necesario que existan acciones previas para registrar la resolución final. Al confirmarla, el sistema deberá conservarla en el historial, cambiar el estado a “Cerrado” e informar al Solicitante. |

## Requisitos no funcionales

### Seguridad e integridad de la información

| ID | Requisito |
|----|-----------|
| RNF-01 | La solución deberá proteger la información transmitida entre los dispositivos de los usuarios y el servidor mediante comunicaciones cifradas. Toda comunicación realizada a través de la red deberá utilizar HTTPS con TLS 1.2 o superior, sin permitir el envío de credenciales o información de incidencias mediante conexiones HTTP no cifradas. |
| RNF-02 | Ante una interrupción inesperada del servicio y su posterior reinicio, la información correspondiente a las operaciones confirmadas antes de la interrupción deberá permanecer registrada. |
| RNF-03 | Ante una pérdida total simulada del entorno de almacenamiento, la información deberá poder recuperarse mediante las copias de respaldo. Para este escenario se admitirá una pérdida máxima de información de 24 horas y el servicio deberá restablecerse en un plazo máximo de 4 horas. |

### Recuperabilidad y disponibilidad de la información

| ID | Requisito |
|----|-----------|
| RNF-04 | El sistema deberá conservar el historial completo de cada incidencia, incluyendo cambios de estado, asignaciones, acciones, intervenciones externas y resolución, durante un período de 2 años desde el cierre de la incidencia. |

### Usabilidad

| ID | Requisito |
|----|-----------|
| RNF-05 | La interfaz deberá presentarse completamente en idioma español. El 100 % de las pantallas utilizadas por Solicitantes, Responsables de Sistemas y Especialistas Externos deberá presentar títulos, campos, acciones, mensajes de validación y notificaciones en español. |
| RNF-06 | El proceso de registro de una incidencia deberá poder realizarse de manera simple y con una cantidad reducida de pasos. En una prueba con usuarios, un Solicitante deberá poder registrar una incidencia básica en un máximo de 2 minutos sin recibir asistencia durante la operación. |

### Usabilidad móvil

| ID | Requisito |
|----|-----------|
| RNF-07 | La solución deberá brindar una interfaz adecuada para los Solicitantes que registran incidencias desde dispositivos móviles. En una pantalla de 360 px de ancho o superior, el usuario deberá poder visualizar y completar el registro sin desplazamiento horizontal y acceder a las acciones necesarias para adjuntar imágenes y confirmar la operación. |

### Rendimiento y capacidad

| ID | Requisito |
|----|-----------|
| RNF-08 | Con hasta 50 usuarios conectados simultáneamente, al menos el 95 % de las operaciones de apertura de listados, consulta de una incidencia y guardado de cambios deberá completarse en un máximo de 3 segundos, excluyendo la transferencia de archivos adjuntos. |
| RNF-09 | Con 50 usuarios simultáneos realizando operaciones habituales, el sistema deberá mantener los límites de respuesta establecidos en RNF-08 y no deberá producir errores atribuibles a falta de capacidad del servicio. |

### Compatibilidad

| ID | Requisito |
|----|-----------|
| RNF-10 | Las funciones principales de la interfaz web deberán poder ejecutarse correctamente en las dos últimas versiones estables de Chrome, Edge, Firefox y Safari, sin pérdida de funcionalidad. |

### Gestión de errores

| ID | Requisito |
|----|-----------|
| RNF-11 | Cuando una operación no pueda completarse por datos faltantes o inválidos, el mensaje de validación deberá identificar el campo o dato involucrado y el motivo del rechazo, evitando mensajes genéricos que no permitan determinar la causa. |
