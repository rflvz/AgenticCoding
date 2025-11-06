# Inicializar Documento de Contexto del Proyecto

Comando para crear o verificar el documento centralizado de contexto del proyecto (`docs/project-context.md`). Este comando asegura que el documento existe y está inicializado con información actual del proyecto y Linear.

> **⚠️ IMPORTANTE:** Este comando debe ejecutarse antes de usar otros comandos que dependen del documento de contexto. Si el documento ya existe, verifica que esté actualizado.

## Propósito

Este comando:

1. **Verifica si existe** el documento de contexto (`docs/project-context.md`)
2. **Crea el documento** si no existe, con información actual del proyecto y Linear
3. **Actualiza información** de Linear si el documento existe pero está desactualizado
4. **Asegura estructura correcta** del documento

## Cuándo Usar

Usa este comando cuando:

- **Primera vez** configurando el proyecto
- El documento de contexto **no existe** o fue eliminado
- Necesitas **re-inicializar** el documento con información actualizada
- Quieres **verificar** que el documento esté correctamente configurado

## Proceso de Inicialización

### Paso 1: Verificar Existencia del Documento

**ANTES de crear, verifica si existe:**

1. **Verificar si existe el archivo:**
   - Ruta: `docs/project-context.md`
   - Si existe: Verificar si necesita actualización
   - Si NO existe: Proceder a crear

2. **Si existe, verificar contenido:**
   - ¿Tiene la estructura correcta?
   - ¿Está actualizado con información reciente?
   - ¿Incluye información de Linear?

### Paso 2: Recopilar Información del Proyecto

**Recopilar información local del proyecto:**

1. **Estructura del proyecto:**
   - Leer `README.md` para obtener descripción y objetivos
   - Analizar estructura de directorios
   - Identificar tecnologías y herramientas usadas
   - Verificar estado actual del proyecto

2. **Información de Git:**
   - Branch actual
   - Últimos commits
   - Estado del repositorio

### Paso 3: Recopilar Información de Linear

**Recopilar información de Linear para poblar el documento:**

1. **Obtener información del equipo:**
   - Usa: `mcp_Linear_get_team` con `query: "DAW"` (o el nombre del equipo)
   - Obtener ID del equipo y nombre

2. **Listar proyectos activos:**
   - Usa: `mcp_Linear_list_projects` con `team: "DAW"` (o ID del equipo)
   - Obtener proyectos activos con:
     - ID, nombre, descripción, prioridad, estado
     - URLs de Linear

3. **Listar issues activos:**
   - Usa: `mcp_Linear_list_issues` con:
     - `team: "DAW"` (o ID del equipo)
     - `state: "In Progress"` para issues en progreso
     - `state: "Todo"` para issues pendientes
     - `limit: 20` para obtener suficientes issues
   - Obtener issues con:
     - ID, título, prioridad, estado
     - Asignado, proyecto, labels
     - Branch de Git, URLs

4. **Obtener detalles de issues importantes:**
   - Para issues relevantes, usar: `mcp_Linear_get_issue` con `id`
   - Obtener descripciones completas y objetivos

### Paso 4: Crear el Documento

**Crear el documento con estructura completa:**

1. **Estructura del documento:**
   ```markdown
   # Contexto del Proyecto [Nombre del Proyecto]
   
   **Última actualización:** [Fecha actual]
   **Versión:** 1.0
   
   > **⚠️ IMPORTANTE:** Este documento es la fuente única de verdad...
   
   ## Información del Proyecto
   
   ### Descripción General
   [Basado en README.md]
   
   ### Objetivos del Proyecto
   [Basado en README.md y análisis del proyecto]
   
   ### Estructura del Proyecto
   [Basado en estructura de directorios]
   
   ### Tecnologías y Herramientas
   [Identificadas del proyecto]
   
   ### Estado Actual del Proyecto
   [Estado general del proyecto]
   
   ## Información de Linear
   
   ### Equipo Principal
   [Información del equipo de Linear]
   
   ### Proyectos Activos
   [Lista de proyectos de Linear]
   
   ### Issues Activos
   [Lista de issues activos de Linear]
   
   ### Prioridades y Focos
   [Prioridades actuales]
   
   ## Convenciones y Estándares
   
   [Convenciones del proyecto]
   
   ## Decisiones Arquitectónicas
   
   [Decisiones importantes documentadas]
   
   ## Bloqueos y Dependencias
   
   [Bloqueos y dependencias actuales]
   
   ## Próximos Pasos
   
   [Próximos pasos planificados]
   
   ## Cómo Usar Este Documento
   
   [Instrucciones de uso]
   
   ## Referencias
   
   [Referencias a otros documentos]
   ```

2. **Poblar secciones con información recopilada:**
   - Información del proyecto: Desde README y análisis local
   - Información de Linear: Desde Linear API
   - Convenciones: Inferir de estructura del proyecto o usar valores por defecto
   - Decisiones: Documentar decisiones iniciales si existen

### Paso 5: Verificar y Completar

**Verificar que el documento esté completo:**

1. **Verificar estructura:**
   - [ ] ¿Tiene todas las secciones principales?
   - [ ] ¿La información de Linear está incluida?
   - [ ] ¿Las referencias son correctas?
   - [ ] ¿La fecha de actualización está actualizada?

2. **Completar información faltante:**
   - Si falta información de Linear, intentar obtenerla
   - Si falta información del proyecto, usar valores por defecto razonables
   - Documentar que cierta información necesita ser actualizada manualmente

## Ejemplo de Uso

### Comando Básico

```
Inicializa el documento de contexto del proyecto.

Verifica si existe docs/project-context.md y créalo si no existe, 
poblando con información actual del proyecto y Linear.
```

### Comando con Verificación

```
Verifica y actualiza el documento de contexto del proyecto.

1. Verifica si existe docs/project-context.md
2. Si existe, verifica que esté actualizado
3. Si no existe o está desactualizado, recopila información de:
   - Proyecto local (README, estructura, Git)
   - Linear (equipo DAW, proyectos, issues)
4. Crea o actualiza el documento con información actualizada
```

## Pasos Detallados de Implementación

### 1. Verificar Existencia

```python
# Pseudocódigo
if file_exists("docs/project-context.md"):
    print("Documento existe, verificando actualización...")
    # Leer documento existente
    # Verificar fecha de última actualización
    # Decidir si necesita actualización
else:
    print("Documento no existe, creando...")
    # Proceder a crear
```

### 2. Recopilar Información Local

```python
# Leer README.md
readme_content = read_file("README.md")

# Analizar estructura de directorios
project_structure = analyze_directory_structure(".")

# Obtener información de Git
current_branch = get_git_branch()
recent_commits = get_recent_commits(limit=5)
```

### 3. Recopilar Información de Linear

```python
# Obtener equipo
team = mcp_Linear_get_team(query="DAW")

# Listar proyectos
projects = mcp_Linear_list_projects(team="DAW")

# Listar issues activos
issues_in_progress = mcp_Linear_list_issues(
    team="DAW",
    state="In Progress",
    limit=20
)

issues_todo = mcp_Linear_list_issues(
    team="DAW",
    state="Todo",
    limit=10
)

# Obtener detalles de issues importantes
for issue in issues_in_progress[:5]:  # Primeros 5 issues
    issue_details = mcp_Linear_get_issue(id=issue.id)
```

### 4. Generar Contenido del Documento

```python
# Generar contenido basado en información recopilada
document_content = generate_project_context_document(
    project_info=project_info,
    linear_team=team,
    linear_projects=projects,
    linear_issues=issues_in_progress + issues_todo,
    update_date=current_date
)

# Escribir documento
write_file("docs/project-context.md", document_content)
```

## Manejo de Errores

### Si Linear no está disponible

Si no se puede acceder a Linear:

1. **Crear documento con información del proyecto:**
   - Incluir información local disponible
   - Documentar que la información de Linear necesita ser añadida manualmente
   - Incluir sección vacía para información de Linear

2. **Documentar en el documento:**
   ```markdown
   ## Información de Linear
   
   > **⚠️ NOTA:** La información de Linear no pudo ser obtenida automáticamente. 
   > Por favor, actualiza esta sección manualmente consultando Linear.
   ```

### Si falta información del proyecto

Si no se puede obtener información del proyecto:

1. **Usar valores por defecto razonables:**
   - Estructura básica estándar
   - Descripción genérica
   - Estado: "En desarrollo"

2. **Documentar que necesita actualización:**
   ```markdown
   > **⚠️ NOTA:** Esta información necesita ser actualizada manualmente.
   ```

## Verificación Post-Creación

Después de crear el documento, verifica:

- [ ] ¿El documento se creó correctamente?
- [ ] ¿Tiene la estructura completa?
- [ ] ¿La información de Linear está incluida (si está disponible)?
- [ ] ¿La información del proyecto está incluida?
- [ ] ¿Las referencias son correctas?
- [ ] ¿La fecha de actualización está correcta?

## Integración con Otros Comandos

Este comando debe ser referenciado por:

1. **Otros comandos de Linear:**
   - Antes de ejecutar comandos que usan contexto, verificar que el documento exista
   - Si no existe, sugerir ejecutar este comando primero

2. **Comandos de agentización:**
   - Antes de contextualizar agentes, verificar que el documento exista
   - Si no existe, crear automáticamente o sugerir ejecutar este comando

## Referencias

- [Documento de Contexto](../../project-context.md)
- [Guía de Actualización](../../project-context-update-guide.md)
- [Comandos de Linear](./)
- [Contexto Compartido](../../agentization/shared-context.md)

---

**Última actualización:** 2025-11-05

