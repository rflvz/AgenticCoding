# Guía de Agentización de Código con Cursor

Guía de referencia rápida para agentización profesional de código usando Cursor, incluyendo configuración de MCPs, comandos avanzados, técnicas de contextualización de agentes y mejores prácticas.

> **⚠️ FUNCIONAL vs EXPERIMENTAL**
>
> **IMPORTANTE:** Esta guía contiene tanto comandos **FUNCIONALES** (completamente funcionales y probados) como comandos **EXPERIMENTALES** (en desarrollo). Siempre usa primero los comandos FUNCIONALES.
>
> **✅ Comandos FUNCIONALES - SOLO COMANDOS DE LINEAR:**
> - **Los comandos de Linear son los únicos FUNCIONALES** - Completamente funcionales y probados
> - Ubicados en `.cursor/commands/` - Comandos funcionales de Linear en general
> - Ubicados en `docs/commands/linear/` - Comandos funcionales de Linear específicos
> - **Solo estos comandos están completamente funcionales y probados**
>
> **⚠️ Comandos EXPERIMENTALES - TODOS LOS DEMÁS:**
> - **Todos los demás comandos son EXPERIMENTALES** - En desarrollo, no confiar ciegamente
> - Ubicados en `docs/commands/agentization/` - Comandos experimentales de agentización
> - Ubicados en `docs/commands/productivity/` - Comandos experimentales de productividad
> - **Estos comandos están en desarrollo y no deben usarse sin precaución**
>
> **Workflow Principal FUNCIONAL (solo comandos de Linear):** `initialize-project-context` → `create-projects` → `create-issues` → `complete-issues` → `review-issues`

## Índice

### Setup
- [Configuración MCP de Linear](./docs/setup/mcp-linear.md) - Instalación y configuración del MCP de Linear
- [Configuración MCP de GitHub](./docs/setup/mcp-github.md) - Instalación y configuración del MCP de GitHub
- [Configuración MCP de Slack/Discord](./docs/setup/mcp-slack.md) - Instalación y configuración de notificaciones

### Comandos FUNCIONALES (✅ Completamente Funcionales)

> **⚠️ IMPORTANTE:** **Solo los comandos de Linear son FUNCIONALES.** Todos los demás comandos son EXPERIMENTALES.

**Ubicaciones:** `.cursor/commands/` (comandos de Linear) y `docs/commands/linear/` (comandos de Linear)

#### Linear (FUNCIONALES - Los únicos comandos funcionales)

**En `.cursor/commands/` (comandos funcionales de Linear):**
- ✅ [Inicializar Contexto del Proyecto](./.cursor/commands/initialize-project-context.md) - Crear documento de contexto centralizado
- ✅ [Crear Issues](./.cursor/commands/create-issues.md) - Comandos para crear issues en Linear
- ✅ [Crear Proyectos](./.cursor/commands/create-projects.md) - Comandos para crear proyectos en Linear
- ✅ [Completar Issues](./.cursor/commands/complete-issues.md) - Comandos para completar y actualizar issues
- ✅ [Revisar Issues](./.cursor/commands/review-issues.md) - Comandos para revisar issues en estado "In Review"
- ✅ [Listar y Buscar](./.cursor/commands/list-search.md) - Comandos para listar y buscar issues

**En `docs/commands/linear/` (comandos funcionales de Linear - duplicados):**
- ✅ [Inicializar Contexto del Proyecto](./docs/commands/linear/initialize-project-context.md) - Crear documento de contexto centralizado
- ✅ [Crear Issues](./docs/commands/linear/create-issues.md) - Comandos para crear issues en Linear
- ✅ [Crear Proyectos](./docs/commands/linear/create-projects.md) - Comandos para crear proyectos en Linear
- ✅ [Completar Issues](./docs/commands/linear/complete-issues.md) - Comandos para completar y actualizar issues
- ✅ [Revisar Issues](./docs/commands/linear/review-issues.md) - Comandos para revisar issues en estado "In Review"
- ✅ [Listar y Buscar](./docs/commands/linear/list-search.md) - Comandos para listar y buscar issues

### Comandos EXPERIMENTALES (⚠️ En Desarrollo)

> **⚠️ IMPORTANTE:** **Todos los comandos que NO son de Linear son EXPERIMENTALES.** Solo los comandos de Linear son FUNCIONALES.

**Ubicaciones:** `docs/commands/agentization/` y `docs/commands/productivity/`

#### Agentización (EXPERIMENTALES)
- ⚠️ [Agente Orquestador](./docs/commands/agentization/agent-orchestrator.md) - Agente especializado en project management
- ⚠️ [Contextualización de Agentes](./docs/commands/agentization/agent-context.md) - Comandos para contextualizar agentes
- ⚠️ [Roles de Agentes](./docs/commands/agentization/agent-roles.md) - Definición de roles especializados
- ⚠️ [Flujos de Trabajo](./docs/commands/agentization/agent-workflows.md) - Workflows que combinan agentización con Linear

#### Productividad (EXPERIMENTALES)
- ⚠️ [Atajos de Teclado](./docs/commands/productivity/keyboard-shortcuts.md) - Atajos de teclado de Cursor
- ⚠️ [Referencia Rápida](./docs/commands/productivity/quick-reference.md) - Comandos rápidos y referencias esenciales
- ⚠️ [Variables Útiles](./docs/commands/productivity/variables.md) - Variables y parámetros especiales
- ⚠️ [Consejos de Productividad](./docs/commands/productivity/tips.md) - Consejos y técnicas para maximizar productividad
- ⚠️ [Flujos de Trabajo Rápidos](./docs/commands/productivity/workflows.md) - Flujos de trabajo comunes

### Agentes
- [Agentes Expertos](./docs/agents/expert-agents.md) - Técnicas de creación y contextualización de agentes especializados
- [Agentes Especializados por Tecnología](./docs/agents/tech-specialized/) - Agentes para React, Python, Node.js, DevOps
  - [Agente React/Next.js](./docs/agents/tech-specialized/react-expert.md)
  - [Agente Python/Django/FastAPI](./docs/agents/tech-specialized/python-expert.md)
  - [Agente TypeScript/Node.js](./docs/agents/tech-specialized/nodejs-expert.md)
  - [Agente DevOps/CI-CD](./docs/agents/tech-specialized/devops-expert.md)
- [Agentes de Contexto Dinámico](./docs/agents/context-aware/) - Agentes adaptativos por tipo de archivo y directorio
  - [Agentes por Tipo de Archivo](./docs/agents/context-aware/file-type-agents.md)
  - [Agentes por Directorio](./docs/agents/context-aware/directory-agents.md)
- [Agentes de Automatización](./docs/agents/automation/) - Agentes especializados en automatización
  - [Agente de Documentación](./docs/agents/automation/documentation-agent.md)
  - [Agente de Testing](./docs/agents/automation/testing-agent.md)
  - [Agente de Refactoring](./docs/agents/automation/refactoring-agent.md)
  - [Agente de Code Review](./docs/agents/automation/code-review-agent.md)

### Reglas
- [Mejores Prácticas](./docs/rules/best-practices.md) - Reglas, patrones y anti-patterns

### Agentización Avanzada
- [Contexto del Proyecto](./docs/project-context.md) - Documento centralizado de contexto del proyecto y Linear
- [Gestión de Memoria](./docs/agentization/memory-management.md) - Técnicas para mantener contexto entre sesiones
- [Contexto Compartido](./docs/agentization/shared-context.md) - Sincronización de contexto entre múltiples agentes
- [Métricas y Tracking](./docs/agentization/metrics-tracking.md) - Tracking de uso y eficiencia de agentes
- [Análisis de Productividad](./docs/agentization/productivity-analysis.md) - Análisis de productividad y ROI

### Workflows
- [Orquestación Multi-Agente](./docs/workflows/multi-agent-orchestration.md) - Coordinación de múltiples agentes especializados
- [Workflow de Feature Completa](./docs/workflows/feature-complete-workflow.md) - Desarrollo completo desde diseño hasta deployment

### Troubleshooting
- [Problemas Comunes](./docs/troubleshooting/common-issues.md) - Solución de problemas comunes y debugging

### Ejemplos
- [Ejemplos de Configuración](./examples/) - Configuraciones listas para usar
- [Templates de .cursorrules](./examples/cursorrules-templates/) - Templates predefinidos para diferentes tipos de proyectos
- [Configuraciones de Agentes](./examples/agent-configs/) - Configuraciones predefinidas de agentes especializados

## Inicio Rápido

### Workflow Principal FUNCIONAL

**Sigue este flujo para trabajar con Linear en Cursor:**

1. **Inicializar Contexto del Proyecto**
   ```bash
   # Usa: .cursor/commands/initialize-project-context.md
   # O: docs/commands/linear/initialize-project-context.md
   # Crea el documento de contexto centralizado del proyecto
   ```

2. **Crear Proyecto en Linear**
   ```bash
   # Usa: .cursor/commands/create-projects.md
   # O: docs/commands/linear/create-projects.md
   # Crea un nuevo proyecto con issues iniciales
   ```

3. **Crear Issues en Linear**
   ```bash
   # Usa: .cursor/commands/create-issues.md
   # O: docs/commands/linear/create-issues.md
   # Crea issues profesionalmente con toda la información necesaria
   ```

4. **Completar Issues**
   ```bash
   # Usa: .cursor/commands/complete-issues.md
   # O: docs/commands/linear/complete-issues.md
   # Implementa código y mueve issues a "In Review"
   ```

5. **Revisar Issues**
   ```bash
   # Usa: .cursor/commands/review-issues.md
   # O: docs/commands/linear/review-issues.md
   # Revisa issues en "In Review" y aprueba o solicita cambios
   ```

### Configuración Inicial

1. **Configurar MCP de Linear**
   ```bash
   # Ver: docs/setup/mcp-linear.md
   ```

2. **Usar un agente experto**
   ```bash
   # Ver: docs/agents/expert-agents.md
   ```

3. **Aplicar reglas de uso**
   ```bash
   # Ver: docs/rules/best-practices.md
   ```

## ¿Por Qué Linear con MCP Mejora el Rendimiento?

### Ventajas de Rendimiento y Gestión de Contexto

La integración de Linear mediante **MCP (Model Context Protocol)** y conexión normal proporciona ventajas significativas en rendimiento y gestión de contexto que transforman cómo trabajas con Cursor:

#### 🚀 Rendimiento Mejorado

**1. Acceso Directo y Optimizado**
- **Sin intermediarios**: El MCP permite comunicación directa entre Cursor y Linear, eliminando capas innecesarias
- **Consultas eficientes**: Las herramientas MCP están optimizadas para consultas rápidas y precisas
- **Menor latencia**: La conexión directa reduce el tiempo de respuesta comparado con métodos indirectos
- **Operaciones atómicas**: Las operaciones en Linear se ejecutan de forma más eficiente mediante MCP

**2. Paralelización de Operaciones**
- **Múltiples consultas simultáneas**: Puedes realizar varias operaciones en Linear al mismo tiempo sin bloquear el flujo
- **Procesamiento asíncrono**: Las operaciones no bloquean la interfaz de Cursor
- **Optimización de red**: El MCP gestiona eficientemente las conexiones y reduce overhead

**3. Caché y Optimización Inteligente**
- **Caché de contexto**: El MCP puede cachear información frecuentemente accedida
- **Consultas selectivas**: Solo se obtiene la información necesaria, no datasets completos
- **Reducción de llamadas**: Operaciones combinadas reducen el número de requests

#### 🧠 Ventana de Contexto Más Pequeña

**1. Contexto Externo vs Contexto Interno**

**Sin Linear con MCP:**
- ❌ Todo el contexto del proyecto debe estar en la ventana de chat
- ❌ Información de issues, proyectos, y estado debe copiarse manualmente
- ❌ El contexto del chat crece exponencialmente con cada conversación
- ❌ Límites de tokens se alcanzan rápidamente con información repetitiva

**Con Linear con MCP:**
- ✅ El contexto del proyecto vive en Linear, no en el chat
- ✅ Solo se consulta información específica cuando se necesita
- ✅ La ventana de chat se mantiene enfocada en la tarea actual
- ✅ El contexto se actualiza dinámicamente sin ocupar tokens del chat

**2. Memoria Externa Persistente**

```
Chat Context (Pequeño)          Linear (Memoria Externa)
┌─────────────────┐            ┌──────────────────────┐
│ Tarea actual    │  ────────> │ Issues completos      │
│ Código relevante│            │ Estado del proyecto  │
│ Decisión actual │            │ Historial completo   │
└─────────────────┘            │ Dependencias         │
                               │ Criterios aceptación │
                               └──────────────────────┘
```

**3. Consultas Bajo Demanda**

- **Solo cuando se necesita**: El agente consulta Linear solo cuando requiere información específica
- **Información fresca**: Siempre obtiene el estado actualizado, no versiones obsoletas del contexto
- **Sin duplicación**: No necesitas repetir información que ya está en Linear
- **Contexto selectivo**: Solo se incluye en el chat lo estrictamente necesario para la tarea actual

**4. Ejemplo Práctico**

**Sin MCP (Contexto Grande):**
```
Chat: "Implementa feature X. El issue DAW-123 dice que necesitamos 
autenticación OAuth2. El proyecto tiene 15 issues relacionados. 
El equipo está trabajando en 3 features paralelas. El estado 
actual es... [500+ tokens de contexto]"
```

**Con MCP (Contexto Pequeño):**
```
Chat: "Implementa feature X"
Agente: [Consulta Linear: get_issue("DAW-123")]
Agente: [Obtiene solo la información necesaria]
Agente: [Implementa con contexto mínimo]
```

#### 📊 Comparativa de Impacto

| Métrica | Sin MCP | Con MCP | Mejora |
|---------|---------|---------|--------|
| **Tokens por conversación** | 2000-5000 | 500-1500 | **70% reducción** |
| **Tiempo de respuesta** | 2-5s | 0.5-1s | **75% más rápido** |
| **Consultas simultáneas** | 1 | Múltiples | **Paralelización** |
| **Contexto obsoleto** | Frecuente | Nunca | **100% actualizado** |
| **Límite de tokens alcanzado** | Frecuente | Raro | **90% menos problemas** |

#### 🎯 Beneficios Clave

1. **Chats más enfocados**: Cada chat se mantiene pequeño y específico a la tarea
2. **Mejor rendimiento**: Operaciones más rápidas y eficientes
3. **Contexto siempre actualizado**: La información viene directamente de Linear
4. **Escalabilidad**: Puedes trabajar en proyectos grandes sin problemas de contexto
5. **Múltiples chats simultáneos**: Cada chat puede ser pequeño porque el contexto está en Linear
6. **Historial completo**: Todo el historial del proyecto está disponible sin ocupar tokens del chat

#### 💡 Mejores Prácticas

- **Usa Linear como memoria externa**: No copies información de Linear al chat
- **Consulta bajo demanda**: Deja que el agente consulte Linear cuando necesite información
- **Mantén chats enfocados**: Cada chat debe tener un propósito específico
- **Confía en el MCP**: El MCP gestiona eficientemente las conexiones y consultas

## Contenido

Esta guía está diseñada para usuarios avanzados que buscan maximizar la productividad con Cursor mediante:

- **MCPs (Model Context Protocol)**: Integración con herramientas externas (Linear, GitHub, Slack/Discord)
- **Comandos Avanzados**: Automatización de tareas comunes
- **Agentes Especializados**: Contextualización de chats para tareas específicas por tecnología y contexto
- **Agentes de Automatización**: Generación automática de tests, documentación, refactoring y code review
- **Orquestación Multi-Agente**: Coordinación de múltiples agentes especializados para tareas complejas
- **Gestión de Memoria y Contexto**: Mantenimiento de contexto persistente entre sesiones
- **Métricas y Análisis**: Tracking de uso y análisis de productividad
- **Mejores Prácticas**: Reglas y patrones para uso efectivo

## Contribuir

Si encuentras mejoras o nuevas técnicas, considera contribuir a esta guía.

