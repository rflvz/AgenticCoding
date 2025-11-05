# Flujos de Trabajo de Agentes

> **⚠️⚠️⚠️ EXPERIMENTAL ⚠️⚠️⚠️**
>
> **Este comando es EXPERIMENTAL y está en desarrollo. No confiar ciegamente.**
>
> **Para comandos FUNCIONALES, usa los comandos de Linear en `.cursor/commands/`:**
> - ✅ [Inicializar Contexto del Proyecto](../../../.cursor/commands/initialize-project-context.md)
> - ✅ [Crear Issues](../../../.cursor/commands/create-issues.md)
> - ✅ [Completar Issues](../../../.cursor/commands/complete-issues.md)
> - ✅ [Revisar Issues](../../../.cursor/commands/review-issues.md)
> - ✅ [Crear Proyectos](../../../.cursor/commands/create-projects.md)
> - ✅ [Listar y Buscar](../../../.cursor/commands/list-search.md)

Flujos de trabajo que combinan agentización con los comandos FUNCIONALES de Linear para automatizar procesos completos.

> **⚠️ IMPORTANTE:** Antes de usar un workflow, lee el [documento de contexto del proyecto](../../../docs/project-context.md) para obtener información actualizada sobre el proyecto y trabajo en Linear. Este documento es la fuente única de verdad para contexto del proyecto. Si el documento no existe, usa el [comando FUNCIONAL de inicialización](../../../.cursor/commands/initialize-project-context.md) para crearlo.

## Filosofía: Workflows Profesionales

Cuando defines un workflow, **NO** solo das instrucciones básicas. Actúa como un **arquitecto de workflows profesional** que:

1. **Analiza el contexto del proyecto** antes de definir el workflow
2. **Lee el documento de contexto** del proyecto para información actualizada
3. **Integra con comandos FUNCIONALES** de Linear
4. **Define pasos claros** y responsabilidades específicas
5. **Establece reglas profesionales** para cada paso del workflow
6. **Añade contexto del proyecto** para mejor precisión

## Proceso Profesional de Definición de Workflows

### Paso 1: Leer Contexto del Proyecto

**⚠️ REGLA CRÍTICA: SIEMPRE lee el documento de contexto del proyecto antes de definir un workflow:**

1. **Leer documento de contexto:**
   - Ubicación: `docs/project-context.md`
   - Contiene: Información del proyecto, equipo, proyectos en Linear, issues activos, convenciones

2. **Si el documento no existe:**
   - Usa el comando FUNCIONAL: `.cursor/commands/initialize-project-context.md`
   - Crea el documento de contexto antes de definir el workflow

3. **Extraer información relevante:**
   - Equipo principal y miembros
   - Proyectos activos en Linear
   - Issues activos y prioridades
   - Convenciones del proyecto (commits, branches, labels)
   - Flujos de trabajo establecidos

### Paso 2: Definir Workflow

**Define claramente el workflow y sus pasos:**

1. **Objetivo del Workflow:**
   - ¿Cuál es el objetivo del workflow? (ej: Crear issue desde error, Completar issue con commit)
   - ¿Qué resultado final debe lograr?

2. **Pasos del Workflow:**
   - ¿Qué pasos específicos debe seguir el workflow?
   - ¿Qué comandos FUNCIONALES debe usar en cada paso?
   - ¿Qué decisiones debe tomar en cada paso?

3. **Reglas del Workflow:**
   - ¿Qué reglas debe seguir el workflow?
   - ¿Cómo debe priorizar tareas?
   - ¿Qué formato debe usar para crear issues?

## Flujos de Trabajo Básicos

### Workflow: Crear Issue desde Error

**Workflow profesional para crear issues desde errores:**

```
Workflow: Crear Issue desde Error

Pasos:
1. Leer contexto del proyecto (docs/project-context.md)
2. Analizar el error proporcionado
3. Identificar la causa raíz
4. Crear issue profesionalmente usando @linear create-issues:
   - Usar comando FUNCIONAL: .cursor/commands/create-issues.md
   - Título: "bug: [descripción del error]"
   - Descripción: [análisis técnico completo]
   - Prioridad: [según severidad y contexto del proyecto]
   - Labels: "bug", [área afectada], [según docs/project-context.md]
   - Equipo: [según docs/project-context.md]
5. Añadir stack trace si está disponible
6. Incluir pasos para reproducir
```

### Workflow: Completar Issue con Commit

**Workflow profesional para completar issues desde commits:**

```
Workflow: Completar Issue desde Commit

Pasos:
1. Leer contexto del proyecto (docs/project-context.md)
2. Analizar el commit proporcionado
3. Identificar issues relacionados usando @linear list-search
4. Completar issue profesionalmente usando @linear complete-issues:
   - Usar comando FUNCIONAL: .cursor/commands/complete-issues.md
   - Actualizar estado a "In Review" o "Done" según corresponda
   - Añadir comentario con resumen de cambios
   - Incluir referencias al código modificado
5. Vincular commit al issue si es posible
```

### Workflow: Revisar Código y Crear Issues

**Workflow profesional para revisar código y crear issues:**

```
Workflow: Revisar y Crear Issues

Pasos:
1. Leer contexto del proyecto (docs/project-context.md)
2. Revisar el código proporcionado
3. Identificar problemas (bugs, vulnerabilidades, mejoras)
4. Para cada problema:
   - Crear issue profesionalmente usando @linear create-issues:
     * Usar comando FUNCIONAL: .cursor/commands/create-issues.md
     * Título: "bug: [problema]" o "feature: [mejora]"
     * Descripción: [ubicación, descripción técnica, impacto]
     * Prioridad: [según severidad y contexto del proyecto]
     * Labels: "bug", [área], [según docs/project-context.md]
     * Equipo: [según docs/project-context.md]
5. Proporcionar resumen de issues creados
```

## Flujos de Trabajo Avanzados

### Workflow: Dividir Feature en Issues

**Workflow profesional para dividir features grandes en issues manejables:**

```
Workflow: Dividir Feature

Pasos:
1. Leer contexto del proyecto (docs/project-context.md)
2. Analizar la feature propuesta
3. Crear issue padre (Epic) usando @linear create-issues:
   - Usar comando FUNCIONAL: .cursor/commands/create-issues.md
   - Título: "feature: [nombre]" o "epic: [nombre]"
   - Descripción: [visión general, requisitos, alcance]
   - Labels: "feature", "epic", [según docs/project-context.md]
4. Dividir en issues más pequeños usando @linear create-issues:
   - Diseño: "docs: Diseño de [feature]"
   - Backend: "feature: Backend - [componente]"
   - Frontend: "feature: Frontend - [componente]"
   - Tests: "chore: Tests para [feature]"
   - Documentación: "docs: Documentación de [feature]"
5. Establecer dependencias en descripciones
6. Priorizar según importancia (según docs/project-context.md)
```

### Workflow: Generar Reporte de Sprint

**Workflow profesional para generar reportes de sprint:**

```
Workflow: Reporte de Sprint

Pasos:
1. Leer contexto del proyecto (docs/project-context.md)
2. Listar issues del sprint usando @linear list-search:
   - Usar comando FUNCIONAL: .cursor/commands/list-search.md
   - Filtrar por equipo y fecha de creación
3. Analizar:
   - Issues completados
   - Issues en progreso
   - Issues bloqueados
   - Velocidad del equipo
4. Generar reporte con:
   - Resumen ejecutivo
   - Lista de issues por estado
   - Identificación de bloqueos
   - Sugerencias para próximo sprint (según docs/project-context.md)
```

## Integración con Comandos FUNCIONALES

**Integra los workflows con los comandos FUNCIONALES de Linear:**

1. **Referenciar comandos FUNCIONALES:**
   - Cuando crear issues: Usar `.cursor/commands/create-issues.md`
   - Cuando completar issues: Usar `.cursor/commands/complete-issues.md`
   - Cuando revisar issues: Usar `.cursor/commands/review-issues.md`
   - Cuando listar issues: Usar `.cursor/commands/list-search.md`

2. **Usar contexto del proyecto:**
   - Leer `docs/project-context.md` antes de ejecutar el workflow
   - Aplicar reglas y convenciones definidas
   - Seguir el flujo de trabajo profesional

## Checklist de Profesionalismo

### ⚠️ Antes de Definir un Workflow

- [ ] ¿He leído el documento de contexto del proyecto (`docs/project-context.md`)?
- [ ] ¿He identificado los pasos específicos del workflow?
- [ ] ¿He definido las reglas profesionales para cada paso?
- [ ] ¿He integrado con comandos FUNCIONALES de Linear?

### Al Definir el Workflow

- [ ] ¿El workflow usa comandos FUNCIONALES de Linear?
- [ ] ¿Las reglas siguen las convenciones del proyecto?
- [ ] ¿El workflow usa el contexto del proyecto en sus decisiones?
- [ ] ¿El workflow puede ejecutarse profesionalmente?

### Después de Definir el Workflow

- [ ] ¿El workflow puede crear issues usando el comando FUNCIONAL create-issues.md?
- [ ] ¿El workflow aplica las reglas definidas correctamente?
- [ ] ¿El workflow sigue las convenciones del proyecto?
- [ ] ¿El workflow usa el contexto del proyecto en cada paso?

## Consejos Finales

1. **⚠️ SIEMPRE lee el documento de contexto del proyecto** antes de definir o ejecutar un workflow
2. **Usa comandos FUNCIONALES de Linear** en lugar de comandos experimentales
3. **Define workflows claros** con pasos específicos
4. **Establece reglas profesionales** para cada paso del workflow
5. **Integra con comandos FUNCIONALES** para máxima efectividad
6. **Añade contexto del proyecto** para mejor precisión
7. **Actualiza workflows** cuando cambie el proyecto

## Referencias

- [Documento de Contexto del Proyecto](../../../docs/project-context.md) - Fuente única de verdad para contexto del proyecto
- [Comandos FUNCIONALES de Linear](../../../.cursor/commands/) - Comandos completamente funcionales y probados
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Crear issues profesionalmente
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Completar issues profesionalmente
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Revisar issues profesionalmente
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Listar y buscar issues

---