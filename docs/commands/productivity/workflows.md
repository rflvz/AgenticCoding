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

# Flujos de Trabajo Rápidos

Guía profesional de flujos de trabajo comunes y rápidos para tareas frecuentes, diseñada para acelerar el desarrollo y mejorar la productividad.

## Filosofía: Flujos de Trabajo Eficientes

Los flujos de trabajo eficientes **multiplican la productividad**. Actúa como un **desarrollador profesional** que:

1. **Identifica flujos comunes** y los automatiza
2. **Crea workflows reutilizables** para tareas repetitivas
3. **Combina comandos** para procesos complejos
4. **Documenta workflows** para referencia futura
5. **Personaliza workflows** según necesidades del proyecto

## Proceso de Uso Profesional de Workflows

### Paso 1: Flujos de Trabajo Básicos (Esenciales)

**⚠️ REGLA CRÍTICA: Estos flujos son los MÁS USADOS - memorízalos primero:**

#### Crear Issue desde Error

**Problema:** Crear issues manualmente desde errores es lento y propenso a errores.

**Solución:** Automatiza la creación de issues desde errores:

```
1. Analiza el error proporcionado
2. Identifica la causa raíz
3. Crea issue en Linear:
   @linear create issue "bug: [descripción del error]" \
     --team "Engineering" \
     --labels "bug" \
     --priority "High" \
     --description "[análisis técnico completo]"
```

**Uso profesional:**
- Analiza el error completamente antes de crear issue
- Incluye contexto técnico completo en la descripción
- Prioriza según severidad del error
- Usa labels apropiados para mejor organización

#### Completar Issue Actual

**Problema:** Completar issues manualmente es lento y puede olvidar pasos.

**Solución:** Usa el proceso profesional de completar issues:

```
1. Actualiza estado:
   @linear update issue ISSUE_ID --state "Done"
2. Añade comentario:
   @linear create comment ISSUE_ID "Completado: [resumen]"
```

**⚠️ IMPORTANTE:** Para completar issues profesionalmente, usa [Completar Issues](../../../.cursor/commands/complete-issues.md) que incluye:
- Trabajo con branches y Pull Requests
- Implementación completa
- Verificación antes de revisión
- Proceso completo de revisión

**Uso profesional:**
- Usa [Completar Issues](../../../.cursor/commands/complete-issues.md) para proceso completo
- Añade comentarios con contexto técnico
- Incluye referencias a commits y PRs

#### Revisar Issues Pendientes

**Problema:** Revisar issues manualmente es lento y puede pasar por alto detalles.

**Solución:** Usa comandos para listar y revisar issues:

```bash
@linear list issues --assignee "me" --state "In Progress"
```

**⚠️ IMPORTANTE:** Para revisar issues profesionalmente, usa [Revisar Issues](../../../.cursor/commands/review-issues.md) que incluye:
- Revisión completa de código y PRs
- Verificación de criterios de aceptación
- Ejecución y verificación de tests
- Proceso completo de aprobación

**Uso profesional:**
- Usa [Revisar Issues](../../../.cursor/commands/review-issues.md) para proceso completo
- Revisa código y PRs completamente
- Verifica criterios de aceptación antes de aprobar

### Paso 2: Flujos de Trabajo con Agentes (Avanzados)

**⚠️ REGLA CRÍTICA: Los agentes permiten automatización avanzada:**

#### Crear Issue con Contexto del Agente

**Problema:** Crear issues sin contexto produce issues incompletos.

**Solución:** Usa agentes para crear issues con contexto completo:

```
Crea un issue en Linear con el título "[título]" para el equipo "[equipo]" 
basándote en el error que estamos viendo en el código.
```

**El agente:**
1. Analiza el código y el error
2. Crea issue con contexto técnico completo
3. Prioriza según severidad
4. Asigna labels apropiados

**Uso profesional:**
- Proporciona contexto completo al agente
- Revisa el issue creado antes de continuar
- Ajusta prioridad y labels si es necesario

#### Actualizar Issue desde Commit

**Problema:** Actualizar issues manualmente desde commits es lento y propenso a errores.

**Solución:** Usa agentes para actualizar issues automáticamente:

```
Basándome en este commit, actualiza el issue ISSUE_ID con un comentario 
describiendo los cambios realizados.
```

**El agente:**
1. Identifica el issue relacionado
2. Actualiza estado si corresponde
3. Añade comentario con hash del commit
4. Incluye resumen de cambios

**Uso profesional:**
- Incluye hash del commit en el comentario
- Añade resumen de cambios realizados
- Actualiza estado si corresponde

#### Buscar Issues Relacionados

**Problema:** Buscar issues manualmente es lento y puede pasar por alto issues relacionados.

**Solución:** Usa agentes para buscar issues relacionados:

```
Busca issues relacionados con "[término]" y muéstrame los que están abiertos.
```

**El agente:**
1. Busca issues similares
2. Filtra por estado abierto
3. Proporciona resumen
4. Sugiere actualizar issues existentes si aplica

**Uso profesional:**
- Usa términos específicos para búsquedas precisas
- Revisa issues encontrados antes de crear nuevos
- Actualiza issues existentes si aplica

### Paso 3: Flujos de Trabajo de Desarrollo (Profesionales)

**⚠️ REGLA CRÍTICA: Estos flujos son fundamentales para desarrollo profesional:**

#### Iniciar Trabajo en Issue

**Problema:** Iniciar trabajo sin actualizar estado dificulta tracking.

**Solución:** Usa flujo profesional para iniciar trabajo:

```
1. Obtener issue:
   @linear get issue ISSUE_ID
2. Actualizar estado:
   @linear update issue ISSUE_ID --state "In Progress"
3. Añadir comentario:
   @linear create comment ISSUE_ID "Empezando a trabajar"
```

**⚠️ IMPORTANTE:** Para iniciar trabajo profesionalmente, usa [Completar Issues](../../../.cursor/commands/complete-issues.md) que incluye:
- Análisis completo del issue
- Creación de branch y Pull Request
- Implementación completa
- Verificación antes de revisión

**Uso profesional:**
- Usa [Completar Issues](../../../.cursor/commands/complete-issues.md) para proceso completo
- Actualiza estado inmediatamente al iniciar
- Añade comentarios con contexto técnico

#### Completar Trabajo en Issue

**Problema:** Completar trabajo sin documentar dificulta tracking y revisión.

**Solución:** Usa flujo profesional para completar trabajo:

```
1. Actualizar estado:
   @linear update issue ISSUE_ID --state "Done"
2. Añadir comentario:
   @linear create comment ISSUE_ID "Completado: [resumen de cambios]"
3. Incluir referencia a commit si aplica
```

**⚠️ IMPORTANTE:** Para completar trabajo profesionalmente, usa [Completar Issues](../../../.cursor/commands/complete-issues.md) que incluye:
- Trabajo con branches y Pull Requests
- Implementación completa
- Verificación antes de revisión
- Proceso completo de revisión

**Uso profesional:**
- Usa [Completar Issues](../../../.cursor/commands/complete-issues.md) para proceso completo
- Añade comentarios con contexto técnico completo
- Incluye referencias a commits y PRs

#### Crear Issue desde Bug Encontrado

**Problema:** Crear issues manualmente desde bugs es lento y propenso a errores.

**Solución:** Usa flujo profesional para crear issues desde bugs:

```
1. Analizar el bug
2. Crear issue:
   @linear create issue "bug: [descripción]" \
     --team "Engineering" \
     --priority "[según severidad]" \
     --labels "bug,[área]"
3. Añadir descripción técnica completa
```

**Uso profesional:**
- Analiza el bug completamente antes de crear issue
- Incluye contexto técnico completo en la descripción
- Prioriza según severidad del bug
- Usa labels apropiados para mejor organización

### Paso 4: Flujos de Trabajo de Revisión (Profesionales)

**⚠️ REGLA CRÍTICA: Estos flujos son fundamentales para revisión profesional:**

#### Revisar Código y Crear Issues

**Problema:** Revisar código manualmente y crear issues es lento y propenso a errores.

**Solución:** Usa flujo profesional para revisar código y crear issues:

```
1. Revisar código proporcionado
2. Identificar problemas (bugs, vulnerabilidades, mejoras)
3. Para cada problema, crear issue:
   @linear create issue "bug: [problema]" \
     --description "[ubicación, descripción técnica, impacto]"
4. Priorizar según severidad
```

**Uso profesional:**
- Revisa código completamente antes de crear issues
- Identifica todos los problemas relevantes
- Crea issues separados para cada problema
- Prioriza según severidad

#### Verificar Fix de Bug

**Problema:** Verificar fixes manualmente es lento y puede pasar por alto problemas.

**Solución:** Usa flujo profesional para verificar fixes:

```
1. Buscar issue relacionado:
   @linear search issues "[descripción del bug]"
2. Verificar que el fix esté implementado
3. Actualizar issue:
   @linear update issue ISSUE_ID --state "Done"
   @linear create comment ISSUE_ID "Fix verificado en [commit]"
```

**Uso profesional:**
- Busca issue relacionado antes de verificar
- Verifica que el fix esté completamente implementado
- Añade comentarios con referencia al commit
- Actualiza estado apropiadamente

### Paso 5: Flujos de Trabajo de Project Management (Avanzados)

**⚠️ REGLA CRÍTICA: Estos flujos son fundamentales para gestión de proyectos:**

#### Generar Reporte de Sprint

**Problema:** Generar reportes manualmente es lento y propenso a errores.

**Solución:** Usa flujo profesional para generar reportes:

```
1. Listar issues del sprint:
   @linear list issues --team "[equipo]" --created-after "[fecha inicio]"
2. Analizar:
   - Issues completados
   - Issues en progreso
   - Issues bloqueados
3. Generar resumen con sugerencias
```

**Uso profesional:**
- Lista issues del sprint completamente
- Analiza progreso y bloqueos
- Genera resumen con sugerencias
- Documenta hallazgos importantes

#### Reasignar Tareas

**Problema:** Reasignar tareas manualmente es lento y puede pasar por alto desbalances.

**Solución:** Usa flujo profesional para reasignar tareas:

```
1. Analizar carga de trabajo:
   @linear list issues --assignee "[usuario]"
2. Identificar desbalances
3. Reasignar:
   @linear update issue ISSUE_ID --assignee "[nuevo asignado]"
```

**Uso profesional:**
- Analiza carga de trabajo completamente
- Identifica desbalances apropiadamente
- Reasigna tareas según necesidades
- Documenta razones de reasignación

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Estos workflows complementan los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Usa estos workflows al crear issues
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Aplica estos workflows al completar issues
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Usa estos workflows al revisar issues
- [Crear Proyectos](../../../.cursor/commands/create-projects.md) - Aplica estos workflows al crear proyectos
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Usa estos workflows al buscar issues

**Cuándo usar cada uno:**
- **Workflows (este documento)**: Para flujos de trabajo rápidos y comunes
- **Comandos FUNCIONALES**: Para procesos completos y trabajo profesional

## Checklist de Profesionalismo

### ⚠️ Al Usar Workflows

- [ ] ¿He identificado el workflow apropiado para mi tarea?
- [ ] ¿Estoy usando comandos FUNCIONALES cuando es necesario?
- [ ] ¿Estoy documentando decisiones importantes?
- [ ] ¿Estoy personalizando workflows según necesidades?

### Antes de Ejecutar Workflow

- [ ] ¿He revisado el workflow completamente?
- [ ] ¿Tengo el contexto necesario para ejecutar el workflow?
- [ ] ¿He verificado que el workflow es apropiado para mi tarea?

## Consejos Finales

1. **⚠️ Memoriza primero los esenciales** - Crear issue, completar issue, revisar issues son los más usados
2. **Usa comandos FUNCIONALES** - Para procesos completos y trabajo profesional
3. **Personaliza workflows** - Ajusta workflows según necesidades del proyecto
4. **Documenta personalizaciones** - Guarda workflows personalizados para referencia
5. **Combina workflows** - Los flujos complejos se simplifican con combinaciones
6. **Automatiza tareas repetitivas** - Usa agentes para automatizar workflows frecuentes

---
_Hecho por Cursor_
