---
title: Guía para Listado y Recomendación de Issues en Linear
tipo_tarea: workflow/agente
---

# Objetivo y Pasos Obligatorios

Analizar, priorizar y recomendar issues de Linear mediante análisis estratégico del estado del proyecto, verificación de dependencias y evaluación de prioridades.

## Pasos Obligatorios

1. Verificar existencia de `../../project-context.md`. IF NO existe → ejecutar `./initialize-project-context.md`
2. Inferir proyecto si no especificado: consultar `list_projects`, analizar contexto semántico, correlacionar términos clave
3. Analizar estado del proyecto: listar issues por estado, mapear dependencias, evaluar prioridades
4. Buscar issues candidatas usando `list_issues` con filtros apropiados
5. Para cada candidata: obtener detalles con `get_issue`, verificar dependencias, evaluar viabilidad
6. Calcular prioridad estratégica usando fórmula: `(5 - Prioridad_Base) + (Bloquea_Otros * 3) + (Critico_Produccion * 4) + (Deadline_Proximo * 2)`
7. Generar recomendaciones con estructura definida
8. IF confianza ≥ 9/10 AND todas las condiciones cumplen → actualizar estado a "Todo" y documentar con comentario

VERIFICAR: ¿Se completaron todos los pasos anteriores? [SI/NO]
- IF NO → Repetir desde el paso faltante
- IF SI → Continuar

## Restricciones Absolutas

- NO mover issues a "Todo" sin confianza ≥ 9/10
- NO recomendar issues con dependencias incompletas
- NO actualizar estados sin verificación exhaustiva de dependencias
- NO omitir documentación de acciones realizadas
- NO mostrar resultados sin análisis estratégico previo
- SI issue tiene `parentId` → verificar estado del padre es "Done"
- SI descripción menciona dependencias → verificar cada una individualmente
- SI confianza < 9/10 → solo recomendar, NO actualizar

## Criterios para Mover a "Todo"

Condiciones REQUERIDAS (todas deben cumplirse):
- Todas las dependencias tienen estado "Done"
- Issue tiene definición clara con criterios de aceptación explícitos
- No existen bloqueos identificados
- Prioridad es Urgent (1), High (2) o Normal (3)
- Información disponible es suficiente para iniciar
- Nivel de confianza ≥ 9/10

Condiciones que IMPIDEN la actualización:
- Dependencias críticas sin completar
- Definición insuficiente o ambigua
- Bloqueos sin resolver
- Estado "Canceled" o "Duplicate"
- Prioridad Low (4) sin justificación especial

---

# Proceso de Análisis

## Análisis del Estado del Proyecto

### Paso 1: Obtener Visión General

VERIFICAR: ¿Se listaron issues agrupados por estado? [SI/NO]
- IF NO → Ejecutar `list_issues` agrupando por estado
- IF SI → Continuar

Acciones:
- Listar issues agrupados por estado
- Identificar acumulaciones que indiquen cuellos de botella
- Detectar issues en estados intermedios por períodos prolongados

### Paso 2: Mapear Dependencias

VERIFICAR: ¿Se construyó el grafo de dependencias? [SI/NO]
- IF NO → Identificar issues padre, verificar relaciones de bloqueo, determinar dependencias satisfechas
- IF SI → Continuar

Acciones:
- Identificar issues padre y sub-issues usando `parentId`
- Verificar relaciones de bloqueo entre issues
- Determinar cuáles issues tienen todas sus dependencias satisfechas

### Paso 3: Evaluar Prioridades

Criterios de evaluación:
- Prioridad asignada: Urgent (1), High (2), Normal (3), Low (4)
- Impacto en bloqueo: Issues que bloquean a múltiples issues tienen mayor peso
- Proximidad de deadline: Issues con fechas límite cercanas requieren atención inmediata
- Criticidad para producción: Issues que afectan sistemas en producción tienen precedencia

## Búsqueda y Filtrado Estratégico

### Categorías de Búsqueda

Categoría A: Issues Listas para Iniciar
- Estado: "Backlog" o "Todo"
- Dependencias: Sin dependencias bloqueantes o todas satisfechas
- Prioridad: Urgent, High o Normal según contexto
- Bloqueos: Sin impedimentos evidentes

Categoría B: Issues Bloqueadoras
- Característica: Bloquean el progreso de otros issues
- Estado: "Backlog" o "Todo" (pendientes de inicio)
- Impacto: Críticas para el flujo del proyecto

Categoría C: Issues que Requieren Atención
- Estado: "In Progress" por período prolongado
- Indicador: Posible necesidad de asistencia o desbloqueo

Categoría D: Issues en Revisión
- Estado: "In Review"
- Acción potencial: Acelerar ciclo de aprobación

### Análisis Profundo de Issues Candidatas

Para cada issue candidata:

Paso 3.1: Obtener Información Completa
- Herramienta: `get_issue` con parámetro `id`
- Datos a revisar: título, descripción, estado, prioridad, labels, asignación, relaciones de dependencia

Paso 3.2: Verificar Dependencias

VERIFICAR: ¿Todas las dependencias están completadas? [SI/NO]
- IF NO → NO recomendar, documentar dependencias pendientes
- IF SI → Continuar

Proceso:
- IF issue tiene `parentId` → consultar estado del issue padre
- IF descripción referencia dependencias → verificar estado de cada issue mencionado
- Utilizar `list_issues` con `parentId` para obtener sub-issues relacionadas
- Confirmar que dependencias críticas tienen estado "Done"

Paso 3.3: Evaluar Viabilidad

Lista de verificación:
- [ ] Todas las dependencias están completadas
- [ ] El issue tiene definición clara y criterios de aceptación
- [ ] Existe información suficiente para iniciar el trabajo
- [ ] No existen bloqueos externos identificados

## Generación de Recomendaciones

### Estructura de Recomendación Individual

Para cada issue recomendada:

```
## [ID-ISSUE]: [Título del Issue]

Prioridad Recomendada: [Alta/Media/Baja]
Justificacion: [Explicación concisa del por qué esta issue es importante ahora]

Estado Actual: [Estado]
Acción Sugerida: [Mover a Todo / Iniciar trabajo / Continuar trabajo / Revisar]

Dependencias:
- [COMPLETADA] [ID-DEP-1]: [Descripción breve]
- [EN PROGRESO] [ID-DEP-2]: [Descripción breve] - Esperando completar
- [PENDIENTE] [ID-DEP-3]: [Descripción breve] - Bloqueante

Contexto Adicional:
- [Información relevante sobre el issue]
- [Razón por la cual es buen momento para abordarlo]
```

### Formato de Presentación

```
# Recomendaciones de Issues

## Resumen del Estado del Proyecto

| Métrica | Valor |
|---------|-------|
| Total de issues | [N] |
| En Backlog | [N] |
| En Todo | [N] |
| In Progress | [N] |
| In Review | [N] |
| Done | [N] |

## Issues Recomendadas (Prioridad Alta)

### 1. [ID-ISSUE]: [Título]

Prioridad: Alta
Estado: Backlog -> Recomendado mover a Todo
Justificación: [Explicación]
Acción: [Estado de la acción: Movida a Todo / Pendiente de confirmación]

## Issues que Requieren Atención

### [ID-ISSUE]: [Título]

Estado: [Estado actual] (desde hace [N] días)
Motivo de atención: [Explicación]
Acción sugerida: [Recomendación]
```

## Actualización de Estado

### Procedimiento de Actualización

Paso 5.1: Verificar Estado Actual
- Herramienta: `get_issue` con `id` del issue
- Confirmar: Estado actual es "Backlog" o equivalente

VERIFICAR: ¿El estado actual es "Backlog"? [SI/NO]
- IF NO → NO actualizar, documentar razón
- IF SI → Continuar

Paso 5.2: Verificación Final de Dependencias
- IF tiene `parentId` → verificar estado del padre es "Done" o no aplica
- IF menciona dependencias en descripción → verificar cada una individualmente

VERIFICAR: ¿Todas las dependencias tienen estado "Done"? [SI/NO]
- IF NO → NO actualizar, documentar dependencias pendientes
- IF SI → Continuar

Paso 5.3: Ejecutar Actualización

VERIFICAR: ¿Nivel de confianza ≥ 9/10? [SI/NO]
- IF NO → NO actualizar, solo recomendar
- IF SI → Continuar

- Herramienta: `update_issue`
- Parámetros: `id` del issue, `state: "Todo"`
- Condición: Solo si se cumplen todos los criterios anteriores

Paso 5.4: Documentar la Acción
- Herramienta: `create_comment`
- Parámetros: `issueId` y contenido del comentario

Formato del comentario:
```
## Actualización de Estado

Acción realizada: Issue movida a "Todo"

Justificación:
- [Razón principal de la actualización]
- [Estado de dependencias verificado]

Recomendación:
- [Siguiente paso sugerido]

---
_Hecho por Cursor_
```

---

# Referencia de Herramientas

## Listar Issues

Herramienta: `list_issues`

Parámetros disponibles:
- `team`: Nombre o ID del equipo
- `state`: Estado del issue ("Backlog", "Todo", "In Progress", "In Review", "Done")
- `assignee`: Usuario asignado (ID, nombre, email, o "me" para el usuario actual)
- `priority`: Nivel de prioridad (1=Urgent, 2=High, 3=Normal, 4=Low)
- `label`: Nombre o ID de la etiqueta
- `project`: Nombre o ID del proyecto (inferir si no se especifica)
- `parentId`: ID del issue padre para obtener sub-issues
- `query`: Texto de búsqueda en título o descripción

Ejemplos:
```
list_issues(team: "[EQUIPO]", state: "Todo", priority: 2)
list_issues(team: "[EQUIPO]", state: "Backlog", priority: 1)
list_issues(team: "[EQUIPO]", parentId: "[ID-EPIC]")
list_issues(query: "[TERMINO-BUSQUEDA]", team: "[EQUIPO]")
```

## Obtener Issue Detallado

Herramienta: `get_issue`

Parámetros:
- `id` (requerido): ID del issue

Retorna: Información completa incluyendo título, descripción, estado, prioridad, labels, asignación, parentId, y relaciones de dependencia.

## Actualizar Issue

Herramienta: `update_issue`

Parámetros:
- `id` (requerido): ID del issue
- `state` (opcional): Nuevo estado
- `priority` (opcional): Nueva prioridad
- `assignee` (opcional): Nueva asignación

## Crear Comentario

Herramienta: `create_comment`

Parámetros:
- `issueId` (requerido): ID del issue
- `body` (requerido): Contenido en formato Markdown

Recordatorio: Incluir siempre `---\n_Hecho por Cursor_` al final.

## Listar Estados Disponibles

Herramienta: `list_issue_statuses`

Parámetros:
- `team` (requerido): Nombre o ID del equipo

## Listar Proyectos

Herramienta: `list_projects`

Usar para inferir proyecto cuando el usuario no lo especifica.

---

# Checklist de Verificación Final

## Antes de Recomendar

VERIFICAR cada item:
- [ ] Se analizó el estado completo del proyecto
- [ ] Se identificaron dependencias correctamente
- [ ] Se verificó el estado de todas las dependencias
- [ ] Se evaluó la prioridad estratégica de cada issue

## Antes de Actualizar Estado

VERIFICAR cada item:
- [ ] Nivel de confianza es 9 o superior en una escala del 1 al 10
- [ ] Se verificaron dependencias una última vez
- [ ] Todas las dependencias tienen estado "Done"
- [ ] El issue tiene definición clara y completa
- [ ] No existen bloqueos sin resolver
- [ ] La prioridad justifica la actualización inmediata
- [ ] Se documentará la acción con comentario apropiado
- [ ] Se incluirá la firma "_Hecho por Cursor_" en el comentario

## Manejo de Errores

IF verificación falla en cualquier paso:
- Documentar el motivo del fallo
- NO proceder con actualización si confianza < 9/10
- Solicitar clarificación si información es insuficiente
- IF dependencias incompletas → listar dependencias pendientes y sus estados

## Repetición de Pasos Críticos

Recordatorio de pasos críticos:
1. Verificar dependencias antes de recomendar
2. Calcular confianza antes de actualizar (debe ser ≥ 9/10)
3. Documentar todas las acciones con comentarios
4. Incluir firma "_Hecho por Cursor_" en comentarios
