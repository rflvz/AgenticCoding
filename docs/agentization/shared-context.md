# Contexto Compartido entre Agentes

Guía para sincronizar contexto entre múltiples chats/agentes en Cursor para trabajar coordinadamente en tareas complejas.

## Concepto

El contexto compartido permite que múltiples agentes trabajen coordinadamente, compartiendo información, estado del proyecto, y decisiones entre diferentes chats.

## Implementación

### 1. Archivo de Contexto Compartido

Crea un archivo central de contexto compartido:

#### `.cursor/memory/shared-context.md`

```markdown
# Contexto Compartido del Proyecto

Última actualización: 2025-01-15 10:30

## Estado del Proyecto

- Proyecto: Sistema de Autenticación
- Sprint: Sprint 5
- Fecha objetivo: 2025-02-15
- Estado general: En progreso

## Issues Activos

| ID | Título | Estado | Asignado | Prioridad |
|----|--------|--------|----------|-----------|
| ISSUE-123 | Implementar login | In Progress | @usuario | High |
| ISSUE-124 | Crear UI de login | In Progress | @usuario | High |
| ISSUE-125 | Sistema de notificaciones | Todo | - | Normal |

## Decisiones Recientes

- 2025-01-15: Usar Zustand para estado global (ADR-001)
- 2025-01-14: Implementar Context API para autenticación
- 2025-01-13: Migrar a Next.js App Router

## Bloqueos Actuales

- ISSUE-124: Esperando aprobación de diseño del equipo de diseño
- ISSUE-123: Revisando implementación de seguridad

## Próximos Pasos

1. Completar ISSUE-123 (login backend)
2. Revisar ISSUE-124 con equipo de diseño
3. Iniciar ISSUE-125 (sistema de notificaciones)

## Contexto de Código

- Último commit: abc123 - "feat: Implementar login básico"
- Branch actual: feature/ISSUE-123-login
- Archivos modificados recientemente:
  - src/components/Login.tsx
  - src/hooks/useAuth.ts
  - src/services/auth.ts
```

### 2. Referencias entre Agentes

Cada agente puede leer y actualizar el contexto compartido:

#### Agente 1 (Frontend)

```
Este agente trabaja en frontend y comparte contexto con otros agentes.

Lee .cursor/memory/shared-context.md para:
- Estado actual del proyecto
- Issues activos relacionados con frontend
- Decisiones que afectan el frontend

Actualiza este archivo cuando:
- Completes un issue de frontend
- Identifiques un bloqueo relacionado con frontend
- Hagas una decisión que afecte otros agentes
```

#### Agente 2 (Backend)

```
Este agente trabaja en backend y comparte contexto con otros agentes.

Lee .cursor/memory/shared-context.md para:
- Estado actual del proyecto
- Issues activos relacionados con backend
- Decisiones que afectan el backend

Actualiza este archivo cuando:
- Completes un issue de backend
- Identifiques un bloqueo relacionado con backend
- Hagas una decisión que afecte otros agentes
```

#### Agente 3 (Project Manager)

```
Este agente gestiona el proyecto y coordina con otros agentes.

Lee .cursor/memory/shared-context.md para:
- Estado general del proyecto
- Todos los issues activos
- Bloqueos y próximos pasos

Actualiza este archivo cuando:
- Cambies el estado de un issue
- Identifiques un nuevo bloqueo
- Actualices próximos pasos
```

## Sincronización de Contexto

### 1. Lectura de Contexto Compartido

Al iniciar un chat, lee el contexto compartido:

```
Al iniciar este chat, lee el contexto compartido:

Lee .cursor/memory/shared-context.md para:
- Estado actual del proyecto
- Issues activos
- Decisiones recientes
- Bloqueos actuales

Usa este contexto para:
- Mantener consistencia con otros agentes
- Evitar trabajo duplicado
- Coordinar con otros chats
```

### 2. Actualización de Contexto Compartido

Actualiza el contexto compartido cuando haya cambios:

```
Actualiza el contexto compartido con:
- Issue completado: ISSUE-123
- Nuevo issue creado: ISSUE-126
- Nuevo bloqueo identificado: Esperando aprobación de diseño
- Nueva decisión: Usar React Query para data fetching

Actualiza .cursor/memory/shared-context.md con estos cambios.
```

## Coordinación entre Agentes

### 1. Agentes Coordinados

Crea múltiples chats especializados que trabajen coordinadamente:

#### Chat 1: Agente Frontend

```
Eres un agente especializado en frontend.

Compartes contexto con otros agentes del proyecto.

Lee .cursor/memory/shared-context.md para contexto compartido.

Trabajas en:
- Componentes React
- UI/UX
- Frontend issues

Coordinas con:
- Agente Backend (para APIs)
- Agente PM (para prioridades)
```

#### Chat 2: Agente Backend

```
Eres un agente especializado en backend.

Compartes contexto con otros agentes del proyecto.

Lee .cursor/memory/shared-context.md para contexto compartido.

Trabajas en:
- APIs y servicios
- Base de datos
- Backend issues

Coordinas con:
- Agente Frontend (para endpoints)
- Agente PM (para prioridades)
```

#### Chat 3: Agente PM

```
Eres un agente especializado en project management.

Coordinas con otros agentes del proyecto.

Lee y actualiza .cursor/memory/shared-context.md regularmente.

Gestionas:
- Prioridades de issues
- Bloqueos y dependencias
- Reportes de progreso

Coordinas con:
- Todos los agentes especializados
```

### 2. Workflow de Coordinación

```
Workflow: Coordinación Multi-Agente

1. Agente PM actualiza contexto compartido con:
   - Nuevos issues
   - Cambios de prioridad
   - Bloqueos identificados

2. Agentes especializados leen contexto compartido:
   - Frontend: Trabaja en issues de frontend
   - Backend: Trabaja en issues de backend

3. Agentes actualizan contexto compartido cuando:
   - Completan un issue
   - Identifican un bloqueo
   - Hacen una decisión importante

4. Agente PM monitorea y ajusta según progreso
```

## Ejemplos de Uso

### Ejemplo 1: Desarrollo de Feature

```
Feature: Sistema de Login

Agente Frontend (Chat 1):
- Lee contexto compartido
- Ve ISSUE-124: Crear UI de login
- Trabaja en componente Login.tsx
- Actualiza contexto: "ISSUE-124 en progreso"

Agente Backend (Chat 2):
- Lee contexto compartido
- Ve ISSUE-123: Implementar login
- Trabaja en API de autenticación
- Actualiza contexto: "ISSUE-123 en progreso"

Agente PM (Chat 3):
- Lee contexto compartido
- Monitorea progreso de ambos issues
- Identifica bloqueo: Frontend necesita API
- Actualiza contexto: "Bloqueo: ISSUE-124 depende de ISSUE-123"
```

### Ejemplo 2: Resolver Bloqueo

```
Bloqueo: Diseño no aprobado

Agente Frontend:
- Identifica bloqueo en ISSUE-124
- Actualiza contexto: "Bloqueo: Esperando aprobación de diseño"

Agente PM:
- Lee contexto compartido
- Ve bloqueo en ISSUE-124
- Reasigna prioridad o recursos
- Actualiza contexto: "Bloqueo resuelto: Diseño aprobado"

Agente Frontend:
- Lee contexto compartido actualizado
- Ve que bloqueo está resuelto
- Continúa trabajo en ISSUE-124
```

## Mejores Prácticas

### 1. Mantener Contexto Actualizado

- ✅ Actualiza contexto compartido regularmente
- ✅ Usa fechas/horarios de última actualización
- ✅ Documenta cambios importantes
- ❌ No dejes contexto desactualizado

### 2. Coordinación Efectiva

- ✅ Lee contexto antes de empezar trabajo
- ✅ Actualiza contexto cuando cambies algo
- ✅ Comunica bloqueos y decisiones importantes
- ❌ No trabajes sin leer contexto compartido

### 3. Organización del Contexto

- ✅ Mantén estructura clara y navegable
- ✅ Organiza por categorías (issues, decisiones, bloqueos)
- ✅ Usa tablas o listas para mejor legibilidad
- ❌ No mezcles información no relacionada

## Referencias

- Ver gestión de memoria en `docs/agentization/memory-management.md`
- Ver agentes expertos en `docs/agents/expert-agents.md`
- Ver workflows en `docs/workflows/multi-agent-orchestration.md`

