# Listar y Buscar Issues como Project Manager Profesional

Guía profesional para listar, buscar y recomendar issues en Linear actuando como un project manager/programador experto.

## Filosofía: Actuar como Experto

Cuando listes y busques issues, **NO** solo uses el MCP de Linear para mostrar resultados. Actúa como un **project manager profesional** que:

1. **Analiza profundamente** el estado del proyecto
2. **Prioriza estratégicamente** según dependencias y contexto
3. **Recomienda inteligentemente** qué issues hacer primero
4. **Gestiona el flujo de trabajo** moviendo issues a "Todo" cuando sea apropiado
5. **Identifica bloqueadores** y dependencias críticas
6. **⚠️ Intuye el proyecto** si el usuario no lo especifica - busca proyectos relacionados en Linear

## Proceso de Análisis y Recomendación Profesional

### Paso 1: Analizar el Estado del Proyecto

**ANTES de recomendar issues:**

1. **Obtener visión general del proyecto**
   - Listar issues por estado para entender distribución del trabajo
   - Identificar cuellos de botella
   - Detectar issues bloqueados o bloqueadores

2. **Analizar dependencias**
   - Identificar issues padre y sus sub-issues
   - Verificar qué issues dependen de otros
   - Detectar issues listos para comenzar (dependencias completadas)

3. **Evaluar prioridades**
   - Issues con prioridad Urgent o High
   - Issues que bloquean a otros
   - Issues con deadlines próximos
   - Issues críticos para producción

4. **Intuir proyecto si no se especifica:**
   - **⚠️ Si el usuario no especifica el proyecto, debes intuirlo**
   - Busca proyectos relacionados usando `list_projects`
   - Analiza el contexto de la búsqueda para identificar proyectos relevantes
   - Si hay proyectos activos relacionados, úsalos como filtro

5. **Aclarar contexto con el usuario si es necesario**
   - ¿En qué área prefieres trabajar? (frontend, backend, api, etc.)
   - ¿Qué tipo de trabajo prefieres? (features, bugs, refactor, docs)
   - ¿Hay algún deadline o prioridad específica?
   - ¿En qué proyecto específico? (si no está claro, intuir basándose en el contexto)

### Paso 2: Búsqueda y Filtrado Estratégico

**Buscar issues de manera inteligente:**

#### Criterios de Búsqueda Recomendados

**1. Issues Listas para Comenzar:**
- Estado: `"Backlog"` o `"Todo"`
- Sin dependencias bloqueantes O dependencias completadas
- Prioridad: Urgent, High, o Normal según contexto
- Sin bloqueos evidentes

**2. Issues Bloqueadores:**
- Prioridad alta que bloquean a otros issues
- Estado: `"Backlog"` o `"Todo"` (aún no iniciadas)
- Críticas para el flujo del proyecto

**3. Issues en Progreso que Necesitan Atención:**
- Estado: `"In Progress"` por mucho tiempo
- Podrían necesitar ayuda o revisión

**4. Issues en Revisión:**
- Estado: `"In Review"` esperando aprobación
- Podrían necesitar revisión urgente

#### Herramientas de Búsqueda

**Usa `list_issues` con múltiples filtros:**

```python
# Issues listas para comenzar
list_issues(team: "DAW", state: "Todo", priority: 2)

# Issues en Backlog con prioridad alta
list_issues(team: "DAW", state: "Backlog", priority: 1)

# Issues de un epic específico
list_issues(team: "DAW", parentId: "ISSUE-EPIC-123")

# Issues por área (usando labels)
list_issues(team: "DAW", state: "Todo", label: "frontend")
```

**Usa `search_issues` para búsqueda por texto:**

```python
search_issues(query: "autenticación", team: "DAW")
```

### Paso 3: Análisis Profundo de Issues Candidatas

**Para cada issue candidata:**

1. **Obtener detalles completos**
   - Usa: `get_issue` con `id` del issue
   - Revisa: título, descripción, estado, prioridad, labels, asignado, dependencias

2. **Verificar dependencias**
   - Si el issue tiene `parentId`: verificar estado del issue padre
   - Si la descripción menciona dependencias: verificar estado de issues dependientes
   - Usa: `list_issues` con `parentId` para ver sub-issues
   - Usa: `get_issue` para verificar estado de issues dependientes mencionados

3. **Evaluar viabilidad**
   - ¿Todas las dependencias están completadas? (`state: "Done"`)
   - ¿El issue está claramente definido?
   - ¿Hay información suficiente para comenzar?
   - ¿Hay bloqueos evidentes?

4. **Calcular prioridad estratégica**
   - Prioridad del issue (Urgent=1, High=2, Normal=3, Low=4)
   - ¿Bloquea a otros issues? (mayor prioridad)
   - ¿Es crítico para producción? (mayor prioridad)
   - ¿Tiene deadline próximo? (mayor prioridad)

### Paso 4: Generar Recomendaciones Inteligentes

**Crear recomendaciones estructuradas:**

#### Estructura de Recomendación

```markdown
## ISSUE-123: [Título del Issue]

**Prioridad Recomendada:** Alta/Media/Baja
**Razón:** [Por qué esta issue es importante ahora]

**Estado Actual:** Backlog/Todo/In Progress
**Acción Sugerida:** Mover a Todo / Comenzar trabajo / Continuar trabajo

**Dependencias:**
- ✅ ISSUE-120 (Completada) - Diseño arquitectónico
- ⏳ ISSUE-121 (In Progress) - Esperando completar

**Contexto:**
- [Información relevante sobre el issue]
- [Por qué es buen momento para hacerlo]
```

#### Criterios de Recomendación

**Recomendar Mover a "Todo" cuando (Alta Confianza 95%+):**
- ✅ Todas las dependencias están completadas
- ✅ Issue claramente definido con criterios de aceptación
- ✅ Sin bloqueos evidentes
- ✅ Prioridad alta o crítica
- ✅ Información suficiente para comenzar

**NO recomendar mover a "Todo" cuando:**
- ❌ Dependencias críticas no completadas
- ❌ Issue con información insuficiente
- ❌ Bloqueos evidentes sin resolver
- ❌ Issue cancelado o duplicado

### Paso 5: Actualizar Status a "Todo" (Alta Confianza)

**Solo actualizar cuando estés muy seguro (95%+ confianza):**

#### Checklist Antes de Actualizar

- [ ] ¿He verificado todas las dependencias están "Done"?
- [ ] ¿El issue está claramente definido?
- [ ] ¿No hay bloqueos evidentes?
- [ ] ¿La prioridad justifica moverlo ahora?
- [ ] ¿El issue no está asignado a otra persona con trabajo activo?

#### Proceso de Actualización

1. **Verificar estado actual**
   - Usa: `get_issue` con `id` del issue
   - Confirma que el estado actual es `"Backlog"` o similar

2. **Verificar dependencias una última vez**
   - Si tiene `parentId`: verificar estado del padre
   - Si menciona dependencias en descripción: verificar cada una

3. **Actualizar estado**
   - Usa: `update_issue` con `id` del issue y `state: "Todo"`
   - Solo si cumple todos los criterios de alta confianza

4. **Documentar la acción**
   - Usa: `create_comment` con `issueId` y mensaje profesional
   - Incluye: razón de la actualización, contexto, recomendación
   - **IMPORTANTE**: Siempre añade al final: `---\n_Hecho por Cursor_`

### Paso 6: Presentar Recomendaciones al Usuario

**Formato profesional de presentación:**

```markdown
# Recomendaciones de Issues para Trabajar

## 📊 Resumen del Estado del Proyecto

- **Total de issues:** 45
- **En Backlog:** 12
- **En Todo:** 8
- **In Progress:** 5
- **In Review:** 3
- **Done:** 17

## 🎯 Issues Recomendadas (Alta Prioridad)

### 1. ISSUE-123: Implementar endpoint de autenticación
**Prioridad:** Alta
**Estado:** Backlog → **Recomendado mover a Todo**
**Razón:** Todas las dependencias completadas, bloquea 2 issues críticas
**Acción:** ✅ Movida a Todo

## ⚠️ Issues que Requieren Atención

### ISSUE-125: Refactorizar middleware
**Estado:** In Progress (desde hace 5 días)
**Razón:** Podría estar bloqueada o necesitar ayuda
**Acción:** ⚠️ Revisar estado y ofrecer asistencia
```

## Herramientas de Referencia

### Listar Issues

**Herramienta:** `list_issues`

**Parámetros útiles:**
- `team`: Filtrar por equipo
- `state`: Filtrar por estado (`"Backlog"`, `"Todo"`, `"In Progress"`, etc.)
- `assignee`: Filtrar por asignado (usa `"me"` para tus issues)
- `priority`: Filtrar por prioridad (1=Urgent, 2=High, 3=Normal, 4=Low)
- `label`: Filtrar por label
- `project`: Filtrar por proyecto - **⚠️ INTUYE el proyecto si el usuario no lo especifica**
- `parentId`: Filtrar por issue padre (para obtener sub-issues)

### Buscar Issues

**Herramienta:** `search_issues` o `list_issues` con filtros

**Parámetros:**
- `query`: Texto de búsqueda
- `team`: Filtrar por equipo
- `timeMin`, `timeMax`: Fechas

### Obtener Issue Detallado

**Herramienta:** `get_issue`

**Parámetros:**
- `id` (requerido): ID del issue

**Retorna:** Información completa del issue incluyendo título, descripción, estado, prioridad, labels, asignado, parentId, dependencias, etc.

### Actualizar Issue

**Herramienta:** `update_issue`

**Parámetros útiles:**
- `id` (requerido): ID del issue a actualizar
- `state` (opcional): Nuevo estado (`"Todo"`, `"In Progress"`, etc.)
- `priority` (opcional): Nueva prioridad
- `assignee` (opcional): Nuevo asignado

### Añadir Comentario

**Herramienta:** `create_comment`

**Parámetros:**
- `issueId` (requerido): ID del issue
- `body` (requerido): Contenido del comentario (soporta Markdown)

**IMPORTANTE:** Siempre incluye al final: `---\n_Hecho por Cursor_`

### Listar Status Disponibles

**Herramienta:** `list_issue_statuses`

**Parámetros:**
- `team` (requerido): Nombre o ID del equipo

## Checklist de Profesionalismo

Antes de recomendar o mover un issue a "Todo", verifica:

### Análisis
- [ ] ¿He analizado el estado completo del proyecto?
- [ ] ¿He identificado dependencias correctamente?
- [ ] ¿He verificado el estado de todas las dependencias?
- [ ] ¿He evaluado la prioridad estratégica?

### Recomendación
- [ ] ¿El issue está claramente definido?
- [ ] ¿Todas las dependencias están completadas?
- [ ] ¿No hay bloqueos evidentes?
- [ ] ¿He incluido razones claras en la recomendación?

### Actualización a "Todo"
- [ ] ¿Tengo alta confianza (95%+) para mover a "Todo"?
- [ ] ¿He verificado dependencias una última vez?
- [ ] ¿He documentado la acción con un comentario?
- [ ] ¿He incluido "_Hecho por Cursor_" en el comentario?

## Consejos Finales

1. **Analiza antes de recomendar** - No solo muestres issues, analízalas estratégicamente
2. **Verifica dependencias siempre** - Nunca recomiendes issues con dependencias incompletas
3. **Solo mueve a "Todo" con alta confianza** - Mejor ser conservador que mover issues incorrectamente
4. **Documenta tus acciones** - Siempre comenta cuando muevas un issue
5. **Prioriza bloqueadores** - Issues que bloquean a otros deben tener alta prioridad
6. **Sé estratégico** - Actúa como project manager, no solo como buscador de issues
