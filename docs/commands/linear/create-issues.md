# Crear Issues como Project Manager Profesional

Guía profesional para crear issues en Linear actuando como un project manager/programador experto.

> **⚠️ IMPORTANTE:** Antes de usar este comando, lee el [documento de contexto del proyecto](../../project-context.md) para obtener información actualizada sobre el proyecto y trabajo en Linear. Este documento es la fuente única de verdad para contexto del proyecto. Si el documento no existe, usa el [comando de inicialización](./initialize-project-context.md) para crearlo.

**⚠️⚠️⚠️ LEE ESTO PRIMERO: Este comando es SOLO para CREAR issues en Linear. NO implementes NADA. NO escribas código. NO trabajes en la tarea. Tu trabajo TERMINA cuando has creado los issues. ⚠️⚠️⚠️**

## ⚠️⚠️⚠️ REGLA CRÍTICA: Tu Trabajo es CREAR Issues, NO Implementar ⚠️⚠️⚠️

**Cuando te piden "crear issues", usar el comando `/create-issues`, o cualquier variación:**
- **Tu trabajo ÚNICAMENTE es CREAR los issues en Linear** - planificar, dividir, organizar y crear los issues
- **NO es implementar la tarea** descrita en el issue
- **NO es escribir código** para resolver el issue
- **NO es completar el trabajo** del issue
- **NO es empezar a trabajar** en la tarea
- **NO es crear archivos** de código
- **NO es hacer commits** en Git
- **NO es crear Pull Requests** para implementar código
- **SÍ es crear Pull Requests vacíos/draft** cuando hay repositorio disponible para preparar la infraestructura

**Tu trabajo TERMINA cuando has creado los issues en Linear. NO continúes con la implementación.**

**Ejemplo:**
- Si el usuario dice "crear issue para implementar autenticación", tu trabajo es:
  - ✅ Analizar la tarea
  - ✅ Dividir en sub-issues si es necesario
  - ✅ Crear los issues en Linear con descripciones completas
  - ✅ Crear Pull Requests vacíos/draft si hay repositorio (para preparar infraestructura)
  - ✅ Vincular los PRs a los issues en Linear
  - ✅ **FIN - Has terminado tu trabajo**
  - ❌ NO implementar el código de autenticación
  - ❌ NO escribir el código del endpoint
  - ❌ NO crear archivos de código
  - ❌ NO hacer commits con código
  - ❌ NO completar la tarea

**Para implementar/completar issues, el usuario debe usar el comando `/complete-issues`**, no `/create-issues`.

**Si el usuario te pide que trabajes en la tarea después de crear los issues, usa `/complete-issues`, no continúes desde `/create-issues`.**

## Filosofía: Actuar como Experto

Cuando crees issues, **NO** solo uses el MCP de Linear. Actúa como un **project manager profesional** que:

1. **Analiza profundamente** antes de crear
2. **Planifica estratégicamente** dividiendo tareas grandes
3. **Gestiona dependencias** entre tareas
4. **Organiza jerárquicamente** con sub-issues
5. **Crea recursos necesarios** (labels, etc.) si no existen
6. **Aclara dudas** antes de proceder

## Proceso de Planificación Profesional

**⚠️⚠️⚠️ RECUERDA EN CADA PASO: Estás CREANDO issues, NO implementando. Tu trabajo termina cuando creas los issues en Linear. ⚠️⚠️⚠️**

### Paso 1: Analizar la Tarea

**⚠️⚠️⚠️ CRÍTICO: Tu trabajo aquí es ANALIZAR para CREAR el issue en Linear, NO para implementarlo. NO empieces a trabajar en la tarea. ⚠️⚠️⚠️**

**ANTES de crear cualquier issue:**

1. **Comprende completamente** qué se necesita hacer (para crear el issue, no para implementarlo)
2. **Aclara dudas con el usuario** si algo no está claro (para poder crear el issue correctamente)
3. **Identifica el alcance** - ¿Es simple o requiere división? (para planificar la creación de issues, no para implementar)

### Paso 2: Divide y Vencerás

**⚠️ RECUERDA: Aquí divides para CREAR issues, NO para implementar. Tu trabajo termina cuando creas los issues.**

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
   - **Crear el issue en Linear usando `create_issue`**
   - **NO implementar nada**

2. **Crear Sub-issues (Issues Hijos)**
   - Divide en tareas de **1-3 días** cada una
   - Cada sub-issue debe ser **independiente cuando sea posible**
   - Usa `parentId` para crear jerarquía
   - **Crear cada sub-issue en Linear usando `create_issue`**
   - **NO implementar nada**

**Herramientas:**
- `create_issue` con `title`, `team`, `description`, `labels` (intuye labels)
- Para sub-issues: `create_issue` con `parentId` (ID del issue padre)

**⚠️⚠️⚠️ CRÍTICO: Una vez creados todos los issues en Linear y vinculados PRs (si hay repositorio), tu trabajo ha TERMINADO.**
- ✅ Has terminado cuando has creado los issues en Linear
- ✅ Has terminado cuando has creado PRs vacíos/draft y los has vinculado a los issues (si hay repositorio)
- ❌ NO continúes con la implementación
- ❌ NO escribas código
- ❌ NO crees archivos de código
- ❌ NO hagas commits con código
- ❌ NO trabajes en la tarea

**Si el usuario quiere que implementes, debe usar `/complete-issues` explícitamente.**

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

**⚠️⚠️⚠️ CRÍTICO: Este paso es CREAR los issues en Linear usando `create_issue`. NO implementes nada. NO escribas código. NO trabajes en la tarea. ⚠️⚠️⚠️**

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

#### Intuir Proyecto

**⚠️ Si el usuario no especifica el proyecto, debes intuirlo:**

- Analiza el contexto del issue (título, descripción, labels)
- Busca proyectos relacionados en Linear usando `list_projects`
- Si el issue menciona un proyecto existente, úsalo
- Si hay un proyecto activo relacionado con el tema, úsalo
- Si no hay proyecto claro, puedes omitir el parámetro `project` o crear uno nuevo si es apropiado

### Paso 6: Crear Pull Requests y Vincular a Issues (si hay repositorio)

**⚠️ REGLA IMPORTANTE: Si hay un repositorio disponible (GitHub/GitLab), crea Pull Requests vacíos/draft y vincúlalos a los issues.**

#### Verificar Repositorio Disponible

1. **Verificar si hay repositorio Git:**
   - Revisar si hay un repositorio Git en el proyecto actual (`git remote -v`)
   - Verificar si hay un repositorio remoto configurado (GitHub/GitLab)
   - Si hay MCP de GitHub configurado, verificar si hay repositorio disponible

2. **Obtener información del repositorio:**
   - Si hay GitHub MCP: usar herramientas para obtener información del repositorio
   - Identificar la rama principal (`main`, `master`, etc.)
   - Obtener el nombre del repositorio y organización

#### Crear Pull Request Vacío/Draft para cada Issue

**Si hay repositorio disponible, para cada issue creado:**

1. **Crear branch vacío:**
   - Nombre del branch basado en el issue: `feature/ISSUE-123-descripcion-corta`, `fix/ISSUE-124-descripcion-bug`, etc.
   - Usar convenciones de nombres según el tipo de issue:
     - `feature/ISSUE-XXX-descripcion` para features
     - `fix/ISSUE-XXX-descripcion` para bugs
     - `refactor/ISSUE-XXX-descripcion` para refactors
     - `docs/ISSUE-XXX-descripcion` para documentación
     - `chore/ISSUE-XXX-descripcion` para chores
   - Crear el branch desde la rama principal (no hacer commits aún)

2. **Crear Pull Request vacío/draft:**
   - Título: Usar el título del issue en Linear
   - Descripción: 
     ```markdown
     ## Issue Relacionado
     Linear: [ISSUE-XXX](enlace-al-issue-en-linear)
     
     ## Descripción
     [Descripción del issue]
     
     ## Estado
     - [ ] Issue creado en Linear
     - [ ] PR preparado
     - [ ] Pendiente de implementación
     ```
   - Marcar como **draft** (borrador) para indicar que está preparado pero no implementado
   - Base: rama principal (`main`, `master`, etc.)
   - Head: el branch recién creado

3. **Vincular PR al Issue en Linear:**
   - Usar `update_issue` con el parámetro `links` para añadir el enlace al PR
   - O incluir el enlace del PR en la descripción del issue (actualizar usando `update_issue`)
   - Formato del enlace: `[PR #123](url-del-pr)` en la descripción o usar `links` array

**Ejemplo de actualización del issue con enlace al PR:**
```markdown
## Enlaces Relacionados
- Pull Request: [PR #123](https://github.com/owner/repo/pull/123)
- Repositorio: [owner/repo](https://github.com/owner/repo)
```

**Herramientas necesarias:**
- `git` commands para crear branches (si hay repositorio local)
- GitHub MCP tools (si está configurado): `create_pull_request`, etc.
- `update_issue` de Linear para vincular el PR usando `links` o actualizar descripción

**⚠️ IMPORTANTE:**
- Solo crear PRs **vacíos/draft** - NO implementar código
- Solo crear branches - NO hacer commits con código
- El PR queda preparado para que se implemente después con `/complete-issues`
- Si no hay repositorio disponible, simplemente omitir este paso

### Paso 7: Gestionar Status

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
- `project` (opcional): ID o nombre del proyecto - **⚠️ INTUYE el proyecto si el usuario no lo especifica**
- `links` (opcional): Array de objetos con `url` y `title` para vincular PRs y otros recursos

**⚠️⚠️⚠️ CRÍTICO: Esta herramienta `create_issue` es para CREAR issues en Linear. ⚠️⚠️⚠️**

**REGLA ABSOLUTA:**
- ✅ Usa `create_issue` para crear issues en Linear
- ✅ Una vez creados todos los issues solicitados, tu trabajo ha TERMINADO
- ❌ NO uses `create_issue` y luego continúes implementando
- ❌ NO escribas código después de crear issues
- ❌ NO crees archivos después de crear issues
- ❌ NO hagas commits después de crear issues
- ❌ NO trabajes en la tarea después de crear issues

**Si el usuario quiere implementación, debe usar `/complete-issues` explícitamente.**

**Importante:** 
- Intuye los labels basándote en tipo de tarea, área afectada y severidad.
- **Intuye el proyecto** analizando el contexto del issue y buscando proyectos relacionados en Linear.
- **NO implementes nada después de crear los issues**

### Gestionar Labels

- `list_issue_labels`: Listar labels existentes
- `create_issue_label`: Crear nuevo label si no existe

### Buscar Issues

- `list_issues`: Listar issues con filtros (team, state, priority, label, parentId, etc.)
- `search_issues`: Buscar issues por texto (query, team, etc.)

### Actualizar Issue

- `update_issue`: Actualizar estado, prioridad, descripción, links, etc.
  - **Parámetro `links`**: Array de objetos `{url: string, title: string}` para vincular PRs y recursos externos
  - Usar para vincular Pull Requests a issues después de crearlos

### Gestión de Pull Requests y Repositorios

**Si hay repositorio disponible (GitHub/GitLab):**

- **GitHub MCP tools** (si está configurado):
  - Crear branches: usar comandos `git` o herramientas del MCP
  - Crear PRs: usar herramientas del MCP de GitHub
  - Obtener información del repositorio
  
- **Crear PRs vacíos/draft:**
  - Crear branch vacío desde la rama principal
  - Crear PR con estado "draft"
  - Vincular PR al issue usando `update_issue` con `links`

### Listar Status Disponibles

- `list_issue_statuses`: Ver todos los status disponibles para un equipo

## Checklist de Profesionalismo

**⚠️⚠️⚠️ CRÍTICO: Este checklist es para CREAR issues. Una vez completado, tu trabajo ha terminado. NO implementes nada. ⚠️⚠️⚠️**

Antes de crear un issue, verifica:

- [ ] ¿Comprendo completamente la tarea? (para crear el issue, no para implementarlo)
- [ ] ¿He aclarado todas las dudas necesarias? (para crear el issue correctamente)
- [ ] ¿Es una tarea grande que requiere división? (para crear múltiples issues, no para implementar)
- [ ] ¿He identificado todas las dependencias? (para documentar en los issues)
- [ ] ¿He intuido los labels apropiados? (crearlos si no existen)
- [ ] ¿El título es descriptivo y claro?
- [ ] ¿La descripción incluye toda la información necesaria?
- [ ] ¿Está asignado al equipo/persona correcta?
- [ ] ¿La prioridad es apropiada?
- [ ] ¿He establecido dependencias correctamente (parentId si aplica)?
- [ ] ¿He asignado el status apropiado?
- [ ] ⚠️ **¿Hay repositorio disponible?** (Si SÍ, crear PRs vacíos/draft y vincularlos)
- [ ] ⚠️ **¿He creado Pull Requests vacíos/draft y vinculado a los issues?** (Si hay repositorio)
- [ ] ⚠️ **¿He creado todos los issues solicitados en Linear?** (Si SÍ, tu trabajo ha terminado. NO continúes)
- [ ] ⚠️ **¿He intentado implementar o escribir código?** (Si SÍ, detente. Eso es para `/complete-issues`)

## Consejos Finales

**⚠️⚠️⚠️ LEE ESTOS CONSEJOS ANTES DE HACER CUALQUIER COSA: ⚠️⚠️⚠️**

1. **⚠️⚠️⚠️ CRÍTICO: Tu trabajo es CREAR issues, NO implementarlos** 
   - Si te piden crear issues, crea los issues en Linear
   - Si hay repositorio, crea PRs vacíos/draft y vincúlalos a los issues
   - DETENTE después de crear issues y vincular PRs
   - NO implementes la tarea
   - NO escribas código
   - NO trabajes en la tarea
   - NO crees archivos de código
   - NO hagas commits con código
   - NO crees Pull Requests con código implementado (solo PRs vacíos/draft)

2. **⚠️ Tu trabajo TERMINA cuando has creado los issues y vinculado PRs (si hay repositorio)** 
   - Una vez creados todos los issues en Linear usando `create_issue`, tu trabajo ha terminado
   - Si hay repositorio, una vez creados los PRs vacíos/draft y vinculados a los issues, tu trabajo ha terminado
   - NO continúes con nada más
   - NO empieces a implementar
   - NO preguntes si quieres que implemente

3. **⚠️ Si el usuario quiere que implementes, debe usar `/complete-issues`** 
   - No continúes desde `/create-issues` hacia la implementación
   - Si el usuario te pide trabajar en la tarea, usa `/complete-issues` explícitamente
   - NO asumas que debes continuar después de crear issues
4. **Nunca crees issues sin analizar primero** - Sé un project manager, no un robot
5. **Siempre divide tareas grandes** - Divide y vencerás (para crear múltiples issues, no para implementar)
6. **Gestiona dependencias proactivamente** - Identifica qué depende de qué (para documentar en los issues)
7. **Crea recursos si faltan** - Labels, proyectos, etc. (para poder crear los issues correctamente)
8. **Aclara dudas antes de crear** - Mejor preguntar que asumir (para crear issues correctos)
9. **Actúa como experto** - No solo uses el MCP, sé estratégico (en la creación de issues, no en la implementación)
10. **Gestiona status apropiadamente** - Usa el status correcto según la fase de trabajo
11. **Crea Pull Requests cuando hay repositorio** - Si hay un repositorio disponible, crea PRs vacíos/draft y vincúlalos a los issues para preparar la infraestructura
