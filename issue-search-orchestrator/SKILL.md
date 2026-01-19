---
name: issue-search-orchestrator
description: Orquesta un workflow de búsqueda/listado de issues en Linear y, tras confirmación del usuario, coordina su completado usando subagentes issue-completer. Usar cuando el usuario pida listar/buscar issues o completar varias issues con confirmación previa.
---

# Issue Search Orchestrator

## Propósito
Guiar un flujo en dos etapas: primero listar/buscar y recomendar issues con análisis profesional; luego, solo tras confirmación explícita del usuario, completar issues con subagentes `issue-completer`.

## Quick Start
1. Ejecuta el flujo de list/search con análisis y recomendaciones.
2. Presenta recomendaciones y pide confirmación explícita.
3. Con confirmación, coordina completado con subagentes `issue-completer`.
4. Reporta resultados consolidados y no marques "Done" sin aprobación.

## Flujo principal
### Etapa 1: List/Search y Recomendación
Antes de recomendar:
- Leer `project-context.md` del proyecto si existe.
- Intuir proyecto si el usuario no lo especifica.
- Analizar dependencias, prioridades y bloqueos.

Herramientas:
- `list_issues` con filtros por estado, prioridad, label, parentId.
- `search_issues` para texto.
- `get_issue` para detalles y dependencias.

Generar recomendaciones estructuradas y, si aplica, mover a "Todo" solo con alta confianza (95%+), documentando con comentario y firma obligatoria.

### Etapa 2: Confirmación del usuario
Regla clave:
```
NO completar issues sin confirmación explícita del usuario.
```

Presenta la lista de issues recomendadas y pregunta qué issues completar.

### Etapa 3: Completado con subagentes
Decisión de arquitectura:
```
IF cantidad_de_issues > 1 THEN
  FOR issue IN issues_confirmadas:
    subagente.issue-completer(issue)
  END FOR
  consolidar_resultados()
ELSE
  subagente.issue-completer(issue)
```

El subagente `issue-completer` debe ejecutar su workflow completo, incluyendo:
- `update_issue(state: "In Progress")`
- Implementación
- PR si hay Git
- `update_issue(state: "In Review")`
- `create_comment` con firma `---\n_Hecho por Cursor_`
- Nunca marcar "Done" sin aprobación del usuario

## Formato de salida: Recomendaciones
```
# Recomendaciones de Issues para Trabajar

## Resumen del Estado del Proyecto
- Total de issues: [N]
- Backlog: [N]
- Todo: [N]
- In Progress: [N]
- In Review: [N]
- Done: [N]

## Issues Recomendadas
1) ISSUE-123: [Título]
   - Prioridad: Alta/Media/Baja
   - Estado: [Estado]
   - Razón: [Motivo]
   - Acción sugerida: [Mover a Todo / Comenzar / Revisar]
```

## Formato de salida: Resultados de completado
```
Issue: [ID] - [Título]

Progreso:
□ In Progress: ✓
□ Implementación: ✓
□ Tests: ✓ (X pasaron, Y fallaron)
□ PR creado: ✓ [URL]
□ In Review: ✓
□ Comentario: ✓

Cambios principales:
- [archivo/área]: [cambio]

Pendientes/Riesgos:
- [si aplica]
```

## Checklist final
```
□ ¿Se realizó list/search con análisis profesional?
□ ¿Se pidió confirmación explícita del usuario?
□ ¿Se usó subagente issue-completer por issue?
□ ¿Issue en "In Review" (si completado)?
□ ¿Comentario con firma creado?
□ ¿NO marcado "Done"?
```

## Referencias
- `commands/list-search.md`
- `agents/issue-completer.md`
