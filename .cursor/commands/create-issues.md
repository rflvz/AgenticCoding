# Crear Issues como Project Manager Profesional

Guía profesional para crear issues en Linear actuando como un project manager/programador experto.

## Filosofía: Actuar como Experto

Cuando crees issues, **NO** solo uses el MCP de Linear. Actúa como un **project manager profesional** que:

1. **Analiza profundamente** antes de crear
2. **Planifica estratégicamente** dividiendo tareas grandes
3. **Gestiona dependencias** entre tareas
4. **Organiza jerárquicamente** con sub-issues
5. **Crea recursos necesarios** (labels, etc.) si no existen
6. **Aclara dudas** antes de proceder

## Proceso de Planificación Profesional

### Paso 1: Analizar la Tarea

**ANTES de crear cualquier issue:**

1. **Comprende completamente** qué se necesita hacer
2. **Aclara dudas con el usuario** si algo no está claro
3. **Identifica el alcance** - ¿Es simple o requiere división?

### Paso 2: Divide y Vencerás

**Si la tarea es grande o compleja:**

Una tarea es "grande" si:
- Requiere más de 3-5 días de trabajo
- Involucra múltiples componentes (frontend, backend, API, DB)
- Requiere trabajo de múltiples personas/equipos
- Tiene múltiples fases claras (diseño, implementación, tests, docs)

**Proceso de división:**

1. **Crear Issue Padre (Epic)**
   - Título: `feature: [Nombre]` o `epic: [Nombre]`
   - Descripción: Visión general, objetivos, alcance
   - Labels: Intuye labels apropiados (`feature`, `epic`, etc.)

2. **Crear Sub-issues (Issues Hijos)**
   - Divide en tareas de **1-3 días** cada una
   - Cada sub-issue debe ser **independiente cuando sea posible**
   - Usa `parentId` para crear jerarquía

**Herramientas:**
- `create_issue` con `title`, `team`, `description`, `labels` (intuye labels)
- Para sub-issues: `create_issue` con `parentId` (ID del issue padre)

### Paso 3: Gestionar Dependencias

**Identificar y establecer dependencias:**

1. **Identificar dependencias**
   - ¿Qué tareas deben completarse antes de otras?
   - ¿Hay bloques de tareas que pueden ejecutarse en paralelo?
   - ¿Qué tareas bloquean a otras?

2. **Documentar dependencias en descripciones**
   ```markdown
   ## Dependencias
   - Requiere: ISSUE-123 (Diseño arquitectónico)
   - Bloquea: ISSUE-124 (Implementación backend)
   - Puede ejecutarse en paralelo con: ISSUE-125
   ```

3. **Priorizar según dependencias**
   - Issues que bloquean a otros: Alta prioridad
   - Issues que pueden esperar: Prioridad normal/baja

### Paso 4: Gestionar Labels Inteligentemente

**Intuir y gestionar labels basándote en la información de la tarea:**

#### Proceso:

1. **Intuir labels basándote en el contenido**
   - **NO esperes** que el usuario te proporcione labels
   - **Analiza** la tarea y determina qué labels son apropiados:
     - **Tipo de issue**: `bug`, `feature`, `refactor`, `docs`, `chore`
     - **Área afectada**: `frontend`, `backend`, `api`, `database`, `infrastructure`
     - **Severidad**: `critical`, `high-priority`, `low-priority`
   - Usa máximo 5 labels por issue

2. **Listar labels existentes**
   - Usa: `list_issue_labels` con `team` (opcional)
   - Revisa la lista de labels retornada

3. **Verificar si los labels intuidos existen**
   - Si el label existe: úsalo directamente
   - Si el label NO existe: créalo

4. **Crear labels si hacen falta**
   - Usa: `create_issue_label`
   - Parámetros: `name` (requerido), `description`, `color` (hex), `teamId` (opcional)

### Paso 5: Crear Issues con Información Completa

**Cuando crees un issue, incluye:**

#### Título Profesional

Formato: `[Type]: [Descripción clara y específica]`

Ejemplos:
- ✅ `bug: Login fails with 401 error using OAuth2 tokens`
- ✅ `feature: Add dark mode toggle to user settings`
- ❌ `Fix bug` (muy genérico)

#### Descripción Completa

**Estructura de descripción:**

```markdown
## Objetivo
[Qué queremos lograr]

## Contexto
[Por qué es necesario, contexto del proyecto]

## Requisitos
- [Requisito 1]
- [Requisito 2]

## Criterios de Aceptación
- [ ] Criterio 1
- [ ] Criterio 2

## Dependencias
- Requiere: ISSUE-123 (si aplica)
- Bloquea: ISSUE-124 (si aplica)
```

#### Asignación y Priorización

- **Asignación**: Asigna al **equipo correcto** según el tipo de trabajo
- **Prioridad**:
  - `Urgent` (1): Solo bugs críticos que bloquean producción
  - `High` (2): Features importantes, bugs significativos, tareas que bloquean
  - `Normal` (3): Trabajo regular (default)
  - `Low` (4): Mejoras menores, optimizaciones opcionales

### Paso 6: Gestionar Status

**Status disponibles:** `Backlog`, `Todo`, `In Progress`, `In Review`, `Done`, `Canceled`, `Duplicate`

**Status por fase de trabajo:**

- **Backlog**: Tareas pendientes de planificación
- **Todo**: Tareas listas para comenzar (default al crear)
- **In Progress**: Tareas en desarrollo activo
- **In Review**: Tareas completadas esperando revisión
- **Done**: Tareas completadas y aprobadas

**Reglas:**
- Issues que **dependen** de otros deben estar en `Todo` hasta que las dependencias estén `Done`
- Issues que **bloquean** a otros deben tener prioridad alta
- Issues que pueden ejecutarse **en paralelo** pueden estar `In Progress` simultáneamente

**Transiciones:** `Backlog → Todo → In Progress → In Review → Done`

## Herramientas de Referencia

### Crear Issue

**Herramienta:** `create_issue`

**Parámetros principales:**
- `title` (requerido): Título del issue
- `team` (requerido): Nombre o ID del equipo
- `description` (opcional): Descripción en Markdown
- `assignee` (opcional): Email del usuario o "me"
- `priority` (opcional): 1=Urgent, 2=High, 3=Normal, 4=Low
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados**
- `parentId` (opcional): ID del issue padre para crear sub-issue
- `state` (opcional): Estado inicial (`"Backlog"`, `"Todo"`, etc.)
- `project` (opcional): ID o nombre del proyecto

**Importante:** Intuye los labels basándote en tipo de tarea, área afectada y severidad.

### Gestionar Labels

- `list_issue_labels`: Listar labels existentes
- `create_issue_label`: Crear nuevo label si no existe

### Buscar Issues

- `list_issues`: Listar issues con filtros (team, state, priority, label, parentId, etc.)
- `search_issues`: Buscar issues por texto (query, team, etc.)

### Actualizar Issue

- `update_issue`: Actualizar estado, prioridad, descripción, etc.

### Listar Status Disponibles

- `list_issue_statuses`: Ver todos los status disponibles para un equipo

## Checklist de Profesionalismo

Antes de crear un issue, verifica:

- [ ] ¿Comprendo completamente la tarea?
- [ ] ¿He aclarado todas las dudas necesarias?
- [ ] ¿Es una tarea grande que requiere división?
- [ ] ¿He identificado todas las dependencias?
- [ ] ¿He intuido los labels apropiados? (crearlos si no existen)
- [ ] ¿El título es descriptivo y claro?
- [ ] ¿La descripción incluye toda la información necesaria?
- [ ] ¿Está asignado al equipo/persona correcta?
- [ ] ¿La prioridad es apropiada?
- [ ] ¿He establecido dependencias correctamente (parentId si aplica)?
- [ ] ¿He asignado el status apropiado?

## Consejos Finales

1. **Nunca crees issues sin analizar primero** - Sé un project manager, no un robot
2. **Siempre divide tareas grandes** - Divide y vencerás
3. **Gestiona dependencias proactivamente** - Identifica qué depende de qué
4. **Crea recursos si faltan** - Labels, proyectos, etc.
5. **Aclara dudas antes de crear** - Mejor preguntar que asumir
6. **Actúa como experto** - No solo uses el MCP, sé estratégico
7. **Gestiona status apropiadamente** - Usa el status correcto según la fase de trabajo
