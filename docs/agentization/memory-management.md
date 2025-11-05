# Gestión de Memoria y Contexto Persistente

Guía para mantener contexto y memoria entre sesiones de trabajo con agentes en Cursor.

## Concepto

La gestión de memoria permite que los agentes mantengan información entre sesiones, recordando decisiones previas, contexto del proyecto, y preferencias del usuario.

## Técnicas de Memoria Persistente

### 1. Archivos de Memoria

Crea archivos de memoria para almacenar contexto que persiste entre sesiones.

#### `.cursor/memory/agent-context.md`

```markdown
# Contexto del Agente

Última actualización: 2025-01-15

## Proyecto Actual

- Nombre: Sistema de Autenticación
- Stack: React, Node.js, PostgreSQL
- Equipo: Engineering

## Decisiones Previas

- Usamos TypeScript estricto
- Preferimos componentes funcionales sobre clases
- Usamos Context API para estado global
- Testing con Jest y React Testing Library

## Preferencias del Usuario

- Formato de issues: "[Type]: [Descripción]"
- Labels estándar: frontend, backend, bug, feature
- Prioridad por defecto: Normal
- Equipo por defecto: Engineering

## Contexto de Trabajo Actual

- Feature actual: Sistema de autenticación
- Issues relacionados:
  - ISSUE-123: Implementar login
  - ISSUE-124: Crear UI de login
- Estado: En progreso

## Notas Importantes

- Evitar crear issues duplicados
- Verificar issues similares antes de crear nuevos
- Usar emojis en mensajes de Slack cuando sea apropiado
```

#### `.cursor/memory/project-context.md`

```markdown
# Contexto del Proyecto

## Arquitectura

- Frontend: React + Next.js
- Backend: Node.js + Express
- Database: PostgreSQL
- Testing: Jest + React Testing Library

## Convenciones

### Código
- TypeScript estricto
- ESLint + Prettier
- Componentes funcionales
- Hooks personalizados para lógica reutilizable

### Git
- Commits en inglés
- Formato: "type: description"
- Branch naming: "feature/ISSUE-123-description"

### Issues
- Formato: "[Type]: [Descripción]"
- Labels estándar: frontend, backend, bug, feature, refactor
- Equipo: Engineering

## Equipos y Personas

- Engineering: Equipo principal de desarrollo
- Design: Equipo de diseño
- Product: Equipo de producto

## Configuración

- MCPs configurados: Linear, GitHub
- Notificaciones: Slack #dev-notifications
- Reportes: Diarios a las 9:00 AM
```

### 2. Referencias a Archivos de Memoria

Incluye archivos de memoria en el contexto del agente:

```
Contextualiza este agente con el contexto del proyecto.

Lee el archivo .cursor/memory/agent-context.md para:
- Decisiones previas del proyecto
- Preferencias del usuario
- Contexto de trabajo actual

Usa este contexto al crear issues y trabajar en el proyecto.
```

### 3. Actualización de Memoria

Actualiza archivos de memoria cuando haya cambios importantes:

```
Actualiza el archivo de memoria con:
- Nueva feature iniciada: Sistema de notificaciones
- Nuevo issue creado: ISSUE-125
- Nueva decisión: Usar Zustand para estado global
```

## Contexto Compartido entre Agentes

### 1. Archivo de Contexto Compartido

Crea un archivo de contexto compartido entre múltiples chats:

#### `.cursor/memory/shared-context.md`

```markdown
# Contexto Compartido

Última actualización: 2025-01-15

## Estado del Proyecto

- Sprint actual: Sprint 5
- Fecha objetivo: 2025-02-15
- Prioridad: Alta para features de autenticación

## Issues Activos

- ISSUE-123: Implementar login (In Progress)
- ISSUE-124: Crear UI de login (In Progress)
- ISSUE-125: Sistema de notificaciones (Todo)

## Decisiones Recientes

- 2025-01-15: Decidimos usar Zustand para estado global
- 2025-01-14: Implementamos Context API para autenticación
- 2025-01-13: Migramos a Next.js App Router

## Bloqueos Actuales

- Esperando aprobación de diseño para ISSUE-124
- Revisando implementación de ISSUE-123

## Próximos Pasos

1. Completar ISSUE-123
2. Revisar ISSUE-124 con equipo de diseño
3. Iniciar ISSUE-125
```

### 2. Sincronización de Contexto

Sincroniza contexto entre múltiples chats:

```
Este agente comparte contexto con otros chats del proyecto.

Lee .cursor/memory/shared-context.md para:
- Estado actual del proyecto
- Issues activos
- Decisiones recientes
- Bloqueos actuales

Actualiza este archivo cuando:
- Cambies el estado de un issue
- Hagas una nueva decisión
- Identifiques un bloqueo
- Completes un issue
```

## Técnicas Avanzadas

### 1. Memoria Basada en Commits

Crea memoria basada en commits recientes:

#### `.cursor/memory/commit-history.md`

```markdown
# Historial de Commits Relevantes

## Últimos Commits

- abc123: feat: Implementar login básico
  - Archivos: src/components/Login.tsx, src/hooks/useAuth.ts
  - Issues: ISSUE-123
  
- def456: fix: Corregir error de autenticación
  - Archivos: src/services/auth.ts
  - Issues: ISSUE-123
  
- ghi789: refactor: Simplificar componente Login
  - Archivos: src/components/Login.tsx
  - Issues: ISSUE-124
```

### 2. Memoria de Decisiones

Documenta decisiones importantes:

#### `.cursor/memory/decisions.md`

```markdown
# Decisiones de Arquitectura

## ADR-001: Estado Global

**Fecha**: 2025-01-15
**Estado**: Aceptado
**Contexto**: Necesitamos estado global para autenticación
**Decisión**: Usar Zustand en lugar de Redux
**Consecuencias**: Menor bundle size, API más simple

## ADR-002: Framework de Testing

**Fecha**: 2025-01-10
**Estado**: Aceptado
**Contexto**: Necesitamos framework de testing
**Decisión**: Usar Jest + React Testing Library
**Consecuencias**: Mejor integración con React, mejores prácticas
```

### 3. Memoria de Errores

Documenta errores comunes y sus soluciones:

#### `.cursor/memory/error-solutions.md`

```markdown
# Soluciones de Errores Comunes

## Error: TypeScript type errors en componentes

**Causa**: Props no tipadas correctamente
**Solución**: Añadir tipos a props con interface
**Ejemplo**: Ver componente Button.tsx

## Error: N+1 queries en Django

**Causa**: Queries no optimizadas
**Solución**: Usar select_related o prefetch_related
**Ejemplo**: Ver modelo User en models.py
```

## Workflows con Memoria

### Workflow: Iniciar Nueva Sesión

1. Lee `.cursor/memory/agent-context.md`
2. Lee `.cursor/memory/shared-context.md`
3. Contextualiza el agente con la información
4. Continúa donde se dejó la sesión anterior

```
Al iniciar una nueva sesión, lee:
- .cursor/memory/agent-context.md
- .cursor/memory/shared-context.md

Usa este contexto para:
- Recordar decisiones previas
- Continuar trabajo en progreso
- Mantener consistencia con sesiones anteriores
```

### Workflow: Actualizar Memoria

1. Identifica cambios importantes
2. Actualiza archivos de memoria relevantes
3. Documenta decisiones y contexto nuevo

```
Actualiza la memoria con:
- Nuevo issue creado: ISSUE-126
- Nueva decisión: Usar React Query para data fetching
- Nuevo bloqueo: Esperando aprobación de diseño
```

### Workflow: Sincronizar Contexto

1. Lee contexto compartido
2. Sincroniza con otros chats
3. Actualiza cuando sea necesario

```
Sincroniza contexto con otros chats:
- Lee .cursor/memory/shared-context.md
- Actualiza estado de issues activos
- Documenta decisiones nuevas
```

## Mejores Prácticas

### 1. Mantener Memoria Actualizada

- ✅ Actualiza memoria cuando cambia el contexto
- ✅ Documenta decisiones importantes
- ✅ Mantén fechas de última actualización
- ❌ No dejes memoria desactualizada

### 2. Organización de Memoria

- ✅ Organiza memoria por tipo (contexto, decisiones, errores)
- ✅ Usa archivos separados para diferentes tipos de memoria
- ✅ Mantén estructura clara y navegable
- ❌ No mezcles diferentes tipos de información

### 3. Contexto Relevante

- ✅ Incluye solo información relevante
- ✅ Actualiza información obsoleta
- ✅ Mantén memoria concisa
- ❌ No acumules información innecesaria

## Referencias

- Ver agentes expertos en `docs/agents/expert-agents.md`
- Ver contexto compartido en `docs/agentization/shared-context.md`
- Ver ejemplos en `examples/agent-configs/`

