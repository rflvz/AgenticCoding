# Contexto del Proyecto AgenticCoding

**Última actualización:** 2025-11-06  
**Versión:** 1.1

> **⚠️ IMPORTANTE:** Este documento es la fuente única de verdad para todos los comandos y agentes. Todos los comandos y agentes deben leer este documento para obtener contexto del proyecto y trabajo en Linear.

## Información del Proyecto

### Descripción General

**AgenticCoding** es una guía de referencia rápida para agentización profesional de código usando Cursor, incluyendo configuración de MCPs, comandos avanzados, técnicas de contextualización de agentes y mejores prácticas.

### Objetivos del Proyecto

- Documentar técnicas avanzadas de agentización con Cursor
- Proporcionar comandos y workflows para mejorar productividad
- Integrar Linear para gestión de tareas y proyectos
- Crear agentes especializados para diferentes contextos
- Establecer mejores prácticas y patrones de agentización

### Estructura del Proyecto

```
AgenticCoding/
├── docs/
│   ├── commands/          # Documentación de comandos
│   ├── agents/            # Documentación de agentes especializados
│   ├── setup/             # Configuración de MCPs
│   ├── workflows/         # Workflows y procesos
│   ├── agentization/      # Técnicas avanzadas de agentización
│   └── project-context.md # Este documento (contexto centralizado)
├── examples/              # Ejemplos y configuraciones
└── README.md              # Documentación principal
```

### Tecnologías y Herramientas

- **Editor:** Cursor
- **Control de Versiones:** Git/GitHub
- **Gestión de Proyectos:** Linear
- **MCPs:** Linear, GitHub, Slack/Discord
- **Documentación:** Markdown

### Estado Actual del Proyecto

- **Fase:** Desarrollo activo
- **Enfoque:** Documentación y mejora de comandos
- **Prioridad:** Alta
- **Branch Actual:** `feature/DAW-27-mejorar-comandos-experimentales-productivity`

## Información de Linear

### Equipo Principal

- **Equipo:** DAW
- **ID del Equipo:** `1edf0b57-2c5e-46e4-8d64-29b40a9a2905`
- **URL:** https://linear.app/clasificadoria/team/DAW

### Proyectos Activos

#### 1. Agentización con Linear en Cursor

- **ID:** `4e316246-3b26-437d-a4d3-bc2343f26e6f`
- **Prioridad:** High
- **Estado:** In Progress
- **Lead:** Rafa
- **Descripción:** Documentación y guías sobre la importancia y utilidades de agentizar con Linear en Cursor
- **Objetivo:** Crear documentación profesional y completa que explique por qué es fundamental aprender a agentizar con Linear en Cursor, todas las utilidades prácticas de esta integración, y mejoras específicas para el programa AgenticCoding
- **URL:** https://linear.app/clasificadoria/project/agentizacion-con-linear-en-cursor-cd1ee84c469f

### Issues Activos (En Progreso)
### Issues Completados Recientemente

#### DAW-21: Acceso centralizado a documento de contexto

- **ID:** `89bd872e-5af4-4017-a69e-8080ae42a5b8`
- **Prioridad:** High
- **Estado:** Done ✅
- **Asignado:** Rafa
- **Proyecto:** Agentización con Linear en Cursor
- **Labels:** workflow, cursor, agentization, docs
- **Branch:** `feature/DAW-21-acceso-documento-contexto`
- **Objetivo:** Establecer un sistema centralizado donde todos los comandos y agentes accedan a un documento de referencia que contenga información del proyecto actual y del trabajo planificado en Linear.
- **URL:** https://linear.app/clasificadoria/issue/DAW-21/feature-acceso-centralizado-a-documento-de-contexto-del-proyecto-y

#### DAW-12: Mejora de productividad y eficiencia en desarrollo

- **ID:** `4ebb43ad-fb17-49a1-8c21-f018fc08be97`
- **Prioridad:** High
- **Estado:** Done ✅
- **Asignado:** Rafa
- **Proyecto:** Agentización con Linear en Cursor
- **Labels:** productivity, agentization, docs
- **Branch:** `feature/DAW-12-productividad-eficiencia`
- **Objetivo:** Documentar las mejoras concretas de productividad que se obtienen al agentizar con Linear en Cursor, con métricas y casos de uso específicos.
- **URL:** https://linear.app/clasificadoria/issue/DAW-12/docs-mejora-de-productividad-y-eficiencia-en-desarrollo

### Prioridades y Focos

- **Alta Prioridad:** 
  - Proyecto: Agentización con Linear en Cursor (In Progress)
  - Issues completados: DAW-21 ✅, DAW-12 ✅

- **Prioridad Media (En Progreso):**
  - DAW-40: Epic: Parte 3 - Informe Final con Evidencias
  - DAW-42: Documentar resultados del perfilado con capturas
  - Proyecto: Perfilado de Programas en Java

- **Prioridad Baja:**
  - DAW-44: Crear comparativa con versión mejorada (opcional)

- **Completado:**
  - Entrega modelos físicos ✅

## Convenciones y Estándares

### Convenciones de Commits

- Usar formato: `type: descripción` (ej: `feat:`, `fix:`, `docs:`)
- Incluir referencia al issue cuando aplique: `Closes #DAW-21`
- Describir cambios de forma clara y concisa

### Convenciones de Branches

- Formato: `feature/DAW-XX-descripcion-corta` o `fix/DAW-XX-descripcion-bug`
- Siempre trabajar en branches, nunca directamente en `main`
- Crear Pull Requests para revisión

### Convenciones de Documentación

- Usar Markdown para toda la documentación
- Estructura clara con encabezados y secciones
- Incluir ejemplos de uso cuando sea relevante
- Referenciar otros documentos relacionados

### Convenciones de Issues en Linear

- Títulos descriptivos con tipo: `type: descripción` (ej: `feature:`, `docs:`, `fix:`)
- Descripciones completas con objetivos, contexto, requisitos y criterios de aceptación
- Usar labels apropiados: `workflow`, `cursor`, `agentization`, `docs`, `productivity`
- Asignar al equipo DAW
- Vincular con proyecto "Agentización con Linear en Cursor" cuando aplique

## Decisiones Arquitectónicas

### Decisión: Documento Centralizado de Contexto

**Fecha:** 2025-11-05  
**Decisión:** Crear `docs/project-context.md` como fuente única de verdad para contexto del proyecto y Linear.  
**Razón:** Evitar redundancia y asegurar coherencia entre comandos y agentes.  
**Impacto:** Todos los comandos y agentes deben leer este documento antes de trabajar.

### Decisión: Estructura de Documentación

**Fecha:** 2025-11-05  
**Decisión:** Organizar documentación en carpetas temáticas (`commands/`, `agents/`, `setup/`, etc.).  
**Razón:** Facilitar navegación y mantenimiento.  
**Impacto:** Nueva documentación debe seguir esta estructura.

## Bloqueos y Dependencias

### Bloqueos Actuales

Ninguno identificado actualmente.

### Dependencias Entre Issues

- **DAW-40** (Epic) contiene:
  - DAW-42: Documentar resultados del perfilado con capturas
  - DAW-44: Crear comparativa con versión mejorada (opcional)
- **DAW-40** requiere: Epic: Parte 2 - Perfilado con NetBeans (DAW-35)

## Próximos Pasos

1. Completar DAW-40: Epic: Parte 3 - Informe Final con Evidencias
   - DAW-42: Documentar resultados del perfilado con capturas
   - DAW-44: Crear comparativa con versión mejorada (opcional)
2. Continuar con proyecto: Agentización con Linear en Cursor
3. Actualizar documentación de comandos para referenciar este documento
4. Crear workflows de actualización automática del documento de contexto

## Cómo Usar Este Documento

### Para Comandos

Todos los comandos deben:
1. Leer este documento antes de ejecutar cualquier acción
2. Usar la información de Linear para contextualizar tareas
3. Actualizar este documento cuando se hagan cambios relevantes
4. Referenciar este documento en la documentación de comandos

### Para Agentes

Todos los agentes deben:
1. Leer este documento al iniciar cualquier tarea
2. Usar la información del proyecto para contextualizar trabajo
3. Consultar issues activos antes de crear nuevos issues
4. Actualizar este documento cuando se completen tareas importantes

### Para Actualizar el Documento

Ver: `docs/project-context-update-guide.md` para instrucciones detalladas sobre cómo actualizar este documento.

## Referencias

- [README Principal](./README.md)
- [Comandos de Linear](./commands/linear/)
- [Contexto Compartido](./agentization/shared-context.md)
- [Gestión de Memoria](./agentization/memory-management.md)

---

**Nota:** Este documento debe actualizarse regularmente para reflejar el estado actual del proyecto y trabajo en Linear. Ver guía de actualización para más detalles.

