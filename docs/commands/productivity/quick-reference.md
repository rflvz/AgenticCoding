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

# Referencia Rápida de Comandos

Guía profesional de referencia rápida para comandos de Cursor y herramientas MCP de Linear.

## Filosofía: Entender la Diferencia

**⚠️ REGLA CRÍTICA: Es fundamental entender la diferencia entre comandos de Cursor y herramientas MCP:**

### Comandos de Cursor

Los **comandos de Cursor** son **prompts rápidos** que se activan escribiendo `/` seguido del nombre del comando. Son archivos Markdown en `.cursor/commands/` que proporcionan instrucciones al agente de IA.

**Ejemplos:**
- `/create-issues` - Activa el comando para crear issues profesionalmente
- `/complete-issues` - Activa el comando para completar issues profesionalmente
- `/review-issues` - Activa el comando para revisar issues profesionalmente

**Características:**
- Se activan con `/nombre-comando`
- Son prompts rápidos que guían al agente
- Están en archivos `.md` en `.cursor/commands/`
- Proporcionan instrucciones paso a paso al agente

### Herramientas MCP (Model Context Protocol)

Las **herramientas MCP** son funciones disponibles a través del protocolo MCP. El MCP de Linear proporciona herramientas (tools) que el agente puede usar, **NO son comandos de bash**.

**Ejemplos:**
- `@linear list issues` - Usa la herramienta MCP para listar issues
- `@linear create issue` - Usa la herramienta MCP para crear un issue
- `@linear update issue` - Usa la herramienta MCP para actualizar un issue

**Características:**
- Se usan con `@linear` seguido de la acción
- Son herramientas/funciones disponibles a través del MCP
- El agente las usa automáticamente cuando es necesario
- Proporcionan acceso directo a la API de Linear

### ¿Qué es MCP?

**MCP (Model Context Protocol)** es un protocolo que permite a los agentes de IA acceder a herramientas y recursos externos. El MCP de Linear proporciona herramientas que permiten al agente interactuar con Linear directamente.

**¿Qué hace el MCP de Linear?**
- Proporciona herramientas para interactuar con Linear
- Permite al agente crear, listar, actualizar issues
- Permite al agente gestionar proyectos y equipos
- Proporciona acceso a la API de Linear de forma segura

## Proceso de Uso Profesional

### Paso 1: Usar Comandos de Cursor

**⚠️ REGLA CRÍTICA: Los comandos de Cursor son prompts rápidos que guían al agente:**

#### Activar Comandos

Los comandos se activan escribiendo `/` seguido del nombre:

```
/create-issues
/complete-issues
/review-issues
```

**Uso profesional:**
- Usa comandos de Cursor para procesos completos y profesionales
- Los comandos proporcionan instrucciones paso a paso al agente
- Los comandos pueden usar herramientas MCP cuando sea necesario

#### Mezclar Comandos para Crear Prompts

**⚠️ REGLA CRÍTICA: Puedes mezclar comandos para crear prompts personalizados:**

Puedes combinar comandos o crear prompts que usen múltiples comandos:

```
Crea un issue usando /create-issues y luego completa el trabajo usando /complete-issues
```

O puedes crear prompts que combinen funcionalidades:

```
Usa /create-issues para crear el issue y luego /complete-issues para implementarlo
```

**Uso profesional:**
- Combina comandos según tus necesidades
- Crea prompts personalizados que usen múltiples comandos
- Los comandos pueden trabajar juntos para flujos complejos

### Paso 2: Usar Herramientas MCP de Linear

**⚠️ REGLA CRÍTICA: Las herramientas MCP se usan automáticamente por el agente, NO son comandos de bash:**

#### Herramientas Disponibles

El MCP de Linear proporciona herramientas que el agente puede usar:

- **Crear issues**: El agente puede usar herramientas MCP para crear issues
- **Listar issues**: El agente puede usar herramientas MCP para listar issues
- **Actualizar issues**: El agente puede usar herramientas MCP para actualizar issues
- **Gestionar proyectos**: El agente puede usar herramientas MCP para gestionar proyectos

**Uso profesional:**
- El agente usa las herramientas MCP automáticamente cuando es necesario
- Puedes pedirle al agente que use herramientas MCP específicas
- Recuerda que son herramientas MCP, no comandos de bash

#### Ejemplo de Uso

Cuando usas un comando como `/create-issues`, el agente:
1. Lee las instrucciones del comando
2. Usa las herramientas MCP de Linear necesarias
3. Crea el issue usando las herramientas MCP
4. Te proporciona el resultado

**No necesitas escribir comandos de bash** - el agente usa las herramientas MCP automáticamente.

### Paso 3: Crear Prompts Personalizados

**⚠️ REGLA CRÍTICA: Puedes crear prompts que combinen comandos y herramientas MCP:**

#### Ejemplo: Crear y Completar Issue

```
Crea un issue para implementar autenticación usando /create-issues, 
y luego usa /complete-issues para implementarlo completamente.
```

El agente:
1. Usa `/create-issues` para crear el issue profesionalmente
2. Usa las herramientas MCP de Linear necesarias
3. Usa `/complete-issues` para implementar el código
4. Usa las herramientas MCP de Linear para actualizar el issue

#### Ejemplo: Listar y Revisar Issues

```
Lista mis issues en progreso y luego usa /review-issues para revisar el primero.
```

El agente:
1. Usa herramientas MCP de Linear para listar issues
2. Usa `/review-issues` para revisar el issue seleccionado
3. Usa las herramientas MCP de Linear necesarias

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Esta referencia rápida complementa los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Comando `/create-issues` que usa herramientas MCP de Linear
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Comando `/complete-issues` que usa herramientas MCP de Linear
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Comando `/review-issues` que usa herramientas MCP de Linear
- [Crear Proyectos](../../../.cursor/commands/create-projects.md) - Comando que usa herramientas MCP de Linear
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Comando que usa herramientas MCP de Linear

**Cuándo usar cada uno:**
- **Comandos de Cursor** (`/create-issues`, etc.): Para procesos completos y profesionales
- **Herramientas MCP** (`@linear`): Se usan automáticamente por el agente cuando es necesario

## Flujos de Trabajo Rápidos

### Flujo 1: Crear Issue Rápido

```
Usa /create-issues para crear un issue de bug con toda la información necesaria.
```

El agente usa el comando `/create-issues` y las herramientas MCP de Linear necesarias.

### Flujo 2: Completar Issue

```
Usa /complete-issues para completar el issue DAW-27 profesionalmente.
```

El agente usa el comando `/complete-issues` y las herramientas MCP de Linear necesarias.

### Flujo 3: Mezclar Comandos

```
Crea un issue usando /create-issues y luego completa el trabajo usando /complete-issues.
```

El agente combina ambos comandos y usa las herramientas MCP de Linear necesarias.

## Checklist de Profesionalismo

### ⚠️ Al Usar Comandos

- [ ] ¿Entiendo la diferencia entre comandos de Cursor y herramientas MCP?
- [ ] ¿Estoy usando comandos de Cursor (`/create-issues`, etc.) para procesos completos?
- [ ] ¿Estoy dejando que el agente use herramientas MCP automáticamente?
- [ ] ¿Estoy combinando comandos cuando es necesario?

### Antes de Crear Prompts

- [ ] ¿He identificado qué comandos necesito?
- [ ] ¿He considerado cómo combinar comandos para mi flujo?
- [ ] ¿He dejado claro qué herramientas MCP pueden ser necesarias?

## Consejos Finales

1. **⚠️ Entiende la diferencia** - Comandos de Cursor son prompts rápidos, herramientas MCP son funciones
2. **Usa comandos de Cursor** - Para procesos completos y profesionales
3. **Combina comandos** - Crea prompts personalizados que usen múltiples comandos
4. **Deja que el agente use MCP** - Las herramientas MCP se usan automáticamente cuando es necesario
5. **Recuerda que MCP no es bash** - Son herramientas/funciones, no comandos de terminal
6. **Integra con comandos FUNCIONALES** - Para procesos completos y trabajo profesional

---
_Hecho por Cursor_
