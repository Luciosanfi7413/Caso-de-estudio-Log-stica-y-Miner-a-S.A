# Sistema de Gestión de Incidencias Técnicas — Grupo 1

> Materia: Diseño de Sistemas Web — Analista Funcional de Sistemas  
> Institución: Terciario Urquiza — Rosario  
> Docente: Pedernera Pablo  
> Cuatrimestre: 2.º de 2026  
> Comisión: 3.º 1.ª

## Integrantes

Ver [integrantes.md](integrantes.md).

## Descripción del proyecto

El proyecto consiste en el análisis y documentación de un sistema destinado a centralizar y organizar la gestión de incidencias técnicas de una organización.

La solución permitirá registrar, consultar, priorizar, asignar y realizar el seguimiento de las incidencias desde su creación hasta su resolución y cierre. Además, contemplará el registro de incidencias desde dispositivos móviles, la participación de especialistas externos y la conservación de un historial de acciones y soluciones anteriores.

El objetivo es mejorar la trazabilidad de las solicitudes de soporte, centralizar la información y facilitar el seguimiento del trabajo realizado por el área de Sistemas.

## Caso de estudio

El caso de estudio corresponde a **Logística y Minería S.A.**, empresa dedicada al transporte de cargas y a actividades vinculadas al sector logístico y minero.

Actualmente, los problemas técnicos son comunicados al área de Sistemas mediante distintos canales, como teléfono, WhatsApp, correo electrónico o comunicación personal. Parte de estas solicitudes se registra manualmente en planillas, lo que genera dificultades para realizar el seguimiento de los incidentes, conocer sus tiempos de atención, identificar responsables y conservar un historial completo de las soluciones aplicadas.

Además, cuando un problema requiere la intervención de un especialista externo, la comunicación se realiza principalmente mediante correo electrónico, lo que dificulta la centralización de la información y la trazabilidad de la intervención.

A partir del relevamiento realizado, se propone analizar y documentar una solución que permita centralizar el proceso de soporte técnico y gestionar las incidencias de forma organizada desde su registro hasta su resolución.

## Entregas

| Entrega | Descripción | Fecha | Estado |
|---------|-------------|-------|--------|
| EP-01 | Presentación preliminar: stakeholders y requisitos | 19/08/2026 | Completada |
| EP-02 | Entrega intermedia: historias de usuario, casos de uso, DoR, slicing, modelo ER y diseño UI | 07/10/2026 | Entregada; ajustes posteriores a la devolución |
| Final | Versión definitiva y presentación | A confirmar | Pendiente |

## Estructura del repositorio

```text
/
├── README.md
├── integrantes.md
├── RECURSOS.md
├── DOR.md
├── slicing.md
├── docs/
│   ├── requisitos.md
│   ├── historias-de-usuario.md
│   ├── casos-de-uso.md
│   ├── er-modelo.md
│   ├── diseño-ui.md
│   └── stakeholders.md
├── diagramas/
│   ├── casos-de-uso.puml
│   ├── casos-de-uso.png
│   ├── er.puml
│   ├── ER-Model.png
│   └── wireframes/
└── cuestionario/
```

## Instrucciones operativas

- Mantener `integrantes.md` actualizado con los integrantes del grupo.
- Un integrante del grupo es responsable de subir los cambios al repositorio.
- Mantener los archivos en la carpeta correspondiente según la estructura indicada.
- Los diagramas deben incluir el código fuente PlantUML (`.puml`) y su imagen de visualización (`.png`).
- Para visualizar o generar diagramas, se puede utilizar [PlantUML](https://www.plantuml.com/plantuml/uml/).