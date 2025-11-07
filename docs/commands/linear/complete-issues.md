   # Completar Issues Profesionalmente

Guía profesional para completar issues en Linear actuando como un programador/project manager experto. **NO solo marques el issue como "Done"**. Completa el trabajo de manera profesional, implementando la solución completa, trabajando con GitHub, poniéndolo en "In Review" para revisión, y verificando que todo esté correcto antes de marcar como "Done".

> **⚠️ IMPORTANTE:** Antes de usar este comando, lee el [documento de contexto del proyecto](../../project-context.md) para obtener información actualizada sobre el proyecto y trabajo en Linear. Este documento es la fuente única de verdad para contexto del proyecto. Si el documento no existe, usa el [comando de inicialización](./initialize-project-context.md) para crearlo.

## Filosofía: Completar Profesionalmente

Cuando completes un issue, **NO** solo lo marques como "Done". Actúa como un **programador profesional** que:

1. **⚠️ SIEMPRE mueve a "In Progress"** al iniciar el trabajo en el issue
2. **Analiza el issue completamente** antes de empezar
3. **⚠️ Intuye el proyecto** si el issue no tiene proyecto asignado - busca proyectos relacionados en Linear
4. **Aclara dudas** si algo no está claro
5. **SIEMPRE trabaja con branches y Pull Requests** cuando sea posible (nunca en main/master directamente)
6. **Implementa la solución completa** con código real
7. **Verifica que funciona** antes de poner en revisión
8. **SIEMPRE mueve a "In Review"** después de implementar - NO marques como "Done" sin visto bueno
9. **NUNCA marques como "Done"** sin aprobación explícita del usuario
10. **Documenta el trabajo** realizado

## Proceso Profesional de Completar Issues

### Paso 1: Análisis Profundo del Issue y Marcar como "In Progress"

**⚠️ REGLA CRÍTICA: NADA MÁS INICIAR EL TRABAJO, mueve el issue a "In Progress":**

1. **Obtener detalles completos del issue**
   - Usa: `get_issue`
   - Parámetros: `id` (ID del issue, ej: "ISSUE-123")
   - Revisa toda la información retornada: título, descripción, estado, asignado, labels, etc.

2. **⚠️ ACTUALIZAR INMEDIATAMENTE A "In Progress":**
   - Usa: `update_issue` con `id` (ID del issue), `state: "In Progress"`
   - **Hazlo NADA MÁS empezar a trabajar en el issue**
   - Esto indica que el trabajo ha comenzado

3. **⚠️ Intuir proyecto si falta:**
   - Si el issue no tiene proyecto asignado, busca proyectos relacionados usando `list_projects`
   - Analiza el contexto del issue (título, descripción, labels, equipo) para identificar proyectos relevantes
   - Si hay un proyecto activo relacionado, actualiza el issue con `update_issue` y parámetro `project`

4. **Analizar el contenido:**
   - ¿Qué requiere exactamente el issue?
   - ¿Hay criterios de aceptación claros?
   - ¿Hay dependencias o sub-issues?
   - ¿Hay referencias a código existente?
   - ¿Hay contexto técnico suficiente?

5. **Aclarar dudas con el usuario si es necesario:**
   - ¿Hay algún estilo de código específico que deba seguir?
   - ¿Hay algún framework o biblioteca preferida?
   - ¿Requiere tests? ¿Qué nivel de cobertura?

6. **Verificar dependencias:**
   - ¿Hay sub-issues que deben completarse primero?
   - ¿Hay issues padre que dependen de este?
   - ¿Hay issues relacionados que deba considerar?

### Paso 2: Decisión de Repositorio vs Archivos Simples

**Evalúa si necesitas un repositorio o basta con crear archivos:**

#### Criterios para Crear Repositorio

**SÍ necesitas crear/inicializar un repositorio cuando:**
- El issue requiere control de versiones (Git)
- El issue implica múltiples archivos relacionados
- El issue requiere trabajo colaborativo o revisión de código
- El issue es parte de un proyecto existente que usa Git
- El issue requiere historial de cambios y commits
- El issue necesita integración con CI/CD o workflows
- El issue requiere crear Pull Requests para revisión

**NO necesitas crear repositorio cuando:**
- El issue es muy simple (1-2 archivos independientes)
- El issue solo requiere crear scripts o configuraciones simples
- El issue es una tarea única sin necesidad de versionado
- El usuario solo necesita los archivos creados sin historial Git

#### Identificar Carpeta de Destino

**Antes de crear archivos, identifica la ubicación correcta:**

1. **Analizar estructura del proyecto:**
   - Revisar estructura de directorios existente
   - Identificar patrones de organización (frontend/backend, src/lib, etc.)
   - Verificar convenciones del proyecto

2. **Determinar carpeta apropiada:**
   - Para código: `src/`, `lib/`, `app/`, `components/`, según estructura
   - Para tests: `tests/`, `__tests__/`, `spec/`, según convención
   - Para configuración: raíz del proyecto o `.config/`
   - Para documentación: `docs/`, `documentation/`, o raíz

3. **Si no estás seguro de la carpeta:**
   - Preguntar al usuario: "¿En qué carpeta debo crear [archivo]?"

4. **Seguir convenciones del proyecto:**
   - Si existe `src/components/`, crear componentes ahí
   - Si existe `src/services/`, crear servicios ahí
   - Si existe `tests/`, crear tests ahí

### Paso 3: Integración con GitHub (si aplica)

**Trabajar profesionalmente con control de versiones cuando sea necesario:**

#### Verificar Repositorio Existente

1. **Verificar si existe repositorio:**
   - Revisar si hay un repositorio Git en el proyecto actual
   - Verificar si hay un repositorio remoto configurado

2. **Si NO existe repositorio pero el issue lo requiere:**
   - Inicializar repositorio Git local
   - Crear `.gitignore` apropiado
   - Crear README inicial

#### Trabajar con Ramas y Pull Requests

**⚠️ REGLA CRÍTICA: SIEMPRE usa branches y Pull Requests cuando sea posible - NUNCA trabajes directamente en `main` o `master`:**

1. **Crear rama desde el issue:**
   ```bash
   git checkout -b feature/ISSUE-123-authentication-endpoint
   # o
   git checkout -b fix/ISSUE-124-login-bug
   ```

2. **Convenciones de nombres de ramas:**
   - `feature/ISSUE-123-descripcion-corta`
   - `fix/ISSUE-124-descripcion-bug`
   - `refactor/ISSUE-125-descripcion-refactor`
   - `docs/ISSUE-126-descripcion-docs`
   - `chore/ISSUE-127-descripcion-chore`

3. **Proceso obligatorio:**
   ```bash
   # 1. Asegurarse de estar en main/master actualizado
   git checkout main
   git pull origin main
   
   # 2. Crear rama desde el issue
   git checkout -b feature/ISSUE-123-nombre-descriptivo
   
   # 3. Trabajar en la rama
   # ... implementar código ...
   
   # 4. Commit y push a la rama
   git commit -m "feat: Implementación para ISSUE-123"
   git push origin feature/ISSUE-123-nombre-descriptivo
   
   # 5. Crear Pull Request (siempre que sea posible)
   ```

4. **Crear Pull Request:**
   - **SIEMPRE** crea un Pull Request cuando trabajes con Git
   - Enlaza el PR con el issue en Linear
   - Menciona el PR en el comentario del issue

### Paso 4: Implementación Completa

**Implementar la solución profesionalmente:**

1. **Identificar ubicación de archivos:**
   - Analizar estructura del proyecto para determinar carpeta apropiada
   - Si no está claro, preguntar al usuario
   - Seguir convenciones del proyecto

2. **Implementar el código:**
   - Crear archivos en la carpeta identificada o confirmada
   - Escribir código limpio y bien estructurado
   - Seguir las convenciones del proyecto
   - Añadir comentarios cuando sea necesario
   - Documentar funciones/métodos importantes

3. **Añadir tests si aplica:**
   - Tests unitarios para funciones críticas
   - Tests de integración si es necesario
   - Verificar que los tests pasan

4. **Verificar que funciona:**
   - Probar manualmente la funcionalidad
   - Verificar que cumple los criterios de aceptación
   - Verificar que no rompe funcionalidad existente

### Paso 5: Commits y Pull Requests

**⚠️ IMPORTANTE: Siempre trabaja en branches y crea Pull Requests:**

1. **Commits profesionales:**
   ```bash
   git commit -m "feat: Implement authentication endpoint

   Closes #ISSUE-123"
   ```

2. **Push a la rama:**
   ```bash
   git push origin feature/ISSUE-123-authentication-endpoint
   ```

3. **Crear Pull Request:**
   - **SIEMPRE** crea un Pull Request cuando trabajes con Git
   - Enlaza el PR con el issue: `Closes #ISSUE-123`
   - Menciona el PR en el comentario del issue en Linear

### Paso 6: Completar el Issue y Poner en Revisión

**⚠️ REGLA CRÍTICA: SIEMPRE mueve a "In Review" - NUNCA marques como "Done" sin visto bueno del usuario:**

#### Checklist Antes de Marcar como In Review

- [ ] ¿El código está implementado completamente?
- [ ] ¿Los tests pasan (si aplica)?
- [ ] ¿Funciona correctamente?
- [ ] ¿Está commiteado y pusheado a una rama?
- [ ] ¿Se ha creado un Pull Request?
- [ ] ¿Está documentado el trabajo realizado?

#### Proceso de Completar y Poner en Revisión

1. **SIEMPRE actualizar estado a "In Review":**
   - Usa: `update_issue` con `id` (ID del issue), `state: "In Review"`
   - **NUNCA** marques como "Done" sin aprobación explícita del usuario
   - Nota: Usa `list_issue_statuses` con el `team` para verificar los estados disponibles

2. **Añadir comentario profesional con resumen:**
   - Usa: `create_comment`
   - Incluye: resumen de cambios, referencias a commits/PRs, verificación
   - Menciona que está listo para revisión y esperando aprobación
   - **IMPORTANTE**: Siempre añade al final: `---\n_Hecho por Cursor_`

3. **Mencionar Pull Request:**
   - Si se creó un PR, menciona el enlace al PR en el comentario
   - Enlaza el PR con el issue en GitHub/GitLab

### Paso 7: Revisar Issue en "In Review"

**⚠️ REGLA CRÍTICA: NUNCA marques como "Done" sin aprobación explícita del usuario:**

#### Proceso de Revisión

1. **Verificar estado del issue:**
   - Obtener issue: Usa `get_issue` con `id` (ID del issue)
   - Verificar que está en estado "In Review"
   - Revisar código implementado y Pull Request

2. **Ejecutar tests y verificar:**
   - Ejecutar tests existentes
   - Verificar que todos los tests pasan
   - Si algún test falla, documentar el problema en un comentario

3. **Completar revisión:**
   - **NUNCA** actualices a "Done" sin aprobación explícita del usuario
   - Si todo está correcto, añade comentario de revisión con resultados
   - Espera aprobación del usuario antes de marcar como "Done"
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

### Paso 8: Actualizar Issue Padre (si aplica)

**Si completaste un sub-issue:**

1. **Verificar progreso del issue padre:**
   - Obtén el issue padre: `get_issue` con `id` del `parentId`
   - Lista sub-issues: `list_issues` con `parentId` del issue padre
   - Calcula progreso: cuenta cuántos sub-issues tienen `state: "Done"` vs total

2. **Actualizar issue padre con progreso:**
   - Actualiza descripción: `update_issue` con `id` del padre y `description` actualizada incluyendo sección de progreso
   - Añade comentario: `create_comment` con `issueId` del padre y mensaje de progreso
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

## Herramientas de Referencia

### Obtener Issue

**Herramienta:** `get_issue`

**Parámetros:**
- `id` (requerido): ID del issue (ej: "ISSUE-123")

**Retorna:** Información completa del issue incluyendo título, descripción, estado, asignado, labels, parentId, etc.

### Actualizar Issue

**Herramienta:** `update_issue`

**Parámetros:**
- `id` (requerido): ID del issue
- `state` (opcional): Nuevo estado (ej: "Done", "In Progress")
- `description` (opcional): Descripción actualizada
- `assignee` (opcional): Nuevo asignado
- `priority` (opcional): Nueva prioridad (1=Urgent, 2=High, 3=Normal, 4=Low)
- `labels` (opcional): Array de labels actualizados
- `dueDate` (opcional): Nueva fecha de vencimiento

### Añadir Comentario

**Herramienta:** `create_comment`

**Parámetros:**
- `issueId` (requerido): ID del issue
- `body` (requerido): Contenido del comentario (soporta Markdown)
- `parentId` (opcional): ID de comentario padre para respuestas

**IMPORTANTE - Formato de Comentarios:**
- **Siempre** incluye al final de cada comentario: `---\n_Hecho por Cursor_`
- Esto indica que el trabajo fue realizado por Cursor y permite tracking

### Listar Issues (Incluye Sub-issues)

**Herramienta:** `list_issues`

**Parámetros útiles:**
- `parentId`: Filtrar por issue padre (para obtener sub-issues)
- `team`: Filtrar por equipo
- `state`: Filtrar por estado
- `assignee`: Filtrar por asignado
- `priority`: Filtrar por prioridad
- `label`: Filtrar por label
- `project`: Filtrar por proyecto

### Listar Estados Disponibles

**Herramienta:** `list_issue_statuses`

**Parámetros:**
- `team` (requerido): Nombre o ID del equipo

**Retorna:** Lista de estados disponibles para el equipo, incluyendo nombres y tipos

**Uso:** Úsalo para verificar qué estados están disponibles antes de actualizar un issue, especialmente para verificar si "In Review" existe en el equipo

## Checklist de Profesionalismo

### ⚠️ Al Iniciar el Trabajo

**REGLA CRÍTICA: NADA MÁS INICIAR EL TRABAJO, actualiza a "In Progress":**

- [ ] ⚠️ **¿He actualizado el issue a "In Progress"?** (OBLIGATORIO al iniciar)
- [ ] ¿He analizado completamente el issue?
- [ ] ¿He creado una rama para el trabajo? (SIEMPRE)
- [ ] ¿He verificado dependencias?

### Antes de Marcar como "In Review"

Antes de poner un issue en "In Review", verifica:

- [ ] ¿El issue está en "In Progress"? (debe estar desde el inicio)
- [ ] ¿He implementado el código completamente?
- [ ] ¿Funciona correctamente?
- [ ] ¿He creado un Pull Request? (SIEMPRE que sea posible)
- [ ] ¿He pusheado los cambios a la rama?
- [ ] ¿He documentado el trabajo en el comentario del issue?

### ⚠️ Al Revisar Issue en "In Review"

**REGLA CRÍTICA: NUNCA marques como "Done" sin aprobación explícita del usuario**

- [ ] ¿He verificado que el issue está en estado "In Review"?
- [ ] ¿He revisado el código y Pull Request?
- [ ] ¿He ejecutado los tests existentes?
- [ ] ¿Todos los tests pasan?
- [ ] ¿He añadido comentario de revisión con resultados?
- [ ] ⚠️ **NO he marcado como "Done"** - Esperando aprobación del usuario
- [ ] ¿He incluido "_Hecho por Cursor_" al final del comentario?

## Consejos Finales

1. **⚠️ SIEMPRE mueve a "In Progress"** - NADA MÁS iniciar el trabajo en el issue
2. **⚠️ SIEMPRE usa branches y Pull Requests** - Nunca trabajes directamente en main/master
3. **⚠️ SIEMPRE mueve a "In Review"** - No marques como "Done" sin visto bueno del usuario
4. **⚠️ NUNCA marques como "Done"** - Solo después de aprobación explícita del usuario
5. **Crea Pull Requests siempre que sea posible** - Facilita revisión y colaboración
6. **Aclara dudas antes y durante** - Mejor preguntar que asumir
7. **Verifica que funciona** - No solo implementes, prueba
8. **Documenta el trabajo** - Comentarios profesionales en el issue
9. **SIEMPRE incluye "_Hecho por Cursor_" en comentarios** - Permite tracking y transparencia
