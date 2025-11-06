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
>     
>     Estos comandos se activan en tu proyecto simplemente poniendo:
>     `/el-comando`
>     Por ejemplo: `/create-issues`, `/complete-issues`, `/review-issues`

# Flujos de Trabajo Rápidos

Guía profesional de flujos de trabajo comunes usando comandos de Cursor y herramientas MCP de Linear.

## Filosofía: Flujos de Trabajo Eficientes

Los flujos de trabajo eficientes **multiplican la productividad**. Actúa como un **desarrollador profesional** que:

1. **Usa comandos de Cursor** (`/create-issues`, `/complete-issues`, etc.) para procesos completos
2. **Combina comandos** para crear flujos personalizados
3. **Deja que el agente use herramientas MCP** automáticamente cuando sea necesario
4. **Crea issues completos** con estados, prioridades, labels y descripciones
5. **Documenta el trabajo** realizado

## Proceso de Uso Profesional de Workflows

### Paso 1: Flujos de Trabajo Básicos (Esenciales)

**⚠️ REGLA CRÍTICA: Estos flujos usan comandos de Cursor, NO comandos de bash:**

#### Crear Issue desde Error

**Problema:** Crear issues manualmente desde errores es lento y propenso a errores.

**Solución:** Usa el comando de Cursor para crear issues profesionalmente:

```
Usa /create-issues para crear un issue de bug basándote en este error:
[descripción del error]
```

El agente:
1. Usa el comando `/create-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para crear el issue
3. Añade estado, prioridad, labels y descripción completa
4. Te proporciona el issue creado

**Uso profesional:**
- Usa `/create-issues` para crear issues profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El issue se crea con toda la información necesaria

#### Completar Issue Actual

**Problema:** Completar issues manualmente es lento y puede olvidar pasos.

**Solución:** Usa el comando de Cursor para completar issues profesionalmente:

```
Usa /complete-issues para completar el issue DAW-27 profesionalmente.
```

El agente:
1. Usa el comando `/complete-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para obtener y actualizar el issue
3. Implementa el código necesario
4. Crea Pull Request si es necesario
5. Mueve el issue a "In Review"

**Uso profesional:**
- Usa `/complete-issues` para completar issues profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El proceso incluye implementación, PR y revisión

#### Revisar Issues Pendientes

**Problema:** Revisar issues manualmente es lento y puede pasar por alto detalles.

**Solución:** Usa el comando de Cursor para revisar issues profesionalmente:

```
Usa /review-issues para revisar el issue DAW-27 que está en "In Review".
```

El agente:
1. Usa el comando `/review-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para obtener el issue
3. Revisa el código y Pull Request
4. Verifica criterios de aceptación
5. Aprueba o solicita cambios

**Uso profesional:**
- Usa `/review-issues` para revisar issues profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El proceso incluye revisión completa de código y PR

### Paso 2: Flujos de Trabajo con Combinación de Comandos (Avanzados)

**⚠️ REGLA CRÍTICA: Puedes combinar comandos para crear flujos personalizados:**

#### Crear y Completar Issue

**Problema:** Crear y completar issues por separado es lento.

**Solución:** Combina comandos para crear flujos personalizados:

```
Crea un issue para implementar autenticación usando /create-issues, 
y luego usa /complete-issues para implementarlo completamente.
```

El agente:
1. Usa `/create-issues` para crear el issue profesionalmente
2. Usa herramientas MCP de Linear para crear el issue
3. Usa `/complete-issues` para implementar el código
4. Usa herramientas MCP de Linear para actualizar el issue
5. Crea Pull Request y mueve a "In Review"

**Uso profesional:**
- Combina comandos según tus necesidades
- Crea flujos personalizados que usen múltiples comandos
- El agente usa herramientas MCP automáticamente

#### Listar y Revisar Issues

**Problema:** Listar y revisar issues manualmente es lento.

**Solución:** Combina comandos para crear flujos personalizados:

```
Lista mis issues en progreso y luego usa /review-issues para revisar el primero.
```

El agente:
1. Usa herramientas MCP de Linear para listar issues
2. Usa `/review-issues` para revisar el issue seleccionado
3. Usa herramientas MCP de Linear para actualizar el issue

**Uso profesional:**
- Combina comandos para flujos complejos
- Deja que el agente use herramientas MCP automáticamente
- Crea flujos personalizados según necesidades

### Paso 3: Flujos de Trabajo de Desarrollo (Profesionales)

**⚠️ REGLA CRÍTICA: Estos flujos usan comandos de Cursor y herramientas MCP:**

#### Iniciar Trabajo en Issue

**Problema:** Iniciar trabajo sin actualizar estado dificulta tracking.

**Solución:** Usa el comando de Cursor para iniciar trabajo profesionalmente:

```
Usa /complete-issues para empezar a trabajar en el issue DAW-27.
```

El agente:
1. Usa el comando `/complete-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para obtener el issue
3. Actualiza el estado a "In Progress"
4. Crea branch y Pull Request si es necesario
5. Comienza la implementación

**Uso profesional:**
- Usa `/complete-issues` para iniciar trabajo profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El proceso incluye actualización de estado y creación de branch

#### Completar Trabajo en Issue

**Problema:** Completar trabajo sin documentar dificulta tracking y revisión.

**Solución:** Usa el comando de Cursor para completar trabajo profesionalmente:

```
Usa /complete-issues para completar el issue DAW-27 completamente.
```

El agente:
1. Usa el comando `/complete-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para obtener el issue
3. Implementa el código necesario
4. Crea Pull Request
5. Mueve el issue a "In Review"
6. Añade comentarios con contexto técnico

**Uso profesional:**
- Usa `/complete-issues` para completar trabajo profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El proceso incluye implementación, PR y documentación

#### Crear Issue desde Bug Encontrado

**Problema:** Crear issues manualmente desde bugs es lento y propenso a errores.

**Solución:** Usa el comando de Cursor para crear issues profesionalmente:

```
Usa /create-issues para crear un issue de bug basándote en este error:
[descripción del bug]
```

El agente:
1. Usa el comando `/create-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para crear el issue
3. Añade estado, prioridad, labels y descripción completa
4. Te proporciona el issue creado

**Uso profesional:**
- Usa `/create-issues` para crear issues profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El issue se crea con toda la información necesaria

### Paso 4: Flujos de Trabajo de Revisión (Profesionales)

**⚠️ REGLA CRÍTICA: Estos flujos usan comandos de Cursor y herramientas MCP:**

#### Revisar Código y Crear Issues

**Problema:** Revisar código manualmente y crear issues es lento y propenso a errores.

**Solución:** Usa el comando de Cursor para crear issues profesionalmente:

```
Revisa este código y usa /create-issues para crear issues para cada problema encontrado.
```

El agente:
1. Revisa el código proporcionado
2. Identifica problemas (bugs, vulnerabilidades, mejoras)
3. Usa `/create-issues` para crear issues profesionalmente
4. Usa herramientas MCP de Linear para crear cada issue
5. Añade estado, prioridad, labels y descripción completa

**Uso profesional:**
- Usa `/create-issues` para crear issues profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- Cada issue se crea con toda la información necesaria

#### Verificar Fix de Bug

**Problema:** Verificar fixes manualmente es lento y puede pasar por alto problemas.

**Solución:** Usa el comando de Cursor para verificar fixes profesionalmente:

```
Usa /review-issues para verificar que el fix del bug está correctamente implementado.
```

El agente:
1. Usa el comando `/review-issues` que proporciona instrucciones paso a paso
2. Usa herramientas MCP de Linear para obtener el issue
3. Verifica que el fix esté implementado
4. Revisa el código y Pull Request
5. Actualiza el issue apropiadamente

**Uso profesional:**
- Usa `/review-issues` para verificar fixes profesionalmente
- El agente usa herramientas MCP de Linear automáticamente
- El proceso incluye verificación completa

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Estos workflows usan los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Comando `/create-issues` que usa herramientas MCP de Linear
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Comando `/complete-issues` que usa herramientas MCP de Linear
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Comando `/review-issues` que usa herramientas MCP de Linear
- [Crear Proyectos](../../../.cursor/commands/create-projects.md) - Comando que usa herramientas MCP de Linear
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Comando que usa herramientas MCP de Linear

**Cuándo usar cada uno:**
- **Workflows (este documento)**: Para flujos de trabajo rápidos y comunes
- **Comandos FUNCIONALES**: Para procesos completos y trabajo profesional

## Checklist de Profesionalismo

### ⚠️ Al Usar Workflows

- [ ] ¿He identificado el workflow apropiado para mi tarea?
- [ ] ¿Estoy usando comandos de Cursor (`/create-issues`, etc.) para procesos completos?
- [ ] ¿Estoy dejando que el agente use herramientas MCP automáticamente?
- [ ] ¿Estoy combinando comandos cuando es necesario?

### Antes de Ejecutar Workflow

- [ ] ¿He revisado el workflow completamente?
- [ ] ¿Tengo el contexto necesario para ejecutar el workflow?
- [ ] ¿He verificado que el workflow es apropiado para mi tarea?

## Consejos Finales

1. **⚠️ Usa comandos de Cursor** - Para procesos completos y profesionales
2. **Combina comandos** - Crea flujos personalizados que usen múltiples comandos
3. **Deja que el agente use MCP** - Las herramientas MCP se usan automáticamente cuando es necesario
4. **Crea issues completos** - Siempre incluye estado, prioridad, labels y descripción
5. **Documenta el trabajo** - Añade comentarios con contexto técnico
6. **Integra con comandos FUNCIONALES** - Para procesos completos y trabajo profesional

---
_Hecho por Cursor_
