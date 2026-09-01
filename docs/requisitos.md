## Descripción del sistema

El sistema tiene como objetivo centralizar y organizar la gestión de incidencias técnicas de Logística y Minería S.A. Actualmente, las solicitudes de soporte se comunican mediante distintos canales, como teléfono, WhatsApp, correo electrónico o comunicación personal, y parte de la información se registra manualmente en planillas, lo que dificulta el seguimiento de los incidentes y la conservación de un historial completo.

La solución permitirá registrar, consultar, asignar, priorizar y realizar el seguimiento de las incidencias desde su creación hasta su resolución y cierre. También contemplará la participación de especialistas externos cuando una incidencia no pueda ser resuelta internamente y permitirá el registro de incidencias desde dispositivos móviles para aquellos usuarios que desarrollan sus tareas fuera de las instalaciones de la empresa.

## Requisitos funcionales

### Módulo 1 — Acceso y gestión de usuarios

| ID | Requisito |
|----|-----------|
| RF-01 | El sistema debe permitir a todo usuario autorizado iniciar sesión mediante credenciales individuales y acceder a las funciones habilitadas para su perfil. |
| RF-02 | El sistema debe permitir al Responsable de Sistemas registrar y habilitar a un Especialista Externo para participar en la atención de incidencias. El sistema deberá admitir múltiples especialistas externos habilitados de manera simultánea. |
| RF-03 | El sistema debe permitir al Responsable de Sistemas revocar el acceso de un Especialista Externo cuando deje de encontrarse autorizado para prestar servicios a la organización. |

### Módulo 2 — Registro de incidencias

| ID | Requisito |
|----|-----------|
| RF-04 | El sistema debe permitir al Solicitante registrar una incidencia mediante un formulario estandarizado que solicite la información necesaria para su atención. Al confirmar el registro, la incidencia deberá quedar asociada al solicitante, identificada de manera única y disponible para su gestión. |
| RF-05 | El sistema debe permitir al Chofer registrar una incidencia desde un dispositivo móvil durante sus recorridos, indicando el elemento afectado, sus datos identificatorios y una descripción de la situación. |
| RF-06 | El sistema debe permitir al Solicitante adjuntar imágenes o documentos como información complementaria de una incidencia, incluyendo fotografías de desperfectos informados durante los recorridos. |

### Módulo 3 — Consulta y seguimiento de incidencias

| ID | Requisito |
|----|-----------|
| RF-07 | El sistema debe permitir al Solicitante consultar el estado de sus incidencias y conocer quién se encuentra a cargo de su resolución. |
| RF-08 | El sistema debe permitir al Responsable de Sistemas consultar las incidencias registradas y acceder a la información asociada a cada una para realizar su gestión. |
| RF-09 | El sistema debe permitir al Especialista Externo consultar las incidencias que le hayan sido asignadas y acceder únicamente a la información necesaria para su atención. |
| RF-10 | El sistema debe permitir al Responsable de Sistemas consultar el historial de incidencias, acciones realizadas y soluciones registradas anteriormente, permitiendo utilizar esa información como antecedente ante problemas similares. |

### Módulo 4 — Gestión y asignación de incidencias

| ID | Requisito |
|----|-----------|
| RF-11 | El sistema debe permitir al Responsable de Sistemas establecer la prioridad de una incidencia utilizando criterios definidos de urgencia e impacto. |
| RF-12 | El sistema debe permitir al Responsable de Sistemas actualizar el estado de una incidencia durante su gestión. Cuando se produzca un cambio de estado, el sistema deberá informar al Solicitante. |
| RF-13 | El sistema debe permitir al Responsable de Sistemas asignar o reasignar la responsabilidad de una incidencia a un responsable interno o a un Especialista Externo autorizado. Cuando cambie el responsable, el sistema deberá informar al Solicitante. |

### Módulo 5 — Resolución e historial de intervenciones

| ID | Requisito |
|----|-----------|
| RF-14 | El sistema debe permitir al Responsable de Sistemas registrar las acciones realizadas durante la atención de una incidencia, conservando la información como parte de su historial. |
| RF-15 | El sistema debe permitir al Especialista Externo registrar avances, diagnósticos, acciones realizadas y la solución aplicada en las incidencias que se encuentren bajo su responsabilidad. |
| RF-16 | El sistema debe permitir al Responsable de Sistemas registrar la resolución final y cerrar una incidencia una vez finalizada su atención. La solución deberá conservarse junto con el historial de la incidencia. |

## Requisitos no funcionales

### Seguridad e integridad de la información

| ID | Requisito |
|----|-----------|
| RNF-01 | La solución deberá proteger la información transmitida entre los dispositivos de los usuarios y el servidor mediante comunicaciones cifradas. Toda comunicación realizada a través de la red deberá utilizar HTTPS con TLS 1.2 o superior, sin permitir el envío de credenciales o información de incidencias mediante conexiones HTTP no cifradas. |
| RNF-02 | La información confirmada por los usuarios no deberá perderse ante una interrupción inesperada del servicio. Después de simular una interrupción y reiniciar el servicio, toda incidencia, cambio de estado, asignación, comentario o resolución confirmada previamente deberá permanecer registrada. |

### Recuperabilidad y disponibilidad de la información

| ID | Requisito |
|----|-----------|
| RNF-03 | La solución deberá permitir recuperar la información ante una pérdida o falla del entorno donde se encuentre almacenada. Ante una pérdida total simulada, la pérdida máxima de información admitida será de 24 horas y el servicio deberá poder restablecerse en un plazo máximo de 4 horas. |

### Usabilidad

| ID | Requisito |
|----|-----------|
| RNF-04 | La interfaz deberá presentarse completamente en idioma español. El 100 % de las pantallas utilizadas por Solicitantes, Choferes, Responsable de Sistemas y Especialistas Externos deberá presentar títulos, campos, acciones, mensajes de validación y notificaciones en español. |
| RNF-05 | El proceso de registro de una incidencia deberá poder realizarse de manera simple y con una cantidad reducida de pasos. En una prueba con usuarios, un Solicitante deberá poder registrar una incidencia básica en un máximo de 2 minutos sin recibir asistencia durante la operación. |

### Usabilidad móvil

| ID | Requisito |
|----|-----------|
| RNF-06 | La solución deberá brindar una interfaz adecuada para los usuarios que registran incidencias desde dispositivos móviles. En una pantalla de 360 px de ancho o superior, el usuario deberá poder visualizar y completar el registro sin desplazamiento horizontal y acceder a las acciones necesarias para adjuntar información y confirmar la operación. |

### Rendimiento y capacidad

| ID | Requisito |
|----|-----------|
| RNF-07 | Con hasta 50 usuarios conectados simultáneamente, al menos el 95 % de las operaciones de apertura de listados, consulta de una incidencia y guardado de cambios deberá completarse en un máximo de 3 segundos, excluyendo la transferencia de archivos adjuntos. |
| RNF-08 | Con 50 usuarios simultáneos realizando operaciones habituales, el sistema deberá mantener los límites de respuesta establecidos en RNF-06 y no deberá producir errores atribuibles a falta de capacidad del servicio. |

### Compatibilidad

| ID | Requisito |
|----|-----------|
| RNF-09 | Las funciones principales de la interfaz web deberán poder ejecutarse correctamente en las dos últimas versiones estables de Chrome, Edge, Firefox y Safari, sin pérdida de funcionalidad. |

### Gestión de errores

| ID | Requisito |
|----|-----------|
| RNF-10 | Cuando una operación no pueda completarse por datos faltantes o inválidos, el mensaje de validación deberá identificar el campo o dato involucrado y el motivo del rechazo, evitando mensajes genéricos que no permitan determinar la causa. |
