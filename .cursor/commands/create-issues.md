# Crear Issues en Linear

## Objetivo y Restricciones

Objetivo: Crear issues en Linear usando el MCP. NO implementar código. NO escribir código. NO trabajar en la tarea.

Restricciones absolutas:
- Tu trabajo TERMINA cuando has creado los issues en Linear
- NO implementar la tarea descrita en el issue
- NO escribir código para resolver el issue
- NO crear archivos de código
- NO hacer commits con código
- NO crear Pull Requests con código implementado
- SÍ crear Pull Requests vacíos/draft si hay repositorio disponible

## Pasos Obligatorios

1. Analizar la tarea solicitada
2. VERIFICAR: ¿La tarea requiere división? [SI/NO]
   - IF SI → Crear issue padre (epic) y sub-issues
   - IF NO → Crear issue único
3. VERIFICAR: ¿Hay repositorio disponible? [SI/NO]
   - IF SI → Crear PRs vacíos/draft y vincular a issues
   - IF NO → Continuar sin PRs
4. Gestionar labels: intuir, verificar existencia, crear si faltan
5. Crear issues en Linear con información completa
6. VERIFICAR: ¿Se crearon todos los issues solicitados? [SI/NO]
   - IF SI → FIN. Tu trabajo ha terminado.
   - IF NO → Repetir pasos faltantes

## Proceso de Creación

### Paso 1: Analizar Tarea

ANTES de crear cualquier issue:

1. Comprender completamente qué se necesita hacer
2. VERIFICAR: ¿Hay dudas que aclarar? [SI/NO]
   - IF SI → Preguntar al usuario antes de continuar
   - IF NO → Continuar
3. Identificar alcance: ¿Es simple o requiere división?

### Paso 2: Dividir Tarea (si aplica)

VERIFICAR: ¿La tarea es grande? [SI/NO]

IF SI (tarea grande) THEN:
- Requiere más de 3-5 días de trabajo
- Involucra múltiples componentes (frontend, backend, API, DB)
- Requiere trabajo de múltiples personas/equipos
- Tiene múltiples fases claras (diseño, implementación, tests, docs)

Proceso de división:
1. Crear Issue Padre (Epic)
   - Título: `feature: [Nombre]` o `epic: [Nombre]`
   - Descripción: Visión general, objetivos, alcance
   - Labels: Intuir labels apropiados
   - Crear usando `create_issue`
2. Crear Sub-issues
   - Dividir en tareas de 1-3 días cada una
   - Cada sub-issue independiente cuando sea posible
   - Usar `parentId` para crear jerarquía
   - Crear cada uno usando `create_issue`

IF NO (tarea simple) THEN:
- Crear issue único con toda la información

### Paso 3: Gestionar Dependencias

1. Identificar dependencias
   - ¿Qué tareas deben completarse antes de otras?
   - ¿Hay bloques que pueden ejecutarse en paralelo?
   - ¿Qué tareas bloquean a otras?
2. Documentar en descripciones:
   ```markdown
   ## Dependencias
   - Requiere: ISSUE-123 (Diseño arquitectónico)
   - Bloquea: ISSUE-124 (Implementación backend)
   - Puede ejecutarse en paralelo con: ISSUE-125
   ```
3. Priorizar según dependencias
   - Issues que bloquean a otros: Alta prioridad
   - Issues que pueden esperar: Prioridad normal/baja

### Paso 4: Gestionar Labels

1. Intuir labels basándote en el contenido
   - NO esperar que el usuario proporcione labels
   - Analizar la tarea y determinar labels apropiados:
     - Tipo: `bug`, `feature`, `refactor`, `docs`, `chore`
     - Área: `frontend`, `backend`, `api`, `database`, `infrastructure`
     - Severidad: `critical`, `high-priority`, `low-priority`
   - Máximo 5 labels por issue
2. Listar labels existentes usando `list_issue_labels`
3. VERIFICAR: ¿Los labels intuidos existen? [SI/NO]
   - IF SI → Usar directamente
   - IF NO → Crear usando `create_issue_label`
4. Crear labels faltantes con `create_issue_label`

### Paso 5: Crear Issues

Cada issue debe incluir:

Título:
- Formato: `[Type]: [Descripción clara y específica]`
- Ejemplos:
  - `bug: Login fails with 401 error using OAuth2 tokens`
  - `feature: Add dark mode toggle to user settings`

Descripción (estructura):
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

Asignación y priorización:
- Asignar al equipo correcto según tipo de trabajo
- Prioridad:
  - Urgent (1): Solo bugs críticos que bloquean producción
  - High (2): Features importantes, bugs significativos, tareas que bloquean
  - Normal (3): Trabajo regular (default)
  - Low (4): Mejoras menores, optimizaciones opcionales

Intuir proyecto:
- VERIFICAR: ¿El usuario especificó proyecto? [SI/NO]
  - IF NO → Analizar contexto del issue, buscar proyectos relacionados con `list_projects`, usar si existe, omitir si no hay proyecto claro
  - IF SI → Usar proyecto especificado

### Paso 6: Crear Pull Requests (si hay repositorio)

VERIFICAR: ¿Hay repositorio disponible? [SI/NO]

IF SI THEN:
1. Verificar repositorio Git (`git remote -v`)
2. Obtener información: rama principal, nombre repositorio, organización
3. Para cada issue creado:
   - Crear branch vacío: `feature/ISSUE-123-descripcion`, `fix/ISSUE-124-descripcion`, etc.
   - Convenciones según tipo:
     - `feature/ISSUE-XXX-descripcion` para features
     - `fix/ISSUE-XXX-descripcion` para bugs
     - `refactor/ISSUE-XXX-descripcion` para refactors
     - `docs/ISSUE-XXX-descripcion` para documentación
     - `chore/ISSUE-XXX-descripcion` para chores
   - Crear PR vacío/draft:
     - Título: Título del issue en Linear
     - Descripción:
       ```markdown
       ## Issue Relacionado
       Linear: [ISSUE-XXX](enlace-al-issue)
       
       ## Descripción
       [Descripción del issue]
       
       ## Estado
       - [ ] Issue creado en Linear
       - [ ] PR preparado
       - [ ] Pendiente de implementación
       ```
     - Marcar como draft
   - Vincular PR al issue usando `update_issue` con parámetro `links`

IF NO THEN:
- Omitir este paso

### Paso 7: Gestionar Status

Status disponibles: `Backlog`, `Todo`, `In Progress`, `In Review`, `Done`, `Canceled`, `Duplicate`

Status por fase:
- Backlog: Tareas pendientes de planificación
- Todo: Tareas listas para comenzar (default al crear)
- In Progress: Tareas en desarrollo activo
- In Review: Tareas completadas esperando revisión
- Done: Tareas completadas y aprobadas

Reglas:
- Issues que dependen de otros: `Todo` hasta que dependencias estén `Done`
- Issues que bloquean a otros: Prioridad alta
- Issues en paralelo: Pueden estar `In Progress` simultáneamente

## Herramientas MCP

### Crear Issue

Herramienta: `create_issue`

Parámetros principales:
- `title` (requerido): Título del issue
- `team` (requerido): Nombre o ID del equipo
- `description` (opcional): Descripción en Markdown
- `assignee` (opcional): Email del usuario o "me"
- `priority` (opcional): 1=Urgent, 2=High, 3=Normal, 4=Low
- `labels` (opcional): Array de nombres de labels (intuir apropiados)
- `parentId` (opcional): ID del issue padre para crear sub-issue
- `state` (opcional): Estado inicial (`"Backlog"`, `"Todo"`, etc.)
- `project` (opcional): ID o nombre del proyecto (intuir si no especificado)
- `links` (opcional): Array de objetos `{url: string, title: string}` para vincular PRs

### Otras Herramientas

- `list_issue_labels`: Listar labels existentes
- `create_issue_label`: Crear nuevo label si no existe
- `list_issues`: Listar issues con filtros
- `update_issue`: Actualizar estado, prioridad, descripción, links
- `list_projects`: Buscar proyectos relacionados
- `list_issue_statuses`: Ver status disponibles para un equipo

## Ejemplos

### Ejemplo 1: Issue Simple

Tarea: "Crear issue para agregar validación de email en formulario de registro"

Proceso:
1. Analizar: Validación de email, tarea simple
2. VERIFICAR: ¿Requiere división? [NO]
3. Intuir labels: `feature`, `frontend`, `validation`
4. Crear issue:
   - Título: `feature: Add email validation to registration form`
   - Descripción con objetivo, contexto, requisitos, criterios
   - Labels: `feature`, `frontend`
   - Prioridad: Normal (3)
5. VERIFICAR: ¿Hay repositorio? [SI/NO]
   - IF SI → Crear PR vacío/draft y vincular
6. FIN

### Ejemplo 2: Tarea Grande (Epic)

Tarea: "Implementar sistema de autenticación completo"

Proceso:
1. Analizar: Sistema completo, múltiples componentes
2. VERIFICAR: ¿Requiere división? [SI]
3. Crear Epic:
   - Título: `epic: Authentication system implementation`
   - Descripción: Visión general del sistema
4. Crear sub-issues:
   - `feature: Design authentication architecture`
   - `feature: Implement OAuth2 backend endpoints`
   - `feature: Create login UI components`
   - `feature: Add session management`
   - `feature: Write authentication tests`
5. Gestionar dependencias entre sub-issues
6. Crear PRs vacíos/draft para cada issue (si hay repositorio)
7. FIN

## Checklist de Verificación

Antes de finalizar, verificar:

- [ ] ¿Comprendo completamente la tarea?
- [ ] ¿He aclarado todas las dudas necesarias?
- [ ] ¿He identificado si la tarea requiere división?
- [ ] ¿He identificado todas las dependencias?
- [ ] ¿He intuido los labels apropiados?
- [ ] ¿He verificado existencia de labels y creado los faltantes?
- [ ] ¿El título es descriptivo y claro?
- [ ] ¿La descripción incluye toda la información necesaria?
- [ ] ¿Está asignado al equipo correcto?
- [ ] ¿La prioridad es apropiada?
- [ ] ¿He establecido dependencias correctamente (parentId si aplica)?
- [ ] ¿He asignado el status apropiado?
- [ ] ¿He verificado si hay repositorio disponible?
- [ ] ¿He creado PRs vacíos/draft y vinculado a issues (si hay repositorio)?
- [ ] ¿He creado todos los issues solicitados en Linear?
- [ ] VERIFICAR: ¿He intentado implementar o escribir código? [SI/NO]
  - IF SI → DETENTE. Eso es para `/complete-issues`
  - IF NO → FIN. Tu trabajo ha terminado.

## Manejo de Errores

Si falla la creación de un issue:
1. VERIFICAR: ¿El error es por parámetros inválidos? [SI/NO]
   - IF SI → Revisar parámetros, corregir y reintentar
   - IF NO → Continuar
2. VERIFICAR: ¿El error es por label inexistente? [SI/NO]
   - IF SI → Crear label faltante y reintentar
   - IF NO → Continuar
3. VERIFICAR: ¿El error es por proyecto inexistente? [SI/NO]
   - IF SI → Omitir proyecto o crear uno nuevo si es apropiado
   - IF NO → Continuar
4. Si el error persiste, informar al usuario con detalles del error

## Recordatorios Finales

Tu trabajo TERMINA cuando:
- Has creado todos los issues solicitados en Linear
- Has creado PRs vacíos/draft y vinculado a issues (si hay repositorio)

NO continúes con:
- Implementación de código
- Escritura de código
- Creación de archivos de código
- Commits con código
- Trabajo en la tarea

Para implementar issues, el usuario debe usar `/complete-issues` explícitamente.
