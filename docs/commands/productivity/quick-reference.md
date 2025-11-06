> **⚠️⚠️⚠️ EXPERIMENTAL ⚠️⚠️⚠️**
> 
> **Este comando es EXPERIMENTAL y está en desarrollo. No confiar ciegamente.**
> 
> **Para comandos FUNCIONALES, usa los comandos de Linear en `.cursor/commands/`:**
> - ✅ [Inicializar Contexto del Proyecto](../../../.cursor/commands/initialize-project-context.md)
> - ✅ [Crear Issues](../../../.cursor/commands/create-issues.md)
> - ✅ [Completar Issues](../../../.cursor/commands/complete-issues.md)
> - ✅ [Revisar Issues](../../../.cursor/commands/review-issues.md)
> - ✅ [Crear Proyectos](../../../.cursor/commands/create-projects.md)
> - ✅ [Listar y Buscar](../../../.cursor/commands/list-search.md)

# Referencia Rápida de Comandos

Guía profesional de referencia rápida para comandos esenciales de Linear y agentización, diseñada para consulta rápida durante el desarrollo.

## Filosofía: Referencia Rápida Eficiente

Una referencia rápida debe ser **concisa pero completa**. Actúa como un **desarrollador profesional** que:

1. **Memoriza comandos frecuentes** para uso diario
2. **Consulta rápidamente** comandos menos usados
3. **Combina comandos** para flujos de trabajo complejos
4. **Usa aliases mentales** para acelerar el trabajo
5. **Referencia comandos FUNCIONALES** cuando sea necesario

## Proceso de Uso Profesional

### Paso 1: Comandos Rápidos de Linear (Esenciales)

**⚠️ REGLA CRÍTICA: Estos son los comandos MÁS USADOS - memorízalos primero:**

#### Crear Issue

```bash
@linear create issue "Título" --team "Equipo"
```

**Parámetros comunes:**
- `--assignee "me"` - Auto-asignar
- `--priority "High"` - Prioridad
- `--labels "bug,frontend"` - Labels
- `--description "Descripción completa"` - Descripción

**Uso profesional:**
- Usa títulos descriptivos: `"bug: Login fails with OAuth2"`
- Intuye labels apropiados basándote en el contexto
- Añade descripciones completas con contexto técnico

#### Listar Issues

```bash
@linear list issues --assignee "me"
```

**Filtros útiles:**
- `--state "In Progress"` - Filtrar por estado
- `--priority "Urgent"` - Filtrar por prioridad
- `--label "bug"` - Filtrar por label
- `--created-after "-P1D"` - Issues del último día

#### Buscar Issues

```bash
@linear search issues "término"
```

**Uso profesional:**
- Busca antes de crear para evitar duplicados
- Usa términos específicos para búsquedas precisas

#### Actualizar Issue

```bash
@linear update issue ISSUE_ID --state "Done"
```

**Parámetros comunes:**
- `--state "In Progress"` - Cambiar estado
- `--assignee "me"` - Reasignar
- `--priority "High"` - Cambiar prioridad
- `--labels "bug,hotfix"` - Actualizar labels

#### Añadir Comentario

```bash
@linear create comment ISSUE_ID "Texto del comentario"
```

**Uso profesional:**
- Añade comentarios con contexto técnico
- Incluye referencias a commits o PRs cuando aplique
- Documenta decisiones importantes

### Paso 2: Aliases Mentales Útiles

**⚠️ REGLA CRÍTICA: Los aliases mentales aceleran significativamente el trabajo:**

#### Issues Míos

```bash
@linear list issues --assignee "me"
```

**Alias mental:** `"mis issues"` → Lista todos mis issues

#### Issues Urgentes

```bash
@linear list issues --priority "Urgent"
```

**Alias mental:** `"issues urgentes"` → Lista issues urgentes

#### Issues de Hoy

```bash
@linear list issues --created-after "-P1D"
```

**Alias mental:** `"issues de hoy"` → Lista issues creados hoy

#### Issues en Progreso

```bash
@linear list issues --state "In Progress" --assignee "me"
```

**Alias mental:** `"issues en progreso"` → Lista mis issues en progreso

**Uso profesional:**
- Crea tus propios aliases mentales para comandos frecuentes
- Documenta aliases útiles para referencia futura

### Paso 3: Comandos de Agentes Rápidos

**⚠️ REGLA CRÍTICA: Los comandos de agentes permiten automatización avanzada:**

#### Contextualizar Agente

```
Contextualiza este agente como [rol]: [descripción]
```

**Ejemplo:**
```
Contextualiza este agente como revisor de código: 
Especializado en encontrar bugs y problemas de seguridad
```

#### Activar Rol

```
Activa rol: [Nombre del Rol]
```

**Ejemplo:**
```
Activa rol: Project Manager
```

#### Ejecutar Workflow

```
Ejecuta workflow: [Nombre del Workflow]
```

**Ejemplo:**
```
Ejecuta workflow: Crear Issue desde Error
```

**Uso profesional:**
- Contextualiza agentes apropiadamente para cada tarea
- Usa roles especializados para tareas específicas
- Crea workflows reutilizables para tareas repetitivas

### Paso 4: Referencias de Comandos Completas

**⚠️ REGLA CRÍTICA: Consulta estas referencias cuando necesites comandos específicos:**

#### Comandos de Linear

| Acción | Comando | Ejemplo |
|--------|---------|---------|
| Crear | `@linear create issue "Título" --team "Equipo"` | `@linear create issue "bug: Login fails" --team "DAW"` |
| Listar | `@linear list issues --assignee "me"` | `@linear list issues --assignee "me" --state "In Progress"` |
| Buscar | `@linear search issues "término"` | `@linear search issues "autenticación"` |
| Actualizar | `@linear update issue ID --state "Done"` | `@linear update issue DAW-27 --state "In Review"` |
| Comentar | `@linear create comment ID "Texto"` | `@linear create comment DAW-27 "Completado"` |

#### Comandos de Agentes

| Acción | Comando | Ejemplo |
|--------|---------|---------|
| Contextualizar | `Contextualiza este agente: [descripción]` | `Contextualiza este agente como revisor de código` |
| Activar Rol | `Activa rol: [nombre]` | `Activa rol: Project Manager` |
| Ejecutar Workflow | `Ejecuta workflow: [nombre]` | `Ejecuta workflow: Crear Issue desde Error` |

### Paso 5: Combinaciones Útiles

**⚠️ REGLA CRÍTICA: Las combinaciones de comandos permiten flujos de trabajo complejos:**

#### Comandos Encadenados

```bash
# Obtener issue y actualizar estado
@linear get issue ISSUE-123
@linear update issue ISSUE-123 --state "In Progress"
@linear create comment ISSUE-123 "Empezando trabajo"
```

#### Múltiples Comandos en Uno

```
Lista mis issues en progreso y crea un issue nuevo para la tarea X
```

**El agente ejecuta:**
1. `@linear list issues --assignee "me" --state "In Progress"`
2. `@linear create issue "Tarea X" --team "Equipo"`

**Uso profesional:**
- Encadena comandos para flujos de trabajo completos
- Usa lenguaje natural para comandos complejos
- Deja que el agente interprete y ejecute múltiples comandos

### Paso 6: Variables Especiales

**⚠️ REGLA CRÍTICA: Las variables especiales simplifican comandos:**

#### Variables de Usuario

- `"me"` - Referencia a tu usuario actual
- `"usuario@email.com"` - Usuario específico por email
- `"Nombre Usuario"` - Usuario por nombre

#### Fechas Relativas

- `-P1D` - Último día (Past 1 Day)
- `-P7D` - Última semana (Past 7 Days)
- `-P30D` - Último mes (Past 30 Days)

#### Estados Comunes

- `"Backlog"` - Pendiente
- `"Todo"` - Por hacer
- `"In Progress"` - En progreso
- `"In Review"` - En revisión
- `"Done"` - Completado

**Uso profesional:**
- Usa `"me"` constantemente para auto-asignación
- Las fechas relativas (`-P1D`) son más útiles que fechas absolutas
- Combina variables para comandos más expresivos

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Esta referencia rápida complementa los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Guía completa para crear issues profesionalmente
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Proceso completo de completar issues
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Revisión profesional de issues
- [Crear Proyectos](../../../.cursor/commands/create-projects.md) - Creación de proyectos completos
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Búsqueda avanzada de issues

**Cuándo usar cada uno:**
- **Referencia rápida (este documento)**: Para comandos simples y consulta rápida
- **Comandos FUNCIONALES**: Para procesos completos y trabajo profesional

## Flujos de Trabajo Rápidos

### Flujo 1: Crear Issue Rápido

```
1. @linear create issue "Título" --team "Equipo" --assignee "me"
2. Añadir descripción si es necesario
```

### Flujo 2: Actualizar Issue

```
1. @linear get issue ISSUE_ID
2. @linear update issue ISSUE_ID --state "In Progress"
3. @linear create comment ISSUE_ID "Comentario"
```

### Flujo 3: Buscar y Actualizar

```
1. @linear search issues "término"
2. Identificar issue relevante
3. @linear update issue ISSUE_ID --state "Done"
```

## Checklist de Profesionalismo

### ⚠️ Al Usar Comandos

- [ ] ¿He memorizado los comandos esenciales?
- [ ] ¿Estoy usando aliases mentales para acelerar?
- [ ] ¿Estoy combinando comandos para flujos complejos?
- [ ] ¿Estoy consultando comandos FUNCIONALES cuando es necesario?

### Antes de Crear Issue

- [ ] ¿He buscado issues similares para evitar duplicados?
- [ ] ¿Estoy usando títulos descriptivos?
- [ ] ¿Estoy añadiendo descripciones completas con contexto?

## Consejos Finales

1. **⚠️ Memoriza primero los esenciales** - Crear, listar, actualizar son los más usados
2. **Usa aliases mentales** - Acelera significativamente el trabajo
3. **Combina comandos** - Los flujos complejos se simplifican con combinaciones
4. **Consulta comandos FUNCIONALES** - Para procesos completos y trabajo profesional
5. **Documenta tus aliases** - Guarda tus aliases mentales para referencia
6. **Practica regularmente** - La memoria muscular se desarrolla con el uso

---
_Hecho por Cursor_
