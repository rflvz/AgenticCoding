# Crear Proyectos Completos con Issues Iniciales

Guía profesional para crear proyectos completos en Linear con issues iniciales estructurados, actuando como un project manager/programador experto, no solo como un usuario básico del MCP.

## Filosofía: Proyecto Completo desde el Inicio

Cuando crees un proyecto, **NO** solo uses el MCP de Linear para crear un proyecto vacío. Actúa como un **project manager profesional** que:

1. **Analiza profundamente** el alcance del proyecto
2. **Planifica estratégicamente** la estructura inicial
3. **Identifica issues iniciales** necesarios para arrancar
4. **Organiza jerárquicamente** con epics y sub-issues
5. **Crea recursos necesarios** (labels, proyectos, etc.) si no existen
6. **Establece dependencias** y flujo de trabajo
7. **Aclara dudas** antes de proceder

## Proceso de Creación Profesional de Proyectos

### Paso 1: Análisis Profundo del Proyecto

**ANTES de crear el proyecto:**

1. **Comprende completamente** qué proyecto se necesita
   - Lee y analiza la solicitud completa
   - Identifica objetivos, alcance y requisitos
   - Detecta componentes principales (frontend, backend, API, etc.)
   - Identifica stakeholders y equipos involucrados

2. **Aclara dudas con el usuario:**
   ```
   Antes de crear el proyecto, necesito aclarar:
   - ¿Cuál es el objetivo principal del proyecto?
   - ¿Cuál es el alcance y duración estimada?
   - ¿Qué equipos estarán involucrados?
   - ¿Hay deadlines o fechas importantes?
   - ¿Existen dependencias con otros proyectos?
   - ¿Qué fases o milestones tiene el proyecto?
   - ¿Hay requisitos técnicos específicos?
   - ¿Qué issues iniciales necesitamos para arrancar?
   ```

3. **Identifica el alcance del proyecto:**
   - ¿Es un proyecto pequeño (1-2 semanas)?
   - ¿Es un proyecto mediano (1-3 meses)?
   - ¿Es un proyecto grande (3+ meses)?
   - ¿Requiere múltiples fases o milestones?

### Paso 2: Planificar Estructura del Proyecto

**Definir la estructura antes de crear:**

1. **Identificar fases del proyecto:**
   - Fase 1: Diseño y planificación
   - Fase 2: Implementación core
   - Fase 3: Integración y testing
   - Fase 4: Documentación y deploy
   - (Adaptar según el proyecto)

2. **Identificar componentes principales:**
   - Frontend
   - Backend
   - API
   - Base de datos
   - Infraestructura
   - Documentación
   - Testing

3. **Identificar tipos de trabajo inicial:**
   - Setup y configuración inicial
   - Diseño arquitectónico
   - Implementación de features core
   - Tests y validación
   - Documentación

### Paso 3: Crear el Proyecto

**Crear el proyecto con información completa:**

#### Información del Proyecto

1. **Nombre descriptivo:**
   - Ejemplo: `"Sistema de Autenticación OAuth2"` o `"Refactorización de API Principal"`

2. **Summary (resumen):**
   - Descripción concisa (máximo 255 caracteres)
   - Ejemplo: `"Implementar sistema completo de autenticación OAuth2 con soporte multi-proveedor"`

3. **Descripción completa:**
   ```markdown
   ## Objetivo del Proyecto
   [Objetivo principal y visión general]
   
   ## Alcance
   - [Componente 1]
   - [Componente 2]
   - [Componente 3]
   
   ## Fases
   1. **Fase 1 - [Nombre]**: [Descripción]
   2. **Fase 2 - [Nombre]**: [Descripción]
   3. **Fase 3 - [Nombre]**: [Descripción]
   
   ## Equipos Involucrados
   - [Equipo 1]: Responsable de [área]
   - [Equipo 2]: Responsable de [área]
   
   ## Fechas Importantes
   - Inicio: [Fecha]
   - Target: [Fecha]
   - Milestones: [Fechas clave]
   
   ## Dependencias
   - Requiere: [Proyecto/Issue relacionado]
   - Bloquea: [Proyecto/Issue relacionado]
   ```

4. **Estado del proyecto:**
   - `planned`: Proyecto planificado pero no iniciado
   - `started`: Proyecto en progreso
   - `paused`: Proyecto pausado temporalmente
   - `completed`: Proyecto completado
   - `canceled`: Proyecto cancelado

5. **Fechas:**
   - `startDate`: Fecha de inicio (formato ISO: "YYYY-MM-DD")
   - `targetDate`: Fecha objetivo de finalización (formato ISO: "YYYY-MM-DD")

6. **Prioridad:**
   - `1` = Urgent: Proyectos críticos que bloquean otros
   - `2` = High: Proyectos importantes
   - `3` = Medium: Proyectos regulares (default)
   - `4` = Low: Proyectos de menor prioridad

7. **Equipo:**
   - Asignar al equipo principal responsable

8. **Lead:**
   - Asignar líder del proyecto (usuario, email, o "me")

9. **Labels:**
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
     - **Tipo de proyecto**: `feature-project` (si es nueva funcionalidad), `refactor-project` (si es refactorización), `infrastructure-project` (si es infraestructura), `migration-project` (si es migración)
     - **Área afectada**: `frontend` (si involucra UI), `backend` (si involucra servidor), `api` (si involucra API), `database` (si involucra BD), `infrastructure` (si involucra infraestructura)
     - **Prioridad**: `critical` (si bloquea producción), `high-priority` (si es importante), `low-priority` (si es menor)
   - Usa máximo 5 labels por proyecto

2. **Listar labels existentes:**
   - Usa: `list_project_labels` (para labels de proyectos)
   - O usa: `list_issue_labels` (para labels de issues, que pueden aplicarse también a proyectos)
   - Revisa la lista de labels retornada

3. **Verificar si los labels intuidos existen:**
   - Si el label existe en la lista: úsalo directamente
   - Si el label NO existe: créalo

4. **Crear labels si hacen falta:**
   - Para labels de proyectos: `create_project_label`
   - Para labels de issues: `create_issue_label`
   - Parámetros requeridos: `name` (nombre del label)
   - Parámetros opcionales: `description`, `color` (formato hexadecimal, ej: "#FF5733"), `teamId` (si no se proporciona, será workspace-wide)

**Ejemplos de intuición de labels:**

- **Proyecto**: "Implementar sistema de autenticación OAuth2"
  - Labels intuidos: `feature-project`, `backend`, `api`, `high-priority`

- **Proyecto**: "Refactorizar arquitectura de base de datos"
  - Labels intuidos: `refactor-project`, `database`, `infrastructure`

- **Proyecto**: "Migrar frontend a React 18"
  - Labels intuidos: `migration-project`, `frontend`

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
   ```
   He identificado estos issues iniciales para el proyecto:
   
   **Setup y Configuración:**
   - [Issue 1]
   - [Issue 2]
   
   **Diseño:**
   - [Issue 3]
   - [Issue 4]
   
   **Implementación Core:**
   - [Issue 5]
   - [Issue 6]
   
   ¿Quieres que añada, modifique o elimine algún issue?
   ```

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
     ├── docs: Diseño de base de datos
     └── docs: Diseño de API
   
   Epic: Implementación core
     ├── feature: [Feature principal 1]
     ├── feature: [Feature principal 2]
     └── feature: [Feature principal 3]
   ```

#### Crear Issues con Información Completa

**Para cada issue inicial:**

1. **Título profesional:**
   - Formato: `[Type]: [Descripción clara y específica]`
   - Ejemplos:
     - ✅ `chore: Configurar repositorio Git y CI/CD`
     - ✅ `docs: Diseño arquitectónico de autenticación`
     - ✅ `feature: Implementar endpoint de login`
     - ❌ `Setup`
     - ❌ `Config`
     - ❌ `Feature`

2. **Descripción completa:**
   ```markdown
   ## Objetivo
   [Qué queremos lograr]
   
   ## Contexto
   [Por qué es necesario en el contexto del proyecto]
   
   ## Requisitos
   - [Requisito 1]
   - [Requisito 2]
   - [Requisito 3]
   
   ## Criterios de Aceptación
   - [ ] Criterio 1
   - [ ] Criterio 2
   - [ ] Criterio 3
   
   ## Dependencias
   - Requiere: [Issue relacionado si aplica]
   - Bloquea: [Issue relacionado si aplica]
   - Puede ejecutarse en paralelo con: [Issue relacionado si aplica]
   
   ## Notas Técnicas
   [Información técnica relevante]
   
   ## Relacionado
   Parte del proyecto: [Nombre del proyecto]
   ```

3. **Vincular al proyecto:**
   - Usa: `create_issue` con parámetro `project` (ID o nombre del proyecto creado)

4. **Asignación inteligente:**
   - Asigna al **equipo correcto** según el tipo de trabajo
   - Asigna a **persona específica** si conoces sus habilidades
   - Usa `"me"` para auto-asignación cuando sea apropiado

5. **Priorización estratégica:**
   - `Urgent`: Solo para issues que bloquean el inicio del proyecto
   - `High`: Issues críticos para el proyecto
   - `Normal`: Issues regulares (default)
   - `Low`: Issues que pueden esperar

6. **Labels:**
   - Intuye los labels apropiados basándote en el contenido (ver proceso en `create-issues.md`)
   - Crea labels si no existen

7. **Jerarquía:**
   - Si es un sub-issue: usa `parentId` (ID del Epic padre)
   - Si es un Epic: no uses `parentId`

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
- `dueDate` (opcional): Fecha en formato "YYYY-MM-DD"
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
   - Añade la sección de dependencias a la descripción

### Paso 8: Verificación y Documentación

**Verificar que todo esté correcto:**

#### Checklist de Verificación

- [ ] ¿El proyecto está creado con información completa?
- [ ] ¿Los labels están creados y asignados?
- [ ] ¿Los issues iniciales están creados y vinculados al proyecto?
- [ ] ¿Las dependencias están documentadas?
- [ ] ¿Los issues están organizados jerárquicamente (Epics y sub-issues)?
- [ ] ¿Las prioridades son apropiadas?
- [ ] ¿Las asignaciones son correctas?
- [ ] ¿Las fechas están establecidas?

#### Actualizar Proyecto con Resumen

1. **Actualizar descripción del proyecto:**
   - Añade sección de "Issues Iniciales" con lista de issues creados
   - Añade sección de "Progreso" para tracking

2. **Ejemplo de actualización:**
   ```markdown
   ## Issues Iniciales
   
   **Setup y Configuración:**
   - ISSUE-123: Configurar repositorio Git y CI/CD
   - ISSUE-124: Configurar entornos de desarrollo
   
   **Diseño:**
   - ISSUE-125: Diseño arquitectónico de autenticación
   - ISSUE-126: Diseño de base de datos
   
   **Implementación Core:**
   - ISSUE-127: Implementar endpoint de login
   - ISSUE-128: Implementar endpoint de registro
   
   ## Progreso
   - Total de issues: 6
   - Completados: 0
   - En progreso: 0
   - Pendientes: 6
   ```

3. **Actualizar proyecto:**
   - Usa: `update_project` con `id` del proyecto y `description` actualizada

## Ejemplos de Uso Profesional

### Ejemplo 1: Crear Proyecto Completo de Autenticación

**Usuario:** "Necesitamos crear un proyecto para implementar sistema de autenticación OAuth2"

**Proceso del agente:**

1. **Aclarar dudas:**
   ```
   Antes de crear el proyecto, necesito aclarar:
   - ¿Cuál es el alcance completo? (solo login, o también registro, recuperación de contraseña, etc.)
   - ¿Qué proveedores OAuth2 necesitamos? (Google, GitHub, etc.)
   - ¿Cuál es el deadline?
   - ¿Qué equipos estarán involucrados?
   - ¿Hay algún sistema de autenticación existente?
   ```

2. **Crear proyecto:**
   - Usa: `create_project`
   - Parámetros: `name`, `team`, `summary`, `description`, `state`, `startDate`, `targetDate`, `priority`, `lead`, `labels` (intuye labels apropiados)

3. **Identificar issues iniciales:**
   - Setup: Configurar proyecto, repositorio, CI/CD
   - Diseño: Diseño arquitectónico, diseño de API, diseño de BD
   - Implementación: Endpoints de autenticación, integración OAuth2, gestión de tokens
   - Testing: Tests unitarios, tests de integración
   - Documentación: Documentación técnica, guía de usuario

4. **Crear Epics y issues:**
   - Epic: Setup inicial (con sub-issues)
   - Epic: Diseño arquitectónico (con sub-issues)
   - Epic: Implementación core (con sub-issues)
   - Epic: Testing (con sub-issues)
   - Epic: Documentación (con sub-issues)
   - Todos vinculados al proyecto con `project`

5. **Establecer dependencias:**
   - Diseño debe completarse antes de implementación
   - Setup debe completarse primero
   - Documentación puede esperar hasta el final

6. **Verificar y actualizar:**
   - Actualizar proyecto con resumen de issues
   - Verificar que todo esté vinculado correctamente

### Ejemplo 2: Crear Proyecto de Refactorización

**Usuario:** "Crear proyecto para refactorizar la API principal"

**Proceso del agente:**

1. **Aclarar dudas:**
   ```
   Antes de crear el proyecto, necesito aclarar:
   - ¿Qué partes de la API necesitan refactorización?
   - ¿Hay algún patrón específico que debamos seguir?
   - ¿Cuál es el objetivo principal? (performance, mantenibilidad, etc.)
   - ¿Hay algún deadline?
   ```

2. **Crear proyecto:**
   - Usa: `create_project` con información completa
   - Labels intuidos: `refactor-project`, `api`, `backend`

3. **Crear issues iniciales:**
   - docs: Análisis de la API actual
   - docs: Diseño de la nueva arquitectura
   - refactor: Refactorizar módulo X
   - refactor: Refactorizar módulo Y
   - chore: Tests de la refactorización
   - docs: Documentación actualizada

4. **Organizar jerárquicamente:**
   - Epic padre para cada módulo a refactorizar
   - Sub-issues para tareas específicas

## Herramientas de Referencia

### Crear Proyecto

**Herramienta:** `create_project`

**Parámetros disponibles:**
- `name` (requerido): Nombre del proyecto
- `team` (requerido): Nombre o ID del equipo
- `summary` (opcional): Resumen conciso (máx 255 chars)
- `description` (opcional): Descripción completa en Markdown
- `state` (opcional): Estado inicial (planned, started, paused, completed, canceled)
- `startDate` (opcional): Fecha de inicio (ISO: "YYYY-MM-DD")
- `targetDate` (opcional): Fecha objetivo (ISO: "YYYY-MM-DD")
- `priority` (opcional): 1=Urgent, 2=High, 3=Medium, 4=Low
- `lead` (opcional): Email del líder o "me"
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados**

### Actualizar Proyecto

**Herramienta:** `update_project`

**Parámetros:**
- `id` (requerido): ID del proyecto
- `name` (opcional): Nuevo nombre
- `summary` (opcional): Nuevo resumen
- `description` (opcional): Nueva descripción
- `state` (opcional): Nuevo estado
- `startDate` (opcional): Nueva fecha de inicio
- `targetDate` (opcional): Nueva fecha objetivo
- `priority` (opcional): Nueva prioridad
- `lead` (opcional): Nuevo líder
- `labels` (opcional): Array de labels actualizados

### Obtener Proyecto

**Herramienta:** `get_project`

**Parámetros:**
- `query` (requerido): ID o nombre del proyecto

### Listar Proyectos

**Herramienta:** `list_projects`

**Parámetros útiles:**
- `team`: Filtrar por equipo
- `state`: Filtrar por estado
- `member`: Filtrar por miembro
- `query`: Buscar por nombre

### Listar Labels de Proyectos

**Herramienta:** `list_project_labels`

**Parámetros opcionales:**
- Ninguno (retorna todos los labels de proyectos)

### Crear Label de Proyecto

**Herramienta:** `create_project_label`

**Parámetros requeridos:**
- `name`: Nombre del label

**Parámetros opcionales:**
- `description`: Descripción del label
- `color`: Color en formato hexadecimal (ej: "#FF5733")

### Crear Issue (con proyecto)

**Herramienta:** `create_issue`

**Parámetros relevantes para proyectos:**
- `title` (requerido): Título del issue
- `team` (requerido): Nombre o ID del equipo
- `project` (opcional): ID o nombre del proyecto (para vincular)
- `parentId` (opcional): ID del issue padre (para sub-issues)
- `description` (opcional): Descripción completa en Markdown
- `assignee` (opcional): Email del usuario o "me"
- `priority` (opcional): 1=Urgent, 2=High, 3=Normal, 4=Low
- `labels` (opcional): Array de nombres de labels - **INTUYE los labels apropiados**
- `dueDate` (opcional): Fecha en formato "YYYY-MM-DD"
- `state` (opcional): Estado inicial del issue

**Importante:** Para vincular issues al proyecto, usa el parámetro `project` con el ID o nombre del proyecto.

### Listar Issues de un Proyecto

**Herramienta:** `list_issues`

**Parámetros:**
- `project` (opcional): ID o nombre del proyecto para filtrar issues del proyecto

## Checklist de Profesionalismo

Antes de considerar un proyecto completo, verifica:

- [ ] ¿Comprendo completamente el proyecto que se necesita?
- [ ] ¿He aclarado todas las dudas necesarias?
- [ ] ¿El proyecto está creado con información completa (nombre, descripción, fechas, equipo, etc.)?
- [ ] ¿He intuido los labels apropiados basándome en el contenido? (crearlos si no existen)
- [ ] ¿He identificado los issues iniciales necesarios?
- [ ] ¿Los issues iniciales están creados y vinculados al proyecto?
- [ ] ¿Los issues están organizados jerárquicamente (Epics y sub-issues) cuando aplica?
- [ ] ¿Las dependencias están documentadas?
- [ ] ¿Las prioridades son apropiadas?
- [ ] ¿Las asignaciones son correctas?
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

