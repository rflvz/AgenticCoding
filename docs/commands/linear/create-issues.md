# Crear Issues como Project Manager Profesional

Guía profesional para crear issues en Linear actuando como un project manager/programador experto, no solo como un usuario básico del MCP.

## Filosofía: Actuar como Experto

Cuando crees issues, **NO** solo uses el MCP de Linear. Actúa como un **project manager profesional** o **programador experto** que:

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
   - Lee y analiza la solicitud completa
   - Identifica todos los componentes involucrados
   - Detecta requisitos implícitos y explícitos

2. **Aclara dudas con el usuario**
   ```
   Antes de crear los issues, necesito aclarar:
   - ¿Cuál es el objetivo principal?
   - ¿Hay requisitos específicos que deba considerar?
   - ¿Existe algún deadline o prioridad especial?
   - ¿Hay dependencias con otros proyectos/features?
   ```

3. **Identifica el alcance**
   - ¿Es una tarea simple (1-3 días)?
   - ¿Es una tarea compleja que requiere división?
   - ¿Requiere múltiples componentes o equipos?

### Paso 2: Divide y Vencerás

**Si la tarea es grande o compleja:**

#### Detectar Tareas Grandes

Una tarea es "grande" si:
- Requiere más de 3-5 días de trabajo
- Involucra múltiples componentes (frontend, backend, API, DB)
- Requiere trabajo de múltiples personas/equipos
- Tiene múltiples fases claras (diseño, implementación, tests, docs)

#### Dividir en Sub-tareas

**Proceso de división:**

1. **Crear Issue Padre (Epic)**
   - Título: `feature: [Nombre de la feature]` o `epic: [Nombre]`
   - Descripción: Visión general, objetivos, alcance
   - Labels: `feature`, `epic`, `architecture`
   - Prioridad: Según importancia general

2. **Crear Sub-issues (Issues Hijos)**
   - Divide en tareas de **1-3 días** cada una
   - Cada sub-issue debe ser **independiente cuando sea posible**
   - Usa `parentId` para crear jerarquía

**Ejemplo de división:**

```
Epic: feature: Sistema de Autenticación OAuth2
  ├── docs: Diseño arquitectónico de autenticación
  ├── feature: Backend - API de autenticación
  ├── feature: Backend - Middleware de autenticación
  ├── feature: Frontend - Componentes de login
  ├── feature: Frontend - Gestión de sesión
  ├── chore: Tests unitarios de autenticación
  ├── chore: Tests de integración
  └── docs: Documentación de usuario
```

**Herramientas para crear jerarquía:**

1. **Crear issue padre (Epic)**
   - Usa: `create_issue`
   - Parámetros: `title`, `team`, `description`, `labels` (intuye los labels basándote en el contenido)

2. **Crear sub-issue con parentId**
   - Usa: `create_issue`
   - Parámetros: `title`, `team`, `parentId` (ID del issue padre), `description`, `labels` (intuye los labels basándote en el contenido)
   - El `parentId` establece la relación padre-hijo

### Paso 3: Gestionar Dependencias

**Identificar y establecer dependencias:**

1. **Identificar dependencias**
   - ¿Qué tareas deben completarse antes de otras?
   - ¿Hay bloques de tareas que pueden ejecutarse en paralelo?
   - ¿Qué tareas bloquean a otras?

2. **Documentar dependencias en descripciones**
   ```
   Descripción del issue:
   
   ## Dependencias
   - Requiere: ISSUE-123 (Diseño arquitectónico)
   - Bloquea: ISSUE-124 (Implementación backend)
   - Puede ejecutarse en paralelo con: ISSUE-125
   ```

3. **Usar parentId para jerarquía**
   - Issues hijos deben completarse antes del padre
   - Usa `parentId` para crear relaciones padre-hijo

4. **Priorizar según dependencias**
   - Issues que bloquean a otros: Alta prioridad
   - Issues que pueden esperar: Prioridad normal/baja

### Paso 4: Gestionar Labels Inteligentemente

**Intuir y gestionar labels basándote en la información de la tarea:**

#### Proceso:

1. **Intuir labels basándote en el contenido**
   - **NO esperes** que el usuario te proporcione labels
   - **Analiza** la tarea y determina qué labels son apropiados:
     - **Tipo de issue**: `bug` (si es un error), `feature` (si es nueva funcionalidad), `refactor` (si es mejora de código), `docs` (si es documentación), `chore` (si es mantenimiento)
     - **Área afectada**: `frontend` (si involucra UI), `backend` (si involucra servidor), `api` (si involucra API), `database` (si involucra BD), `infrastructure` (si involucra infraestructura)
     - **Severidad**: `critical` (si bloquea producción), `high-priority` (si es importante), `low-priority` (si es menor)
   - Usa máximo 5 labels por issue

2. **Listar labels existentes**
   - Usa: `list_issue_labels`
   - Parámetros opcionales: `team` (para filtrar por equipo), `name` (para filtrar por nombre)
   - Revisa la lista de labels retornada

3. **Verificar si los labels intuidos existen**
   - Si el label existe en la lista: úsalo directamente
   - Si el label NO existe: créalo

4. **Crear labels si hacen falta**
   - Usa: `create_issue_label`
   - Parámetros requeridos: `name` (nombre del label)
   - Parámetros opcionales: `description`, `color` (formato hexadecimal, ej: "#FF5733"), `teamId` (si no se proporciona, será workspace-wide)

**Ejemplos de intuición de labels:**

- **Tarea**: "Corregir bug en el login que falla con OAuth2"
  - Labels intuidos: `bug`, `backend` (o `api`), `critical` (si bloquea producción)

- **Tarea**: "Añadir modo oscuro al frontend"
  - Labels intuidos: `feature`, `frontend`

- **Tarea**: "Refactorizar middleware de autenticación"
  - Labels intuidos: `refactor`, `backend`

- **Tarea**: "Documentar API de usuarios"
  - Labels intuidos: `docs`, `api`

### Paso 5: Crear Issues con Información Completa

**Cuando crees un issue, incluye:**

#### Título Profesional

Formato: `[Type]: [Descripción clara y específica]`

Ejemplos:
- ✅ `bug: Login fails with 401 error using OAuth2 tokens`
- ✅ `feature: Add dark mode toggle to user settings`
- ✅ `refactor: Simplify authentication middleware`
- ❌ `Fix bug`
- ❌ `Feature`
- ❌ `Update code`

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
- [Requisito 3]

## Criterios de Aceptación
- [ ] Criterio 1
- [ ] Criterio 2
- [ ] Criterio 3

## Dependencias
- Requiere: ISSUE-123 (si aplica)
- Bloquea: ISSUE-124 (si aplica)
- Puede ejecutarse en paralelo con: ISSUE-125 (si aplica)

## Notas Técnicas
[Información técnica relevante, arquitectura, consideraciones]

## Referencias
[Links a código, documentación, issues relacionados]
```

#### Asignación Inteligente

- Asigna al **equipo correcto** según el tipo de trabajo
- Asigna a **persona específica** si conoces sus habilidades
- Usa `"me"` para auto-asignación cuando sea apropiado
- Considera la **carga de trabajo actual** del equipo

#### Priorización Estratégica

- `Urgent`: Solo bugs críticos que bloquean producción
- `High`: Features importantes, bugs significativos, tareas que bloquean
- `Normal`: Trabajo regular (default)
- `Low`: Mejoras menores, optimizaciones opcionales

### Paso 6: Gestionar Status en Trabajo Paralelo

**Status disponibles en Linear para AgentiCoding:**

- `Backlog`: Tareas pendientes de planificación
- `Todo`: Tareas listas para comenzar
- `In Progress`: Tareas en desarrollo activo
- `In Review`: Tareas completadas esperando revisión
- `Done`: Tareas completadas y aprobadas
- `Canceled`: Tareas canceladas
- `Duplicate`: Issues duplicados

#### Status por Fase de Trabajo Paralelo

Cuando múltiples agentes trabajan en paralelo en AgentiCoding, cada issue debe tener el status apropiado según su fase:

**Fase 1: Planificación y Diseño**

```
Epic Padre (Agente Orquestador):
- Status: "Todo" o "Backlog" (si no está listo para comenzar)
- Descripción: Define la visión general y divide en sub-tareas

Sub-issues de Diseño (Agentes Especializados):
- Status: "Todo" (al crear)
- Status: "In Progress" (cuando el agente comienza a trabajar)
- Status: "In Review" (cuando el diseño está completo, esperando aprobación)
- Status: "Done" (cuando el diseño está aprobado)
```

**Fase 2: Desarrollo**

```
Issues de Implementación (Agentes Especializados):
- Status: "Todo" (al crear, si depende de diseño)
- Status: "In Progress" (cuando el agente comienza a implementar)
- Status: "In Review" (cuando la implementación está completa)
- Status: "Done" (cuando pasa code review)

Issues que pueden ejecutarse en paralelo:
- Frontend: "In Progress" (mientras Backend también está "In Progress")
- Backend: "In Progress" (mientras Frontend también está "In Progress")
- Ambos pueden estar "In Progress" simultáneamente
```

**Fase 3: Testing**

```
Issues de Testing (Agente Testing):
- Status: "Todo" (al crear, esperando que dependencias estén "Done")
- Status: "In Progress" (cuando comienza a escribir tests)
- Status: "In Review" (cuando tests están completos, esperando verificación)
- Status: "Done" (cuando todos los tests pasan)

Nota: Solo puede comenzar cuando ISSUE-126, ISSUE-127, ISSUE-128 están "Done"
```

**Fase 4: Code Review**

```
Issues en Revisión (Agente Code Review):
- Status: "In Review" (cuando el código está listo para revisar)
- Status: "Done" (si aprueba sin cambios)
- Status: "In Progress" (si requiere cambios, reasignar al agente original)
```

**Fase 5: Documentación**

```
Issues de Documentación (Agente Documentation):
- Status: "Todo" (al crear, esperando que implementación esté "Done")
- Status: "In Progress" (cuando comienza a documentar)
- Status: "In Review" (cuando documentación está completa)
- Status: "Done" (cuando documentación está aprobada)
```

**Fase 6: Deployment**

```
Issues de Deployment (Agente DevOps):
- Status: "Todo" (al crear, esperando que todo esté "Done")
- Status: "In Progress" (durante deployment)
- Status: "In Review" (verificando que deployment sea exitoso)
- Status: "Done" (cuando deployment está completo y verificado)
```

#### Reglas de Status en Trabajo Paralelo

**1. Dependencias y Status:**

- Issues que **dependen** de otros deben estar en `Todo` hasta que las dependencias estén `Done`
- Issues que **bloquean** a otros deben tener prioridad alta y estar `In Progress` rápidamente
- Issues que pueden ejecutarse **en paralelo** pueden estar `In Progress` simultáneamente

**2. Transiciones de Status:**

```
Backlog → Todo → In Progress → In Review → Done
                                     ↓
                                (si requiere cambios)
                                     ↓
                              In Progress (nuevamente)
```

**3. Status en Creación de Issues:**

Al crear issues, usa el parámetro `state` según el contexto:

- **Si no hay dependencias**: `state: "Todo"` (listo para comenzar)
- **Si hay dependencias**: `state: "Todo"` (pero documenta las dependencias en la descripción)
- **Si es un Epic padre**: `state: "Backlog"` o `state: "Todo"` según planificación
- **Si es un sub-issue que puede comenzar inmediatamente**: `state: "Todo"`

**4. Actualización de Status Durante Desarrollo:**

Durante el desarrollo paralelo, los agentes deben actualizar el status usando `update_issue`:

- **Al comenzar trabajo**: Actualizar a `In Progress`
- **Al completar trabajo**: Actualizar a `In Review`
- **Al aprobar**: Actualizar a `Done`
- **Si requiere cambios**: Actualizar a `In Progress` y reasignar

#### Ejemplo: Status en Feature Completa

```
Epic: Sistema de Autenticación
Status: "Todo"

├─ ISSUE-123: Diseño arquitectónico
│  Status: "Todo" → "In Progress" → "In Review" → "Done"
│
├─ ISSUE-124: Diseño UI (depende de ISSUE-123)
│  Status: "Todo" (esperando ISSUE-123 "Done") → "In Progress" → "Done"
│
├─ ISSUE-125: Diseño API (depende de ISSUE-123)
│  Status: "Todo" (esperando ISSUE-123 "Done") → "In Progress" → "Done"
│
├─ ISSUE-126: UI de login (depende de ISSUE-124)
│  Status: "Todo" → "In Progress" (paralelo con ISSUE-127) → "In Review" → "Done"
│
├─ ISSUE-127: API de autenticación (depende de ISSUE-125)
│  Status: "Todo" → "In Progress" (paralelo con ISSUE-126) → "In Review" → "Done"
│
├─ ISSUE-128: Integración (depende de ISSUE-126 y ISSUE-127)
│  Status: "Todo" (esperando ambos "Done") → "In Progress" → "In Review" → "Done"
│
├─ ISSUE-129: Tests (depende de ISSUE-128)
│  Status: "Todo" → "In Progress" → "In Review" → "Done"
│
└─ ISSUE-130: Documentación (depende de ISSUE-128)
   Status: "Todo" → "In Progress" → "In Review" → "Done"
```

#### Herramientas para Gestionar Status

**Actualizar Status:**

Usa `update_issue` con el parámetro `state`:

```
update_issue(
  id: "ISSUE-123",
  state: "In Progress"  // o "In Review", "Done", etc.
)
```

**Listar Status Disponibles:**

Usa `list_issue_statuses` con el parámetro `team` para ver todos los status disponibles:

```
list_issue_statuses(team: "DAW")
// Retorna: Backlog, Todo, In Progress, In Review, Done, Canceled, Duplicate
```

**Verificar Status de Dependencias:**

Antes de cambiar un issue a `In Progress`, verifica que las dependencias estén `Done`:

```
list_issues(team: "DAW", parentId: "ISSUE-EPIC-123")
// Verifica que todos los issues dependientes estén "Done"
```

## Ejemplos de Uso Profesional

### Ejemplo 1: Crear Feature Compleja

**Usuario:** "Necesitamos implementar un sistema de notificaciones"

**Proceso del agente:**

1. **Aclarar dudas:**
   ```
   Antes de crear los issues, necesito aclarar:
   - ¿Qué tipos de notificaciones? (email, push, in-app)
   - ¿Hay algún sistema de notificaciones existente?
   - ¿Cuál es el deadline?
   - ¿Requiere integración con servicios externos?
   ```

2. **Analizar y dividir:**
   - Identificar que es una tarea grande (requiere división)
   - Crear Epic padre
   - Dividir en sub-tareas manejables

3. **Crear issues:**
   - **Epic padre**: Usa `create_issue` con `title`, `team`, `description`, `priority`, `labels` (intuye los labels apropiados)
   - **Sub-issues**: Usa `create_issue` con `title`, `parentId` (ID del epic), `team`, `priority`, `labels` (intuye los labels apropiados), `description`

### Ejemplo 2: Crear Issue con Dependencias

**Usuario:** "Crear endpoint de autenticación que depende del diseño"

**Proceso del agente:**

1. **Buscar issue de diseño:**
   - Usa: `search_issues` con `query: "diseño autenticación"` y `team: "Engineering"`
   - O usa: `list_issues` con filtros como `team`, `label`, etc.
   - Revisa los issues encontrados para identificar el issue de diseño relacionado

2. **Crear issue con dependencia:**
   - Usa: `create_issue`
   - Parámetros: `title`, `team`, `description` (incluye sección de dependencias con el ID del issue encontrado), `priority`, `labels` (intuye los labels apropiados basándote en el contenido)

## Herramientas de Referencia

### Crear Issue

**Herramienta:** `create_issue`

**Parámetros disponibles:**
- `title` (requerido): Título del issue
- `team` (requerido): Nombre o ID del equipo
- `description` (opcional): Descripción del issue en Markdown
- `assignee` (opcional): Email del usuario asignado o "me"
- `priority` (opcional): 1=Urgent, 2=High, 3=Normal, 4=Low
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados basándote en el contenido de la tarea**
- `project` (opcional): Nombre o ID del proyecto
- `dueDate` (opcional): Fecha en formato "YYYY-MM-DD"
- `parentId` (opcional): ID del issue padre para crear sub-issue
- `state` (opcional): Estado inicial del issue. Valores disponibles: `"Backlog"`, `"Todo"`, `"In Progress"`, `"In Review"`, `"Done"`, `"Canceled"`, `"Duplicate"`. **Usa el status apropiado según la fase de trabajo paralelo** (ver Paso 6)

**Importante:** Intuye los labels basándote en:
- Tipo de tarea (bug, feature, refactor, docs, chore)
- Área afectada (frontend, backend, api, database, infrastructure)
- Severidad (si aplica)

### Listar Labels

**Herramienta:** `list_issue_labels`

**Parámetros opcionales:**
- `team`: Filtrar por equipo
- `name`: Filtrar por nombre de label

**Retorna:** Lista de labels con información completa (nombre, descripción, color, etc.)

### Crear Label

**Herramienta:** `create_issue_label`

**Parámetros requeridos:**
- `name`: Nombre del label

**Parámetros opcionales:**
- `description`: Descripción del label
- `color`: Color en formato hexadecimal (ej: "#FF5733")
- `teamId`: ID del equipo (si no se proporciona, es workspace-wide)

### Buscar Issues

**Herramienta:** `search_issues`

**Parámetros:**
- `query` (requerido): Texto de búsqueda
- `team` (opcional): Filtrar por equipo
- `timeMin` (opcional): Fecha mínima
- `timeMax` (opcional): Fecha máxima

### Listar Issues

**Herramienta:** `list_issues`

**Parámetros útiles:**
- `team`: Filtrar por equipo
- `state`: Filtrar por estado (`"Backlog"`, `"Todo"`, `"In Progress"`, `"In Review"`, `"Done"`, etc.)
- `assignee`: Filtrar por asignado
- `priority`: Filtrar por prioridad
- `label`: Filtrar por label
- `project`: Filtrar por proyecto
- `parentId`: Filtrar por issue padre (para obtener sub-issues)

### Actualizar Issue

**Herramienta:** `update_issue`

**Parámetros útiles:**
- `id` (requerido): ID del issue a actualizar
- `state` (opcional): Nuevo estado del issue (`"Backlog"`, `"Todo"`, `"In Progress"`, `"In Review"`, `"Done"`, etc.)
- `title` (opcional): Nuevo título
- `description` (opcional): Nueva descripción
- `assignee` (opcional): Nuevo asignado
- `priority` (opcional): Nueva prioridad
- `labels` (opcional): Nuevos labels
- `project` (opcional): Nuevo proyecto
- `dueDate` (opcional): Nueva fecha de vencimiento

**Uso típico para trabajo paralelo:**
```
update_issue(id: "ISSUE-123", state: "In Progress")  // Al comenzar trabajo
update_issue(id: "ISSUE-123", state: "In Review")     // Al completar trabajo
update_issue(id: "ISSUE-123", state: "Done")          // Al aprobar
```

### Listar Status Disponibles

**Herramienta:** `list_issue_statuses`

**Parámetros:**
- `team` (requerido): Nombre o ID del equipo

**Retorna:** Lista de status disponibles para el equipo con sus IDs y nombres

**Uso:**
```
list_issue_statuses(team: "DAW")
// Retorna: Backlog, Todo, In Progress, In Review, Done, Canceled, Duplicate
```

## Checklist de Profesionalismo

Antes de crear un issue, verifica:

- [ ] ¿Comprendo completamente la tarea?
- [ ] ¿He aclarado todas las dudas necesarias?
- [ ] ¿Es una tarea grande que requiere división?
- [ ] ¿He identificado todas las dependencias?
- [ ] ¿He intuido los labels apropiados basándome en el contenido? (crearlos si no existen)
- [ ] ¿El título es descriptivo y claro?
- [ ] ¿La descripción incluye toda la información necesaria?
- [ ] ¿Está asignado al equipo/persona correcta?
- [ ] ¿La prioridad es apropiada?
- [ ] ¿He establecido dependencias correctamente (parentId si aplica)?
- [ ] ¿He asignado el status apropiado según la fase de trabajo paralelo? (ver Paso 6)
- [ ] ¿El status es consistente con las dependencias del issue? (si hay dependencias, debe estar en "Todo" hasta que estén "Done")

## Consejos Finales

1. **Nunca crees issues sin analizar primero** - Sé un project manager, no un robot
2. **Siempre divide tareas grandes** - Divide y vencerás
3. **Gestiona dependencias proactivamente** - Identifica qué depende de qué
4. **Crea recursos si faltan** - Labels, proyectos, etc.
5. **Aclara dudas antes de crear** - Mejor preguntar que asumir
6. **Actúa como experto** - No solo uses el MCP, sé estratégico
7. **Gestiona status en trabajo paralelo** - Usa el status apropiado según la fase (ver Paso 6) y actualiza el status cuando los agentes comienzan, completan o requieren cambios
8. **Sincroniza status con dependencias** - Verifica que las dependencias estén "Done" antes de cambiar un issue a "In Progress"
