# Agente Orquestador de Project Management

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

Guía para crear y gestionar un agente orquestador especializado en project management que coordina issues y tareas en Linear usando comandos FUNCIONALES.

> **⚠️ IMPORTANTE:** Antes de crear un agente orquestador, lee el [documento de contexto del proyecto](../../../docs/project-context.md) para obtener información actualizada sobre el proyecto y trabajo en Linear. Este documento es la fuente única de verdad para contexto del proyecto. Si el documento no existe, usa el [comando FUNCIONAL de inicialización](../../../.cursor/commands/initialize-project-context.md) para crearlo.

## Filosofía: Orquestar Profesionalmente

Cuando creas un agente orquestador, **NO** solo le das instrucciones básicas. Actúa como un **project manager profesional** que:

1. **Planifica estratégicamente** dividiendo features grandes en issues manejables
2. **Coordina eficientemente** monitoreando estados y dependencias
3. **Gestiona recursos** asignando tareas según prioridades y habilidades
4. **Genera reportes** para mantener visibilidad del progreso
5. **Integra con comandos FUNCIONALES** de Linear para máxima efectividad
6. **Usa el contexto del proyecto** para tomar decisiones informadas

## Proceso Profesional de Orquestación

### Paso 1: Leer Contexto del Proyecto

**⚠️ REGLA CRÍTICA: SIEMPRE lee el documento de contexto del proyecto antes de crear el orquestador:**

1. **Leer documento de contexto:**
   - Ubicación: `docs/project-context.md`
   - Contiene: Información del proyecto, equipo, proyectos en Linear, issues activos, convenciones

2. **Si el documento no existe:**
   - Usa el comando FUNCIONAL: `.cursor/commands/initialize-project-context.md`
   - Crea el documento de contexto antes de crear el orquestador

3. **Extraer información relevante:**
   - Equipo principal y miembros
   - Proyectos activos en Linear
   - Issues activos y prioridades
   - Convenciones del proyecto (commits, branches, labels)
   - Flujos de trabajo establecidos

### Paso 2: Configurar Agente Orquestador

**Define claramente las funciones y responsabilidades del orquestador:**

1. **Funciones Principales:**
   - Planificación: Dividir features en issues manejables
   - Coordinación: Monitorear estados y dependencias
   - Gestión: Asignar tareas según prioridades
   - Reportes: Generar reportes de progreso

2. **Comandos FUNCIONALES Disponibles:**
   - `create-issues.md` - Crear issues profesionalmente
   - `complete-issues.md` - Completar issues profesionalmente
   - `review-issues.md` - Revisar issues profesionalmente
   - `create-projects.md` - Crear proyectos con issues iniciales
   - `list-search.md` - Listar y buscar issues

3. **Reglas de Orquestación:**
   - Dividir features grandes en issues de 1-3 días
   - Crear issue padre (Epic) para features complejas
   - Establecer dependencias claras entre issues
   - Priorizar según objetivos del proyecto
   - Asignar según habilidades del equipo

**Ejemplo de Configuración:**

```
Crea un agente orquestador de project management que:

Funciones:
- Planificar: Dividir features grandes usando @linear create-issues
- Coordinar: Monitorear estados usando @linear list-search
- Gestionar: Asignar tareas según prioridades usando @linear update-issue
- Reportar: Generar reportes de progreso

Comandos FUNCIONALES:
- Usar .cursor/commands/create-issues.md para crear issues
- Usar .cursor/commands/complete-issues.md para completar issues
- Usar .cursor/commands/list-search.md para monitorear estados

Reglas:
- Dividir features en issues de 1-3 días
- Crear issue padre (Epic) para features complejas
- Establecer dependencias claras
- Priorizar según contexto del proyecto (docs/project-context.md)
- Asignar según habilidades del equipo
```

### Paso 3: Integrar con Comandos FUNCIONALES

**Integra el orquestador con los comandos FUNCIONALES de Linear:**

1. **Usar comandos FUNCIONALES:**
   - Cuando crear issues: Usar `.cursor/commands/create-issues.md`
   - Cuando completar issues: Usar `.cursor/commands/complete-issues.md`
   - Cuando revisar issues: Usar `.cursor/commands/review-issues.md`
   - Cuando crear proyectos: Usar `.cursor/commands/create-projects.md`

2. **Aplicar contexto del proyecto:**
   - Usar información de `docs/project-context.md`
   - Seguir convenciones del proyecto
   - Aplicar reglas de priorización establecidas

## Casos de Uso Avanzados

### Caso 1: Dividir Feature en Issues

**El orquestador divide una feature grande en issues manejables:**

```
@orchestrator divide feature "Sistema de autenticación" en issues manejables

El orquestador:
1. Lee contexto del proyecto (docs/project-context.md)
2. Analiza la feature propuesta
3. Crea issue padre (Epic) usando @linear create-issues:
   - Título: "feature: Sistema de autenticación"
   - Descripción: Visión general, objetivos, alcance
   - Labels: "feature", "epic" (según docs/project-context.md)
4. Divide en issues más pequeños usando @linear create-issues:
   - Diseño: "docs: Diseño de autenticación"
   - Backend: "feature: Backend API de autenticación"
   - Frontend: "feature: Frontend UI de login"
   - Tests: "chore: Tests para autenticación"
   - Documentación: "docs: Documentación de autenticación"
5. Establece dependencias en descripciones
6. Prioriza según importancia (según docs/project-context.md)
```

### Caso 2: Generar Reporte de Proyecto

**El orquestador genera un reporte completo del proyecto:**

```
@orchestrator generate report --team "Engineering" --period "last-week"

El orquestador:
1. Lee contexto del proyecto (docs/project-context.md)
2. Lista issues usando @linear list-search:
   - Issues completados en la última semana
   - Issues en progreso
   - Issues bloqueados
3. Analiza:
   - Progreso general del proyecto
   - Velocidad del equipo
   - Dependencias y bloqueos
4. Genera reporte con:
   - Resumen ejecutivo
   - Lista de issues por estado
   - Identificación de bloqueos
   - Sugerencias para próximos pasos
```

### Caso 3: Monitorear Dependencias

**El orquestador monitorea dependencias entre issues:**

```
@orchestrator check dependencies --project "Feature X"

El orquestador:
1. Lista todos los issues del proyecto usando @linear list-search
2. Identifica dependencias en descripciones
3. Detecta bloqueos:
   - Issues que dependen de otros no completados
   - Issues que bloquean a otros
4. Sugiere orden de ejecución
5. Actualiza prioridades si es necesario usando @linear update-issue
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

**Uso:** Leer antes de crear el orquestador para obtener información actualizada del proyecto.

### Comandos FUNCIONALES de Linear

**Ubicación:** `.cursor/commands/`

**Comandos disponibles:**
- `initialize-project-context.md` - Inicializar documento de contexto
- `create-issues.md` - Crear issues profesionalmente
- `complete-issues.md` - Completar issues profesionalmente
- `review-issues.md` - Revisar issues profesionalmente
- `create-projects.md` - Crear proyectos con issues iniciales
- `list-search.md` - Listar y buscar issues

**Uso:** Referenciar estos comandos cuando el orquestador necesite realizar operaciones en Linear.

## Checklist de Profesionalismo

### ⚠️ Antes de Crear el Orquestador

- [ ] ¿He leído el documento de contexto del proyecto (`docs/project-context.md`)?
- [ ] ¿He identificado las funciones principales del orquestador?
- [ ] ¿He definido las reglas de orquestación?
- [ ] ¿He integrado con comandos FUNCIONALES de Linear?

### Al Configurar el Orquestador

- [ ] ¿El orquestador tiene acceso a los comandos FUNCIONALES de Linear?
- [ ] ¿Las reglas siguen las convenciones del proyecto?
- [ ] ¿El orquestador usa el contexto del proyecto en sus decisiones?
- [ ] ¿El orquestador puede dividir features profesionalmente?

### Después de Configurar el Orquestador

- [ ] ¿El orquestador puede crear issues usando el comando FUNCIONAL create-issues.md?
- [ ] ¿El orquestador puede monitorear estados usando list-search.md?
- [ ] ¿El orquestador genera reportes útiles?
- [ ] ¿El orquestador gestiona dependencias correctamente?

## Consejos Finales

1. **⚠️ SIEMPRE lee el documento de contexto del proyecto** antes de crear el orquestador
2. **Usa comandos FUNCIONALES de Linear** en lugar de comandos experimentales
3. **Integra con comandos FUNCIONALES** para máxima efectividad
4. **Aplica el contexto del proyecto** en todas las decisiones
5. **Genera reportes regularmente** para mantener visibilidad
6. **Monitorea dependencias** para evitar bloqueos
7. **Reasigna tareas** cuando sea necesario según contexto del proyecto

## Referencias

- [Documento de Contexto del Proyecto](../../../docs/project-context.md) - Fuente única de verdad para contexto del proyecto
- [Comandos FUNCIONALES de Linear](../../../.cursor/commands/) - Comandos completamente funcionales y probados
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Crear issues profesionalmente
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Completar issues profesionalmente
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Listar y buscar issues

---