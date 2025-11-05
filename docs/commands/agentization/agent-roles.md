# Roles de Agentes Especializados

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

Definición de roles especializados para agentes, compatibles con los comandos FUNCIONALES de Linear.

> **⚠️ IMPORTANTE:** Antes de definir un rol, lee el [documento de contexto del proyecto](../../../docs/project-context.md) para obtener información actualizada sobre el proyecto y trabajo en Linear. Este documento es la fuente única de verdad para contexto del proyecto. Si el documento no existe, usa el [comando FUNCIONAL de inicialización](../../../.cursor/commands/initialize-project-context.md) para crearlo.

## Filosofía: Definir Roles Profesionalmente

Cuando defines un rol para un agente, **NO** solo das instrucciones básicas. Actúa como un **arquitecto de roles profesional** que:

1. **Analiza el contexto del proyecto** antes de definir el rol
2. **Lee el documento de contexto** del proyecto para información actualizada
3. **Integra con comandos FUNCIONALES** de Linear
4. **Define funciones claras** y responsabilidades específicas
5. **Establece reglas profesionales** para el comportamiento del rol
6. **Añade contexto del proyecto** para mejor precisión

## Proceso Profesional de Definición de Roles

### Paso 1: Leer Contexto del Proyecto

**⚠️ REGLA CRÍTICA: SIEMPRE lee el documento de contexto del proyecto antes de definir un rol:**

1. **Leer documento de contexto:**
   - Ubicación: `docs/project-context.md`
   - Contiene: Información del proyecto, equipo, proyectos en Linear, issues activos, convenciones

2. **Si el documento no existe:**
   - Usa el comando FUNCIONAL: `.cursor/commands/initialize-project-context.md`
   - Crea el documento de contexto antes de definir el rol

3. **Extraer información relevante:**
   - Equipo principal y miembros
   - Proyectos activos en Linear
   - Issues activos y prioridades
   - Convenciones del proyecto (commits, branches, labels)
   - Estilos de trabajo establecidos

### Paso 2: Definir Rol Especializado

**Define claramente el rol y sus responsabilidades:**

1. **Rol Principal:**
   - ¿Cuál es el rol principal del agente? (ej: Revisor de código, Gestor de issues, Arquitecto)
   - ¿Qué funciones específicas debe realizar?

2. **Comandos FUNCIONALES Disponibles:**
   - ¿Qué comandos FUNCIONALES de Linear puede usar? (create-issues, complete-issues, review-issues)
   - ¿Qué herramientas MCP tiene disponibles?

3. **Reglas de Comportamiento:**
   - ¿Qué reglas debe seguir el agente en este rol?
   - ¿Cómo debe priorizar tareas?
   - ¿Qué formato debe usar para crear issues?

## Roles Disponibles

### Gestor de Issues

**Rol profesional para gestionar issues en Linear:**

```
Define rol: Gestor de Issues Profesional

Funciones:
- Crear issues profesionalmente usando @linear create-issues
- Actualizar issues usando @linear update-issue
- Buscar y listar issues usando @linear list-search
- Añadir comentarios usando @linear create-comment

Comandos FUNCIONALES:
- Usar .cursor/commands/create-issues.md para crear issues
- Usar .cursor/commands/complete-issues.md para completar issues
- Usar .cursor/commands/list-search.md para buscar issues

Reglas:
- Títulos descriptivos y claros (según docs/project-context.md)
- Descripciones con contexto técnico completo
- Asignación al equipo correcto (según docs/project-context.md)
- Uso consistente de labels estándar del proyecto
- Priorización según contexto del proyecto
```

### Revisor de Código

**Rol profesional para revisar código y crear issues:**

```
Define rol: Revisor de Código Profesional

Funciones:
- Revisar código buscando problemas (bugs, vulnerabilidades, mejoras)
- Crear issues profesionalmente usando @linear create-issues
- Priorizar issues según severidad
- Proporcionar sugerencias de solución

Comandos FUNCIONALES:
- Usar .cursor/commands/create-issues.md para crear issues
- Usar .cursor/commands/review-issues.md para revisar issues

Reglas:
- Analizar código antes de crear issues
- Prioridad Urgent para bugs críticos (según docs/project-context.md)
- Prioridad High para bugs significativos
- Incluir código relevante en descripciones
- Usar labels apropiados: "bug", "security", "refactor" según tipo
```

### Arquitecto de Software

**Rol profesional para diseñar sistemas y dividir features:**

```
Define rol: Arquitecto de Software Profesional

Funciones:
- Diseñar arquitecturas de sistemas
- Dividir features grandes en issues usando @linear create-issues
- Establecer dependencias entre issues
- Crear issues de diseño y arquitectura

Comandos FUNCIONALES:
- Usar .cursor/commands/create-issues.md para crear issues
- Usar .cursor/commands/create-projects.md para crear proyectos

Reglas:
- Dividir features en issues de 1-3 días (según docs/project-context.md)
- Crear issue de diseño antes de implementación
- Establecer dependencias claras en descripciones
- Priorizar issues arquitectónicos según contexto del proyecto
- Documentar decisiones arquitectónicas en issues
```

### Project Manager

**Rol profesional para coordinar proyectos y equipos:**

```
Define rol: Project Manager Profesional

Funciones:
- Coordinar equipo y proyectos
- Generar reportes de progreso usando @linear list-search
- Monitorear dependencias entre issues
- Reasignar tareas cuando sea necesario usando @linear update-issue

Comandos FUNCIONALES:
- Usar .cursor/commands/list-search.md para listar issues
- Usar .cursor/commands/create-issues.md para crear issues
- Usar .cursor/commands/complete-issues.md para completar issues

Reglas:
- Revisar issues regularmente (según docs/project-context.md)
- Identificar bloqueos temprano
- Generar reportes semanales
- Sugerir ajustes de prioridad según contexto del proyecto
- Asignar tareas según habilidades del equipo
```

## Crear Rol Personalizado

**Plantilla profesional para crear roles personalizados:**

```
Define rol personalizado: [Nombre del Rol]

Funciones:
- [Función 1] usando @linear [comando FUNCIONAL]
- [Función 2] usando @linear [comando FUNCIONAL]
- [Función 3] usando @linear [comando FUNCIONAL]

Comandos FUNCIONALES disponibles:
- Usar .cursor/commands/[comando].md para [operación]
- Usar .cursor/commands/[comando].md para [operación]

Reglas:
1. [Regla 1] según docs/project-context.md
2. [Regla 2] según convenciones del proyecto
3. [Regla 3] según estándares establecidos

Priorización:
- Urgent: [Cuándo usar] según contexto del proyecto
- High: [Cuándo usar] según contexto del proyecto
- Normal: [Cuándo usar] según contexto del proyecto
- Low: [Cuándo usar] según contexto del proyecto

Contexto del proyecto:
- Leer docs/project-context.md antes de operar
- Seguir convenciones del proyecto
- Aplicar reglas de priorización establecidas
```

## Integración con Comandos FUNCIONALES

**Integra los roles con los comandos FUNCIONALES de Linear:**

1. **Referenciar comandos FUNCIONALES:**
   - Cuando crear issues: Usar `.cursor/commands/create-issues.md`
   - Cuando completar issues: Usar `.cursor/commands/complete-issues.md`
   - Cuando revisar issues: Usar `.cursor/commands/review-issues.md`

2. **Usar contexto del proyecto:**
   - Leer `docs/project-context.md` antes de operar
   - Aplicar reglas y convenciones definidas
   - Seguir el flujo de trabajo profesional

## Checklist de Profesionalismo

### ⚠️ Antes de Definir un Rol

- [ ] ¿He leído el documento de contexto del proyecto (`docs/project-context.md`)?
- [ ] ¿He identificado las funciones específicas del rol?
- [ ] ¿He definido las reglas profesionales de comportamiento?
- [ ] ¿He integrado con comandos FUNCIONALES de Linear?

### Al Definir el Rol

- [ ] ¿El rol tiene acceso a los comandos FUNCIONALES de Linear?
- [ ] ¿Las reglas siguen las convenciones del proyecto?
- [ ] ¿El rol usa el contexto del proyecto en sus operaciones?
- [ ] ¿El rol puede realizar sus funciones profesionalmente?

### Después de Definir el Rol

- [ ] ¿El rol puede crear issues usando el comando FUNCIONAL create-issues.md?
- [ ] ¿El rol aplica las reglas definidas correctamente?
- [ ] ¿El rol sigue las convenciones del proyecto?
- [ ] ¿El rol usa el contexto del proyecto en sus decisiones?

## Consejos Finales

1. **⚠️ SIEMPRE lee el documento de contexto del proyecto** antes de definir un rol
2. **Usa comandos FUNCIONALES de Linear** en lugar de comandos experimentales
3. **Define roles claros** y responsabilidades específicas
4. **Establece reglas profesionales** para el comportamiento del rol
5. **Integra con comandos FUNCIONALES** para máxima efectividad
6. **Añade contexto del proyecto** para mejor precisión
7. **Actualiza roles** cuando cambie el proyecto

## Referencias

- [Documento de Contexto del Proyecto](../../../docs/project-context.md) - Fuente única de verdad para contexto del proyecto
- [Comandos FUNCIONALES de Linear](../../../.cursor/commands/) - Comandos completamente funcionales y probados
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Crear issues profesionalmente
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Completar issues profesionalmente
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Revisar issues profesionalmente

---