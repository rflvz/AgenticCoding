# Guía de Agentización de Código con Cursor

Guía de referencia rápida para agentización profesional de código usando Cursor, incluyendo configuración de MCPs, comandos avanzados, técnicas de contextualización de agentes y mejores prácticas.

> **⚠️ FUNCIONAL vs EXPERIMENTAL**
>
> **IMPORTANTE:** Esta guía contiene tanto comandos **FUNCIONALES** (completamente funcionales y probados) como comandos **EXPERIMENTALES** (en desarrollo). Siempre usa primero los comandos FUNCIONALES.
>
> **✅ Comandos FUNCIONALES:** 
> - Ubicados en `.cursor/commands/` - Comandos funcionales en general
> - Ubicados en `docs/commands/linear/` - Comandos funcionales de Linear
> - Completamente funcionales y probados
>
> **⚠️ Comandos EXPERIMENTALES:** 
> - Ubicados en `docs/commands/agentization/` - Comandos experimentales de agentización
> - Ubicados en `docs/commands/productivity/` - Comandos experimentales de productividad
> - En desarrollo, no confiar ciegamente
>
> **Workflow Principal FUNCIONAL:** `initialize-project-context` → `create-projects` → `create-issues` → `complete-issues` → `review-issues`

## Índice

### Setup
- [Configuración MCP de Linear](./docs/setup/mcp-linear.md) - Instalación y configuración del MCP de Linear
- [Configuración MCP de GitHub](./docs/setup/mcp-github.md) - Instalación y configuración del MCP de GitHub
- [Configuración MCP de Slack/Discord](./docs/setup/mcp-slack.md) - Instalación y configuración de notificaciones

### Comandos FUNCIONALES (✅ Completamente Funcionales)

**Ubicaciones:** `.cursor/commands/` y `docs/commands/linear/`

#### Linear (FUNCIONALES)

**En `.cursor/commands/` (comandos funcionales en general):**
- ✅ [Inicializar Contexto del Proyecto](./.cursor/commands/initialize-project-context.md) - Crear documento de contexto centralizado
- ✅ [Crear Issues](./.cursor/commands/create-issues.md) - Comandos para crear issues en Linear
- ✅ [Crear Proyectos](./.cursor/commands/create-projects.md) - Comandos para crear proyectos en Linear
- ✅ [Completar Issues](./.cursor/commands/complete-issues.md) - Comandos para completar y actualizar issues
- ✅ [Revisar Issues](./.cursor/commands/review-issues.md) - Comandos para revisar issues en estado "In Review"
- ✅ [Listar y Buscar](./.cursor/commands/list-search.md) - Comandos para listar y buscar issues

**En `docs/commands/linear/` (comandos funcionales de Linear):**
- ✅ [Inicializar Contexto del Proyecto](./docs/commands/linear/initialize-project-context.md) - Crear documento de contexto centralizado
- ✅ [Crear Issues](./docs/commands/linear/create-issues.md) - Comandos para crear issues en Linear
- ✅ [Crear Proyectos](./docs/commands/linear/create-projects.md) - Comandos para crear proyectos en Linear
- ✅ [Completar Issues](./docs/commands/linear/complete-issues.md) - Comandos para completar y actualizar issues
- ✅ [Revisar Issues](./docs/commands/linear/review-issues.md) - Comandos para revisar issues en estado "In Review"
- ✅ [Listar y Buscar](./docs/commands/linear/list-search.md) - Comandos para listar y buscar issues

### Comandos EXPERIMENTALES (⚠️ En Desarrollo)

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

