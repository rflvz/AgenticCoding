# Completar Issues Profesionalmente

Guía profesional para completar issues en Linear actuando como un programador/project manager experto. **NO solo marques el issue como "Done"**. Completa el trabajo de manera profesional, implementando la solución completa, trabajando con GitHub, poniéndolo en "In Review" para revisión, y verificando que todo esté correcto antes de marcar como "Done".

## Filosofía: Completar Profesionalmente

Cuando completes un issue, **NO** solo lo marques como "Done". Actúa como un **programador profesional** que:

1. **Analiza el issue completamente** antes de empezar
2. **Aclara dudas** si algo no está claro
3. **Implementa la solución completa** con código real
4. **Trabaja con control de versiones** (Git/GitHub) profesionalmente
5. **Verifica que funciona** antes de poner en revisión
6. **Pone el issue en "In Review"** después de implementar para permitir revisión
7. **Revisa issues en "In Review"** con tests, detecta necesidad de tests y crea tests/issues relacionados
8. **Marca como "Done"** solo después de revisión completa y aprobación
9. **Documenta el trabajo** realizado

## Proceso Profesional de Completar Issues

### Paso 1: Análisis Profundo del Issue

**ANTES de empezar a trabajar:**

1. **Obtener detalles completos del issue**
   - Usa: `get_issue`
   - Parámetros: `id` (ID del issue, ej: "ISSUE-123")
   - Revisa toda la información retornada: título, descripción, estado, asignado, labels, etc.

2. **Analizar el contenido:**
   - ¿Qué requiere exactamente el issue?
   - ¿Hay criterios de aceptación claros?
   - ¿Hay dependencias o sub-issues?
   - ¿Hay referencias a código existente?
   - ¿Hay contexto técnico suficiente?

3. **Aclarar dudas con el usuario si es necesario:**
   ```
   Antes de empezar a trabajar en ISSUE-123, necesito aclarar:
   - ¿Hay algún estilo de código específico que deba seguir?
   - ¿Hay algún framework o biblioteca preferida?
   - ¿Hay algún patrón de diseño que deba usar?
   - ¿Requiere tests? ¿Qué nivel de cobertura?
   - ¿Hay algún deadline específico?
   ```

4. **Verificar dependencias:**
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
- El issue es un ejercicio o prueba rápida

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
   ```
   Necesito crear el archivo [nombre] para ISSUE-123.
   
   ¿En qué carpeta debo guardarlo?
   - [Opción 1 basada en estructura existente]
   - [Opción 2 basada en convención]
   - ¿O prefieres otra ubicación?
   ```

4. **Seguir convenciones del proyecto:**
   - Si existe `src/components/`, crear componentes ahí
   - Si existe `src/services/`, crear servicios ahí
   - Si existe `tests/`, crear tests ahí
   - Si no hay estructura clara, preguntar al usuario

#### Proceso de Decisión

```
Proceso de decisión para ISSUE-123:

1. ¿Requiere control de versiones?
   - Sí → Verificar/crear repositorio
   - No → Crear archivos directamente

2. ¿Es parte de un proyecto existente?
   - Sí → Usar estructura del proyecto
   - No → Preguntar estructura preferida

3. ¿Dónde guardar archivos?
   - Analizar estructura existente
   - Si no está claro → Preguntar al usuario
   - Si está claro → Usar carpeta apropiada
```

### Paso 3: Integración con GitHub (si aplica)

**Trabajar profesionalmente con control de versiones cuando sea necesario:**

#### Verificar Repositorio Existente

1. **Verificar si existe repositorio:**
   - Revisar si hay un repositorio Git en el proyecto actual
   - Verificar si hay un repositorio remoto configurado
   - Comprobar si hay un repositorio en GitHub/GitLab

2. **Si NO existe repositorio pero el issue lo requiere:**
   ```
   El issue requiere control de versiones pero no encuentro un repositorio Git.
   
   ¿Deseas que:
   1. Inicialice un repositorio local?
   2. Cree un repositorio en GitHub?
   3. Use un repositorio existente?
   ```

3. **Si el usuario quiere crear repositorio:**
   - Inicializar repositorio Git local
   - Crear repositorio en GitHub (si es posible)
   - Configurar remote correctamente
   - Crear `.gitignore` apropiado
   - Crear README inicial

4. **Si el issue es simple y no requiere repositorio:**
   - Crear archivos directamente en la carpeta apropiada
   - Verificar que los archivos funcionen
   - Continuar con implementación sin Git

#### Trabajar con Ramas Profesionales

**NUNCA trabajes directamente en `main` o `master`:**

1. **Crear rama desde el issue:**
   ```bash
   # Nombre de rama descriptivo basado en el issue
   git checkout -b feature/ISSUE-123-authentication-endpoint
   # o
   git checkout -b fix/ISSUE-124-login-bug
   # o
   git checkout -b refactor/ISSUE-125-simplify-middleware
   ```

2. **Convenciones de nombres de ramas:**
   - `feature/ISSUE-123-descripcion-corta`
   - `fix/ISSUE-124-descripcion-bug`
   - `refactor/ISSUE-125-descripcion-refactor`
   - `docs/ISSUE-126-descripcion-docs`
   - `chore/ISSUE-127-descripcion-chore`

3. **Proceso de creación de rama:**
   ```bash
   # 1. Asegurarse de estar en main/master actualizado
   git checkout main
   git pull origin main
   
   # 2. Crear rama desde el issue
   git checkout -b feature/ISSUE-123-nombre-descriptivo
   
   # 3. Actualizar issue en Linear con la rama
   # Usa: `update_issue` con id del issue y description actualizada incluyendo la sección de rama
   ```

### Paso 4: Implementación Completa

**Implementar la solución profesionalmente:**

1. **Identificar ubicación de archivos:**
   - Analizar estructura del proyecto para determinar carpeta apropiada
   - Si no está claro, preguntar al usuario: "¿En qué carpeta debo crear [archivo]?"
   - Seguir convenciones del proyecto (src/, lib/, components/, tests/, etc.)

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

5. **Aclarar dudas durante implementación:**
   ```
   Mientras implemento ISSUE-123, tengo una duda:
   - ¿Prefieres usar X o Y para esto?
   - ¿Hay algún caso edge que deba considerar?
   - ¿Debo añadir logging adicional?
   ```

### Paso 5: Commits Profesionales (si aplica)

**Hacer commits con mensajes claros y profesionales:**

#### Convenciones de Commits

**Formato:**
```
[Type]: [Descripción corta]

[Descripción detallada si es necesario]

Closes #ISSUE-123
```

**Tipos de commits:**
- `feat`: Nueva funcionalidad
- `fix`: Corrección de bug
- `refactor`: Refactorización de código
- `docs`: Documentación
- `test`: Tests
- `chore`: Tareas de mantenimiento
- `style`: Formato de código (sin cambios funcionales)

#### Ejemplos de Commits Profesionales

**Ejemplo 1: Feature**
```bash
git commit -m "feat: Implement authentication endpoint

- Add POST /api/auth/login endpoint
- Add JWT token generation
- Add password hashing with bcrypt
- Add input validation

Closes #ISSUE-123"
```

**Ejemplo 2: Fix**
```bash
git commit -m "fix: Resolve login 401 error with OAuth2

- Fix token validation issue
- Update error handling for expired tokens
- Add proper error messages

Closes #ISSUE-124"
```

**Ejemplo 3: Refactor**
```bash
git commit -m "refactor: Simplify authentication middleware

- Extract common logic to helper functions
- Improve code readability
- Reduce code duplication

Closes #ISSUE-125"
```

#### Proceso de Commits

```bash
# 1. Verificar cambios
git status

# 2. Añadir archivos relevantes
git add src/auth/endpoint.js
git add tests/auth.test.js

# 3. Commit con mensaje descriptivo
git commit -m "feat: Implement authentication endpoint

Closes #ISSUE-123"

# 4. Push a la rama
git push origin feature/ISSUE-123-authentication-endpoint
```

### Paso 6: Crear Pull Request (si aplica)

**Si trabajas con GitHub/GitLab:**

1. **Crear Pull Request:**
   - Título descriptivo: `[Type]: [Descripción] - Closes #ISSUE-123`
   - Descripción completa con:
     - Qué se implementó
     - Cómo se probó
     - Screenshots si aplica
     - Referencias al issue

2. **Ejemplo de PR:**
   ```markdown
   ## Descripción
   Implementa el endpoint de autenticación según ISSUE-123
   
   ## Cambios
   - Añadido POST /api/auth/login
   - Implementada generación de JWT tokens
   - Añadido hashing de passwords con bcrypt
   - Añadidos tests unitarios
   
   ## Testing
   - [x] Tests unitarios pasan
   - [x] Verificado manualmente
   - [x] Verificado que no rompe funcionalidad existente
   
   ## Relacionado
   Closes #ISSUE-123
   ```

### Paso 7: Completar el Issue y Poner en Revisión

**Solo marcar como "In Review" cuando TODO esté completo y listo para revisión:**

#### Checklist Antes de Marcar como In Review

- [ ] ¿El código está implementado completamente?
- [ ] ¿Los tests pasan (si aplica)?
- [ ] ¿Funciona correctamente?
- [ ] ¿Cumple todos los criterios de aceptación?
- [ ] ¿Está commiteado y pusheado?
- [ ] ¿Hay un PR creado (si aplica)?
- [ ] ¿Los sub-issues están completados (si aplica)?
- [ ] ¿Está documentado el trabajo realizado?

#### Proceso de Completar y Poner en Revisión

1. **Actualizar estado a "In Review":**
   - Usa: `update_issue`
   - Parámetros: `id` (ID del issue), `state: "In Review"`
   - Nota: El estado puede variar según el equipo. Usa `list_issue_statuses` con el `team` para verificar los estados disponibles si "In Review" no existe

2. **Añadir comentario profesional con resumen:**
   - Usa: `create_comment`
   - Parámetros: `issueId` (ID del issue), `body` (texto del comentario en Markdown)
   - Incluye: resumen de cambios, referencias a commits/PRs, verificación, notas
   - Menciona que está listo para revisión
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

3. **Verificar sub-issues:**
   - Si hay sub-issues, usa: `list_issues` con filtro `parentId: "ISSUE-123"`
   - Revisa el estado de cada sub-issue retornado
   - Si algún sub-issue no está "In Review" o "Done", usa `create_comment` para añadir una nota de advertencia
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

### Paso 8: Revisar Issue en "In Review"

**Cuando una issue está en "In Review" y se solicita revisarla, realizar revisión completa con tests:**

#### Proceso de Revisión con Tests

1. **Verificar estado del issue:**
   - Obtener issue: Usa `get_issue` con `id` (ID del issue)
   - Verificar que está en estado "In Review"
   - Si no está en "In Review", aclarar con el usuario antes de proceder
   - Revisar código implementado en el repositorio
   - Revisar cambios en PR si existe

2. **Ejecutar tests existentes:**
   - Buscar tests relacionados con el código implementado
   - Ejecutar tests unitarios relevantes
   - Ejecutar tests de integración si aplica
   - Verificar que todos los tests pasan
   - Si algún test falla, documentar el problema en un comentario

3. **Analizar necesidad de tests:**
   - ¿Existen tests para el código nuevo implementado?
   - ¿La cobertura de tests es adecuada?
   - ¿Hay casos edge o límites sin cubrir?
   - ¿Hay tests de integración necesarios?
   - ¿Hay tests de regresión necesarios?

4. **Crear issues de testeo si es necesario:**
   - Si faltan tests críticos o importantes, crear issue con `create_issue`
   - Formato del título: `test: [Descripción] - Tests para ISSUE-XXX`
   - Descripción debe incluir:
     - Qué funcionalidad necesita tests
     - Qué tipo de tests son necesarios (unitarios, integración, e2e)
     - Casos edge que deben cubrirse
     - Referencia al issue original
   - Usar `parentId` si la issue original tiene padre para mantener jerarquía
   - Asignar al mismo equipo que la issue original
   - Prioridad según criticidad: High si es funcionalidad crítica, Normal si es estándar
   - Labels apropiados: `test`, y otros según el área (frontend, backend, api, etc.)

5. **Crear tests directamente cuando sea apropiado:**
   - Si es simple y directo crear los tests, hacerlo en el código
   - Asegurar que los tests pasan antes de commitear
   - Commit de tests con mensaje apropiado:
     ```bash
     git commit -m "test: Add tests for ISSUE-123
     
     - Add unit tests for [funcionalidad]
     - Add integration tests for [componente]
     - Cover edge cases
     
     Related to ISSUE-123"
     ```
   - Push de los tests a la rama

6. **Completar revisión:**
   - Actualizar issue a "Done" solo si:
     - Todos los tests existentes pasan
     - Tests necesarios están creados (issues creados o tests en código)
     - Código revisado y aprobado
     - No hay problemas críticos detectados
   - Si hay problemas que requieren cambios, usar `create_comment` para documentarlos
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`
   - Si todo está correcto, actualizar estado: `update_issue` con `id` y `state: "Done"`
   - Añadir comentario de revisión con resultados:
     - Usa: `create_comment`
     - Parámetros: `issueId` (ID del issue), `body` (texto del comentario en Markdown)
     - Incluye:
       - Resultado de ejecución de tests
       - Tests creados o issues de testeo creados
       - Problemas encontrados (si hay)
       - Aprobación o solicitud de cambios
     - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

#### Ejemplo de Revisión

**Issue:** ISSUE-123 está en "In Review"

**Proceso del agente:**

1. **Verificar estado:**
   - Usa: `get_issue` con `id: "ISSUE-123"`
   - Confirma que `state` es "In Review"
   - Revisa código en la rama `feature/ISSUE-123-authentication-endpoint`

2. **Ejecutar tests:**
   ```bash
   npm test
   # o
   pytest tests/
   ```
   - Verifica que todos pasan

3. **Analizar necesidad:**
   - Detecta que faltan tests para casos edge de autenticación
   - Identifica necesidad de tests de integración con OAuth2

4. **Crear issue de testeo:**
   - Usa: `create_issue`
   - Parámetros:
     - `title: "test: Add edge case tests for authentication - Tests para ISSUE-123"`
     - `team: "Engineering"` (mismo equipo)
     - `parentId: "ISSUE-123"` (si tiene padre)
     - `description`: Incluye detalles de qué tests faltan
     - `priority: 2` (High)
     - `labels: ["test", "backend"]`

5. **Crear tests simples:**
   - Crea tests básicos para validación de entrada
   - Commit: `git commit -m "test: Add validation tests for ISSUE-123"`

6. **Completar revisión:**
   - Actualizar a "Done": `update_issue` con `id: "ISSUE-123"` y `state: "Done"`
   - Comentario: `create_comment` con resumen de revisión, incluyendo al final: `---\n_Hecho por Cursor_`

### Paso 9: Actualizar Issue Padre (si aplica)

**Si completaste un sub-issue:**

1. **Verificar progreso del issue padre:**
   - Obtén el issue padre: `get_issue` con `id` del `parentId`
   - Lista sub-issues: `list_issues` con `parentId` del issue padre
   - Calcula progreso: cuenta cuántos sub-issues tienen `state: "Done"` vs total

2. **Actualizar issue padre con progreso:**
   - Actualiza descripción: `update_issue` con `id` del padre y `description` actualizada incluyendo sección de progreso
   - Añade comentario: `create_comment` con `issueId` del padre y mensaje de progreso
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

## Ejemplos de Uso Profesional

### Ejemplo 1: Completar Feature Issue

**Issue:** "Implementar endpoint de autenticación"

**Proceso del agente:**

1. **Analizar issue:**
   - Usa: `get_issue` con `id: "ISSUE-123"`
   - Revisa toda la información retornada: descripción, criterios de aceptación, dependencias, sub-issues

2. **Aclarar dudas:**
   ```
   Antes de implementar ISSUE-123, necesito aclarar:
   - ¿Qué framework de autenticación prefieres? (JWT, OAuth2, etc.)
   - ¿Hay algún patrón de autenticación existente en el proyecto?
   - ¿Requiere tests? ¿Qué nivel de cobertura?
   ```

3. **Crear rama:**
   ```bash
   git checkout -b feature/ISSUE-123-authentication-endpoint
   ```

4. **Implementar:**
   - Escribir código del endpoint
   - Añadir tests
   - Verificar que funciona

5. **Commit:**
   ```bash
   git commit -m "feat: Implement authentication endpoint

   Closes #ISSUE-123"
   ```

6. **Push:**
   ```bash
   git push origin feature/ISSUE-123-authentication-endpoint
   ```

7. **Completar issue y poner en revisión:**
   - Actualizar estado: `update_issue` con `id: "ISSUE-123"` y `state: "In Review"`
   - Añadir comentario: `create_comment` con `issueId: "ISSUE-123"` y `body` con resumen profesional indicando que está listo para revisión, incluyendo al final: `---\n_Hecho por Cursor_`

### Ejemplo 2: Crear Repositorio si no Existe

**Situación:** No hay repositorio Git

**Proceso del agente:**

1. **Detectar falta de repositorio:**
   ```bash
   if [ ! -d .git ]; then
     echo "No hay repositorio Git. ¿Deseas que cree uno?"
   fi
   ```

2. **Si el usuario acepta:**
   ```bash
   # Inicializar repositorio
   git init
   
   # Crear .gitignore
   echo "node_modules/" > .gitignore
   echo ".env" >> .gitignore
   
   # Commit inicial
   git add .
   git commit -m "chore: Initial commit"
   
   # Crear repositorio en GitHub (si es posible)
   # gh repo create --private --source=. --remote=origin
   ```

3. **Continuar con el proceso normal**

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
- Ejemplo de formato completo:
  ```markdown
  ## Resumen de Cambios
  
  - Implementado endpoint de autenticación
  - Añadidos tests unitarios
  - Verificado que funciona correctamente
  
  ## Referencias
  - Branch: `feature/ISSUE-123-authentication-endpoint`
  - Commit: `abc123`
  - PR: #45
  
  Listo para revisión.
  
  ---
  _Hecho por Cursor_
  ```

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

### Buscar Issues

**Herramienta:** `search_issues`

**Parámetros:**
- `query` (requerido): Texto de búsqueda
- `team` (opcional): Filtrar por equipo
- `timeMin` (opcional): Fecha mínima
- `timeMax` (opcional): Fecha máxima

### Listar Estados Disponibles

**Herramienta:** `list_issue_statuses`

**Parámetros:**
- `team` (requerido): Nombre o ID del equipo

**Retorna:** Lista de estados disponibles para el equipo, incluyendo nombres y tipos

**Uso:** Úsalo para verificar qué estados están disponibles antes de actualizar un issue, especialmente para verificar si "In Review" existe en el equipo

## Checklist de Profesionalismo

### Antes de Marcar como "In Review"

Antes de poner un issue en "In Review", verifica:

- [ ] ¿He analizado completamente el issue?
- [ ] ¿He aclarado todas las dudas necesarias?
- [ ] ¿He verificado dependencias y sub-issues?
- [ ] ¿Requiere el issue un repositorio Git o basta con crear archivos?
- [ ] ¿He identificado la carpeta correcta donde guardar los archivos? (preguntar si no estoy seguro)
- [ ] ¿Existe un repositorio Git? (crear solo si el issue lo requiere)
- [ ] ¿He creado una rama profesional para el trabajo?
- [ ] ¿He implementado el código completamente?
- [ ] ¿Funciona correctamente?
- [ ] ¿He añadido tests si aplica?
- [ ] ¿Los tests pasan?
- [ ] ¿He hecho commits con mensajes profesionales?
- [ ] ¿He pusheado los cambios?
- [ ] ¿He creado un PR si aplica?
- [ ] ¿He documentado el trabajo en el comentario del issue?
- [ ] ¿He verificado que sub-issues estén completados?

### Al Revisar Issue en "In Review"

Cuando revises un issue en "In Review", verifica:

- [ ] ¿He verificado que el issue está en estado "In Review"?
- [ ] ¿He revisado el código implementado?
- [ ] ¿He ejecutado los tests existentes?
- [ ] ¿Todos los tests pasan?
- [ ] ¿He analizado si faltan tests?
- [ ] ¿He creado issues de testeo si es necesario?
- [ ] ¿He creado tests directamente si era apropiado?
- [ ] ¿He documentado problemas encontrados?
- [ ] ¿He actualizado a "Done" solo si todo está correcto?
- [ ] ¿He añadido comentario de revisión con resultados?
- [ ] ¿He incluido "_Hecho por Cursor_" al final del comentario?

## Consejos Finales

1. **NUNCA marques un issue como "Done" sin implementar** - Sé un profesional
2. **Pon issues en "In Review" después de implementar** - Permite revisión antes de marcar como "Done"
3. **Revisa issues en "In Review" con tests** - Ejecuta tests existentes y detecta necesidad de nuevos tests
4. **Crea issues de testeo si faltan tests críticos** - No dejes funcionalidad sin tests importantes
5. **Crea tests directamente cuando sea simple** - No siempre necesitas un issue separado
6. **SIEMPRE trabaja con ramas** - Nunca en main/master directamente
7. **Aclara dudas antes y durante** - Mejor preguntar que asumir
8. **Verifica que funciona** - No solo implementes, prueba
9. **Documenta el trabajo** - Comentarios profesionales en el issue
10. **Trabaja con control de versiones** - Git/GitHub profesionalmente
11. **Crea repositorio si hace falta** - No te limites si no existe
12. **SIEMPRE incluye "_Hecho por Cursor_" en comentarios** - Permite tracking y transparencia
