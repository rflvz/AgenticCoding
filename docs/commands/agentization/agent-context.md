# Contextualización de Agentes

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

Guía para contextualizar agentes (chats) con información específica del proyecto, compatible con los comandos FUNCIONALES de Linear.

> **⚠️ IMPORTANTE:** Antes de contextualizar un agente, lee el [documento de contexto del proyecto](../../../docs/project-context.md) para obtener información actualizada sobre el proyecto y trabajo en Linear. Este documento es la fuente única de verdad para contexto del proyecto. Si el documento no existe, usa el [comando FUNCIONAL de inicialización](../../../.cursor/commands/initialize-project-context.md) para crearlo.

## Filosofía: Contextualizar Profesionalmente

Cuando contextualizas un agente, **NO** solo le das instrucciones básicas. Actúa como un **arquitecto de agentes profesional** que:

1. **Analiza el contexto del proyecto** antes de contextualizar
2. **Lee el documento de contexto** del proyecto para información actualizada
3. **Integra con comandos FUNCIONALES** de Linear
4. **Define roles claros** y responsabilidades específicas
5. **Establece reglas profesionales** para el comportamiento del agente
6. **Añade contexto del proyecto** para mejor precisión

## Proceso Profesional de Contextualización

### Paso 1: Leer Contexto del Proyecto

**⚠️ REGLA CRÍTICA: SIEMPRE lee el documento de contexto del proyecto antes de contextualizar:**

1. **Leer documento de contexto:**
   - Ubicación: `docs/project-context.md`
   - Contiene: Información del proyecto, equipo, proyectos en Linear, issues activos, convenciones
   - **Esta es la fuente única de verdad** para contexto del proyecto

2. **Si el documento no existe:**
   - Usa el comando FUNCIONAL: `.cursor/commands/initialize-project-context.md`
   - Crea el documento de contexto antes de contextualizar el agente

3. **Extraer información relevante:**
   - Equipo principal y miembros
   - Proyectos activos en Linear
   - Issues activos y prioridades
   - Convenciones del proyecto (commits, branches, labels)
   - Decisiones arquitectónicas

### Paso 2: Definir Rol del Agente

**Define claramente el rol y responsabilidades del agente:**

1. **Rol Principal:**
   - ¿Cuál es el rol principal del agente? (ej: Revisor de código, Gestor de issues, Arquitecto)
   - ¿Qué funciones específicas debe realizar?

2. **Comandos Disponibles:**
   - ¿Qué comandos FUNCIONALES de Linear puede usar? (create-issues, complete-issues, review-issues)
   - ¿Qué herramientas MCP tiene disponibles?

3. **Reglas de Comportamiento:**
   - ¿Qué reglas debe seguir el agente?
   - ¿Cómo debe priorizar tareas?
   - ¿Qué formato debe usar para crear issues?

**Ejemplo:**

```
Contextualiza este agente como experto en Linear:
- Rol: Gestor de issues profesional
- Funciones: Crear, actualizar, buscar issues en Linear
- Comandos FUNCIONALES disponibles: @linear create-issues, @linear complete-issues
- Reglas: Usar títulos descriptivos, añadir contexto técnico, seguir convenciones del proyecto
```

### Paso 3: Añadir Contexto del Proyecto

**Añade información específica del proyecto al contexto del agente:**

1. **Información del Proyecto:**
   - Nombre del proyecto
   - Equipo asignado
   - Labels estándar del proyecto
   - Prioridad por defecto

2. **Información de Linear:**
   - Proyectos activos en Linear
   - Issues activos y prioridades
   - Estados y flujos de trabajo

3. **Convenciones del Proyecto:**
   - Formato de commits
   - Convenciones de branches
   - Estándares de código
   - Estilos de documentación

**Ejemplo:**

```
Contextualiza este agente con información del proyecto:
- Proyecto: Sistema de autenticación
- Equipo: Engineering (según docs/project-context.md)
- Labels estándar: backend, frontend, security (según docs/project-context.md)
- Prioridad por defecto: Normal
- Formato de títulos: "[Type]: [Descripción]"
```

### Paso 4: Definir Reglas Específicas

**Establece reglas profesionales para el comportamiento del agente:**

1. **Reglas de Creación de Issues:**
   - Formato de títulos
   - Estructura de descripciones
   - Asignación por defecto
   - Labels por tipo de issue

2. **Reglas de Actualización de Issues:**
   - Cuándo añadir comentarios
   - Cómo actualizar estados
   - Cuándo incluir referencias a commits

3. **Reglas de Priorización:**
   - Cómo evaluar prioridad
   - Qué factores considerar
   - Cuándo marcar como urgente

**Ejemplo:**

```
Define reglas para crear issues:
1. Título: Formato "[Type]: [Descripción]" (ej: "bug: Error en autenticación")
2. Descripción: Incluir contexto técnico, pasos para reproducir, impacto
3. Asignación: Equipo "Engineering" por defecto (según docs/project-context.md)
4. Labels: Usar "bug", "feature", "refactor" según tipo, más labels estándar del proyecto
5. Prioridad: Evaluar según severidad del problema y contexto del proyecto
```

### Paso 5: Integrar con Comandos FUNCIONALES

**Integra el contexto del agente con los comandos FUNCIONALES de Linear:**

1. **Referenciar comandos FUNCIONALES:**
   - Cuando crear issues: Usar `.cursor/commands/create-issues.md`
   - Cuando completar issues: Usar `.cursor/commands/complete-issues.md`
   - Cuando revisar issues: Usar `.cursor/commands/review-issues.md`

2. **Usar contexto en comandos:**
   - El agente debe usar el contexto del proyecto al ejecutar comandos
   - Aplicar reglas y convenciones definidas
   - Seguir el flujo de trabajo profesional

**Ejemplo:**

```
Al crear issues usando el comando FUNCIONAL create-issues.md:
- Usa el equipo del contexto del proyecto
- Aplica los labels estándar del contexto
- Sigue el formato de títulos definido
- Prioriza según el contexto del proyecto
```

## Casos de Uso Avanzados

### Caso 1: Agente Revisor de Código

**Contextualiza un agente para revisar código y crear issues automáticamente:**

```
Contextualiza este agente como revisor de código profesional:
- Rol: Revisor experto de código
- Funciones: Revisar código, identificar bugs, crear issues en Linear
- Comandos FUNCIONALES: @linear create-issues (para bugs encontrados)
- Reglas: 
  * Analizar código antes de crear issues
  * Priorizar según severidad (Urgent para bugs críticos, High para bugs regulares)
  * Usar labels apropiados: "bug", "security", "refactor" según tipo
  * Incluir contexto técnico en descripciones
- Contexto del proyecto: Leer docs/project-context.md antes de crear issues
```

### Caso 2: Agente Arquitecto

**Contextualiza un agente para diseñar sistemas y dividir features:**

```
Contextualiza este agente como arquitecto de software:
- Rol: Diseñador de arquitectura
- Funciones: Diseñar sistemas, dividir features, crear issues de arquitectura
- Comandos FUNCIONALES: @linear create-issues (para tareas de diseño)
- Reglas:
  * Dividir features grandes en sub-issues
  * Establecer dependencias entre issues
  * Documentar decisiones arquitectónicas
  * Crear issues padre (Epic) para features grandes
- Contexto del proyecto: Leer docs/project-context.md para entender arquitectura actual
```

### Caso 3: Agente Multi-Rol

**Contextualiza un agente con múltiples roles:**

```
Contextualiza este agente con múltiples roles:
- Rol principal: Revisor de código
- Rol secundario: Gestor de issues
- Contexto del proyecto: Sistema de autenticación (según docs/project-context.md)
- Reglas:
  * Priorizar bugs de seguridad
  * Usar labels estándar del proyecto
  * Seguir convenciones del proyecto
- Comandos FUNCIONALES: 
  * @linear create-issues (para bugs encontrados)
  * @linear complete-issues (para issues asignados)
  * @linear review-issues (para issues en revisión)
```

### Caso 4: Agente con Workflow Completo

**Contextualiza un agente con un workflow completo:**

```
Contextualiza este agente con workflow completo:
1. Leer contexto del proyecto (docs/project-context.md)
2. Revisar código
3. Identificar problemas
4. Crear issues en Linear usando @linear create-issues
5. Monitorear progreso usando @linear list-search
6. Actualizar estados usando @linear complete-issues
7. Generar reportes

Reglas:
- Usar comandos FUNCIONALES de Linear
- Seguir convenciones del proyecto
- Aplicar reglas de priorización
- Documentar decisiones importantes
```

## Herramientas de Referencia

### Documento de Contexto del Proyecto

**Ubicación:** `docs/project-context.md`

**Contiene:**
- Información del proyecto
- Equipo principal y miembros
- Proyectos activos en Linear
- Issues activos y prioridades
- Convenciones del proyecto
- Decisiones arquitectónicas

**Uso:** Leer antes de contextualizar cualquier agente para obtener información actualizada del proyecto.

### Comandos FUNCIONALES de Linear

**Ubicación:** `.cursor/commands/`

**Comandos disponibles:**
- `initialize-project-context.md` - Inicializar documento de contexto
- `create-issues.md` - Crear issues profesionalmente
- `complete-issues.md` - Completar issues profesionalmente
- `review-issues.md` - Revisar issues profesionalmente
- `create-projects.md` - Crear proyectos con issues iniciales
- `list-search.md` - Listar y buscar issues

**Uso:** Referenciar estos comandos cuando el agente necesite realizar operaciones en Linear.

## Checklist de Profesionalismo

### ⚠️ Antes de Contextualizar

- [ ] ¿He leído el documento de contexto del proyecto (`docs/project-context.md`)?
- [ ] ¿He identificado el rol principal del agente?
- [ ] ¿He definido las funciones específicas del agente?
- [ ] ¿He establecido reglas profesionales de comportamiento?
- [ ] ¿He añadido contexto del proyecto al agente?

### Al Contextualizar

- [ ] ¿El agente tiene acceso a los comandos FUNCIONALES de Linear?
- [ ] ¿Las reglas siguen las convenciones del proyecto?
- [ ] ¿El contexto incluye información actualizada del proyecto?
- [ ] ¿El agente puede integrarse con comandos FUNCIONALES?

### Después de Contextualizar

- [ ] ¿El agente puede crear issues usando el comando FUNCIONAL create-issues.md?
- [ ] ¿El agente aplica las reglas definidas correctamente?
- [ ] ¿El agente sigue las convenciones del proyecto?
- [ ] ¿El agente usa el contexto del proyecto en sus operaciones?

## Consejos Finales

1. **⚠️ SIEMPRE lee el documento de contexto del proyecto** antes de contextualizar
2. **Usa comandos FUNCIONALES de Linear** en lugar de comandos experimentales
3. **Define roles claros** y responsabilidades específicas
4. **Establece reglas profesionales** para el comportamiento del agente
5. **Añade contexto del proyecto** para mejor precisión
6. **Integra con comandos FUNCIONALES** para máxima efectividad
7. **Actualiza el contexto** cuando cambie el proyecto

## Referencias

- [Documento de Contexto del Proyecto](../../../docs/project-context.md) - Fuente única de verdad para contexto del proyecto
- [Comandos FUNCIONALES de Linear](../../../.cursor/commands/) - Comandos completamente funcionales y probados
- [Inicializar Contexto del Proyecto](../../../.cursor/commands/initialize-project-context.md) - Crear documento de contexto
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Crear issues profesionalmente
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Completar issues profesionalmente
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Revisar issues profesionalmente

---