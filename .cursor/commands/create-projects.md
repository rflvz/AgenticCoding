# Crear Proyectos Completos con Issues Iniciales

Guía profesional para crear proyectos completos en Linear con issues iniciales estructurados.

## Filosofía: Proyecto Completo desde el Inicio

Cuando crees un proyecto, **NO** solo uses el MCP de Linear para crear un proyecto vacío. Actúa como un **project manager profesional** que:

1. **Analiza profundamente** el alcance del proyecto
2. **Planifica estratégicamente** la estructura inicial
3. **Identifica issues iniciales** necesarios para arrancar
4. **Organiza jerárquicamente** con epics y sub-issues
5. **Crea recursos necesarios** (labels, proyectos, etc.) si no existen
6. **Establece dependencias** y flujo de trabajo
7. **⚠️ Intuye el proyecto** para issues iniciales si no se especifica - busca proyectos relacionados en Linear

## Proceso de Creación Profesional de Proyectos

### Paso 1: Análisis Profundo del Proyecto

**ANTES de crear el proyecto:**

1. **Comprende completamente** qué proyecto se necesita
   - Lee y analiza la solicitud completa
   - Identifica objetivos, alcance y requisitos
   - Detecta componentes principales (frontend, backend, API, etc.)

2. **Aclara dudas con el usuario:**
   - ¿Cuál es el objetivo principal del proyecto?
   - ¿Cuál es el alcance y duración estimada?
   - ¿Qué equipos estarán involucrados?
   - ¿Hay deadlines o fechas importantes?
   - ¿Existen dependencias con otros proyectos?
   - ¿Qué issues iniciales necesitamos para arrancar?

3. **Identifica el alcance del proyecto:**
   - ¿Es un proyecto pequeño (1-2 semanas)?
   - ¿Es un proyecto mediano (1-3 meses)?
   - ¿Es un proyecto grande (3+ meses)?

### Paso 2: Planificar Estructura del Proyecto

**Definir la estructura antes de crear:**

1. **Identificar fases del proyecto:**
   - Fase 1: Diseño y planificación
   - Fase 2: Implementación core
   - Fase 3: Integración y testing
   - Fase 4: Documentación y deploy

2. **Identificar componentes principales:**
   - Frontend, Backend, API, Base de datos, Infraestructura, Documentación, Testing

3. **Identificar tipos de trabajo inicial:**
   - Setup y configuración inicial
   - Diseño arquitectónico
   - Implementación de features core
   - Tests y validación
   - Documentación

### Paso 3: Crear el Proyecto

**Crear el proyecto con información completa:**

#### Información del Proyecto

1. **Nombre descriptivo:** Ej: `"Sistema de Autenticación OAuth2"`

2. **Summary (resumen):** Descripción concisa (máximo 255 caracteres)

3. **Descripción completa:**
   ```markdown
   ## Objetivo del Proyecto
   [Objetivo principal y visión general]
   
   ## Alcance
   - [Componente 1]
   - [Componente 2]
   
   ## Fases
   1. **Fase 1 - [Nombre]**: [Descripción]
   2. **Fase 2 - [Nombre]**: [Descripción]
   
   ## Equipos Involucrados
   - [Equipo 1]: Responsable de [área]
   
   ## Fechas Importantes
   - Inicio: [Fecha]
   - Target: [Fecha]
   ```

4. **Estado del proyecto:**
   - `planned`: Proyecto planificado pero no iniciado
   - `started`: Proyecto en progreso
   - `paused`: Proyecto pausado temporalmente
   - `completed`: Proyecto completado
   - `canceled`: Proyecto cancelado

5. **Fechas:**
   - `startDate`: Fecha de inicio (formato ISO: "YYYY-MM-DD")
   - `targetDate`: Fecha objetivo (formato ISO: "YYYY-MM-DD")

6. **Prioridad:**
   - `1` = Urgent: Proyectos críticos que bloquean otros
   - `2` = High: Proyectos importantes
   - `3` = Medium: Proyectos regulares (default)
   - `4` = Low: Proyectos de menor prioridad

7. **Labels:**
   - Intuir labels apropiados basándote en el contenido del proyecto
   - Crear labels si no existen (ver Paso 4)

**Herramienta:** `create_project`

**Parámetros:**
- `name` (requerido): Nombre del proyecto
- `team` (requerido): Nombre o ID del equipo
- `summary` (opcional): Resumen conciso (máx 255 chars)
- `description` (opcional): Descripción completa en Markdown
- `state` (opcional): Estado inicial
- `startDate` (opcional): Fecha de inicio (ISO: "YYYY-MM-DD")
- `targetDate` (opcional): Fecha objetivo (ISO: "YYYY-MM-DD")
- `priority` (opcional): 1=Urgent, 2=High, 3=Medium, 4=Low
- `lead` (opcional): Email del líder o "me"
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados**

### Paso 4: Gestionar Labels Inteligentemente

**Intuir y gestionar labels basándote en la información del proyecto:**

#### Proceso:

1. **Intuir labels basándote en el contenido:**
   - **NO esperes** que el usuario te proporcione labels
   - **Analiza** el proyecto y determina qué labels son apropiados:
     - **Tipo de proyecto**: `feature-project`, `refactor-project`, `infrastructure-project`, `migration-project`
     - **Área afectada**: `frontend`, `backend`, `api`, `database`, `infrastructure`
     - **Prioridad**: `critical`, `high-priority`, `low-priority`
   - Usa máximo 5 labels por proyecto

2. **Listar labels existentes:**
   - Usa: `list_project_labels` (para labels de proyectos)
   - O usa: `list_issue_labels` (para labels de issues)
   - Revisa la lista de labels retornada

3. **Verificar si los labels intuidos existen:**
   - Si el label existe: úsalo directamente
   - Si el label NO existe: créalo

4. **Crear labels si hacen falta:**
   - Para labels de proyectos: `create_project_label`
   - Para labels de issues: `create_issue_label`
   - Parámetros: `name` (requerido), `description`, `color` (hex), `teamId` (opcional)

### Paso 5: Identificar Issues Iniciales

**Identificar qué issues iniciales son necesarios:**

#### Proceso de Identificación:

1. **Analizar el proyecto:**
   - ¿Qué tareas son críticas para arrancar?
   - ¿Qué setup inicial es necesario?
   - ¿Qué diseño arquitectónico requiere?
   - ¿Qué features core deben implementarse primero?

2. **Categorizar issues iniciales:**

   **Setup y Configuración:**
   - Setup inicial del proyecto
   - Configuración de herramientas
   - Configuración de CI/CD
   - Configuración de entornos

   **Diseño:**
   - Diseño arquitectónico
   - Diseño de base de datos
   - Diseño de API
   - Diseño de UI/UX

   **Implementación Core:**
   - Features principales
   - Integraciones críticas
   - Funcionalidades base

   **Testing:**
   - Setup de tests
   - Tests unitarios
   - Tests de integración

   **Documentación:**
   - Documentación técnica
   - Documentación de usuario
   - Guías de desarrollo

3. **Aclarar con el usuario:**
   - Presentar issues iniciales identificados
   - Confirmar si añadir, modificar o eliminar algún issue

### Paso 6: Crear Issues Iniciales

**Crear issues iniciales profesionalmente:**

#### Organización Jerárquica

1. **Si hay múltiples issues relacionados:**
   - Crear **Epic padre** para agrupar issues relacionados
   - Crear **sub-issues** bajo el Epic usando `parentId`
   - Vincular issues al proyecto usando `project`

2. **Estructura sugerida:**
   ```
   Epic: Setup inicial del proyecto
     ├── chore: Configurar repositorio Git
     ├── chore: Configurar CI/CD
     └── chore: Configurar entornos de desarrollo
   
   Epic: Diseño arquitectónico
     ├── docs: Diseño de arquitectura general
     └── docs: Diseño de base de datos
   ```

#### Crear Issues con Información Completa

**Para cada issue inicial:**

1. **Título profesional:** Formato: `[Type]: [Descripción clara y específica]`

2. **Descripción completa:**
   ```markdown
   ## Objetivo
   [Qué queremos lograr]
   
   ## Contexto
   [Por qué es necesario en el contexto del proyecto]
   
   ## Requisitos
   - [Requisito 1]
   - [Requisito 2]
   
   ## Criterios de Aceptación
   - [ ] Criterio 1
   - [ ] Criterio 2
   
   ## Dependencias
   - Requiere: [Issue relacionado si aplica]
   - Bloquea: [Issue relacionado si aplica]
   ```

3. **Vincular al proyecto:** Usa `create_issue` con parámetro `project` (ID o nombre del proyecto creado)

4. **Asignación y priorización:**
   - Asigna al **equipo correcto** según el tipo de trabajo
   - Prioridad: `Urgent` solo para issues que bloquean el inicio, `High` para críticos, `Normal` para regulares

5. **Labels:** Intuye los labels apropiados basándote en el contenido

6. **Jerarquía:** Si es un sub-issue: usa `parentId` (ID del Epic padre)

7. **Proyecto:**
   - **⚠️ Si el usuario no especifica el proyecto para los issues iniciales, intuye el proyecto creado**
   - Todos los issues iniciales deben estar vinculados al proyecto creado
   - Si hay proyectos relacionados existentes, puedes vincularlos también según el contexto

**Herramienta:** `create_issue`

**Parámetros relevantes:**
- `title` (requerido): Título del issue
- `team` (requerido): Nombre o ID del equipo
- `project` (opcional): ID o nombre del proyecto (para vincular)
- `parentId` (opcional): ID del issue padre (para sub-issues)
- `description` (opcional): Descripción completa en Markdown
- `assignee` (opcional): Email del usuario o "me"
- `priority` (opcional): 1=Urgent, 2=High, 3=Normal, 4=Low
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados**
- `state` (opcional): Estado inicial del issue

### Paso 7: Establecer Dependencias y Flujo

**Gestionar dependencias entre issues iniciales:**

1. **Identificar dependencias:**
   - ¿Qué issues deben completarse antes de otros?
   - ¿Hay bloques de issues que pueden ejecutarse en paralelo?
   - ¿Qué issues bloquean a otros?

2. **Documentar dependencias:**
   - Añade sección "Dependencias" en la descripción de cada issue
   - Usa formato: `- Requiere: ISSUE-123 (Nombre del issue)`
   - Usa formato: `- Bloquea: ISSUE-124 (Nombre del issue)`

3. **Priorizar según dependencias:**
   - Issues que bloquean a otros: Alta prioridad
   - Issues que pueden esperar: Prioridad normal/baja

4. **Actualizar issues con dependencias:**
   - Usa: `update_issue` con `id` del issue y `description` actualizada

### Paso 8: Verificación y Documentación

**Verificar que todo esté correcto:**

#### Checklist de Verificación

- [ ] ¿El proyecto está creado con información completa?
- [ ] ¿Los labels están creados y asignados?
- [ ] ¿Los issues iniciales están creados y vinculados al proyecto?
- [ ] ¿Las dependencias están documentadas?
- [ ] ¿Los issues están organizados jerárquicamente (Epics y sub-issues)?
- [ ] ¿Las prioridades son apropiadas?

#### Actualizar Proyecto con Resumen

1. **Actualizar descripción del proyecto:**
   - Añade sección de "Issues Iniciales" con lista de issues creados
   - Añade sección de "Progreso" para tracking

2. **Actualizar proyecto:**
   - Usa: `update_project` con `id` del proyecto y `description` actualizada

## Herramientas de Referencia

### Crear Proyecto

**Herramienta:** `create_project`

**Parámetros principales:**
- `name` (requerido): Nombre del proyecto
- `team` (requerido): Nombre o ID del equipo
- `summary` (opcional): Resumen conciso (máx 255 chars)
- `description` (opcional): Descripción completa en Markdown
- `state` (opcional): Estado inicial
- `startDate`, `targetDate` (opcional): Fechas (ISO: "YYYY-MM-DD")
- `priority` (opcional): 1=Urgent, 2=High, 3=Medium, 4=Low
- `lead` (opcional): Email del líder o "me"
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados**

### Gestionar Proyectos

- `update_project`: Actualizar proyecto
- `get_project`: Obtener proyecto por ID o nombre
- `list_projects`: Listar proyectos con filtros

### Gestionar Labels

- `list_project_labels`: Listar labels de proyectos
- `create_project_label`: Crear label de proyecto
- `list_issue_labels`: Listar labels de issues
- `create_issue_label`: Crear label de issue

### Crear Issues

- `create_issue`: Crear issue con `project` para vincular al proyecto
- `update_issue`: Actualizar issue con dependencias

## Checklist de Profesionalismo

Antes de considerar un proyecto completo, verifica:

- [ ] ¿Comprendo completamente el proyecto que se necesita?
- [ ] ¿He aclarado todas las dudas necesarias?
- [ ] ¿El proyecto está creado con información completa?
- [ ] ¿He intuido los labels apropiados? (crearlos si no existen)
- [ ] ¿He identificado los issues iniciales necesarios?
- [ ] ¿Los issues iniciales están creados y vinculados al proyecto?
- [ ] ¿Los issues están organizados jerárquicamente (Epics y sub-issues)?
- [ ] ¿Las dependencias están documentadas?
- [ ] ¿Las prioridades son apropiadas?
- [ ] ¿He actualizado el proyecto con resumen de issues iniciales?

## Consejos Finales

1. **Nunca crees proyectos vacíos** - Siempre identifica y crea issues iniciales
2. **Siempre analiza primero** - Sé un project manager, no un robot
3. **Organiza jerárquicamente** - Usa Epics para agrupar issues relacionados
4. **Gestiona dependencias proactivamente** - Identifica qué depende de qué
5. **Crea recursos si faltan** - Labels, proyectos, etc.
6. **Aclara dudas antes de crear** - Mejor preguntar que asumir
7. **Actúa como experto** - No solo uses el MCP, sé estratégico
8. **Vincula issues al proyecto** - Usa el parámetro `project` para mantener todo organizado
