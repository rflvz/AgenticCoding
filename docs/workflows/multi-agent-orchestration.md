# Orquestación de Múltiples Agentes

Guía para coordinar múltiples agentes especializados trabajando juntos en tareas complejas.

## Concepto

La orquestación de múltiples agentes permite coordinar varios agentes especializados para trabajar juntos en tareas complejas, dividiendo el trabajo según expertise y coordinando resultados.

## Arquitectura de Agentes

### 1. Agente Orquestador

Agente principal que coordina otros agentes:

```
Eres un agente orquestador. Tu función es coordinar múltiples agentes especializados para completar tareas complejas.

## Tu Rol

- Dividir tareas complejas en subtareas
- Asignar subtareas a agentes especializados
- Coordinar resultados de múltiples agentes
- Sincronizar contexto entre agentes
- Gestionar dependencias entre tareas

## Agentes Disponibles

- Agente Frontend: Componentes React, UI/UX
- Agente Backend: APIs, servicios, base de datos
- Agente Testing: Tests, cobertura, calidad
- Agente Documentation: Documentación, READMEs
- Agente DevOps: CI/CD, deployment, infraestructura
- Agente PM: Project management, prioridades

## Proceso de Orquestación

1. Analizar tarea compleja
2. Dividir en subtareas
3. Asignar subtareas a agentes apropiados
4. Coordinar ejecución
5. Consolidar resultados
```

### 2. Agentes Especializados

Agentes que realizan tareas específicas:

#### Agente Frontend

```
Eres un agente especializado en frontend.

Trabajas en:
- Componentes React
- UI/UX
- Frontend issues

Coordinas con:
- Agente Backend (para APIs)
- Agente Testing (para tests)
- Agente PM (para prioridades)
```

#### Agente Backend

```
Eres un agente especializado en backend.

Trabajas en:
- APIs y servicios
- Base de datos
- Backend issues

Coordinas con:
- Agente Frontend (para endpoints)
- Agente Testing (para tests)
- Agente PM (para prioridades)
```

## Workflows Multi-Agente

### Workflow: Desarrollo Completo de Feature

#### 1. Fase de Planificación (Agente Orquestador)

```
Feature: Sistema de Login

1. Analizar requisitos
2. Dividir en subtareas:
   - Diseño UI (Agente Frontend)
   - API Backend (Agente Backend)
   - Tests (Agente Testing)
   - Documentación (Agente Documentation)
3. Crear issues en Linear:
   - ISSUE-123: Diseño UI de login
   - ISSUE-124: API de autenticación
   - ISSUE-125: Tests de login
   - ISSUE-126: Documentación de login
4. Establecer dependencias entre issues
```

#### 2. Fase de Desarrollo (Agentes Especializados)

**Agente Frontend (Chat 1):**
```
Trabaja en ISSUE-123: Diseño UI de login

1. Lee contexto compartido
2. Diseña componente Login.tsx
3. Implementa UI según diseño
4. Actualiza contexto: "ISSUE-123 en progreso"
5. Notifica cuando esté listo para backend
```

**Agente Backend (Chat 2):**
```
Trabaja en ISSUE-124: API de autenticación

1. Lee contexto compartido
2. Diseña API de autenticación
3. Implementa endpoints
4. Actualiza contexto: "ISSUE-124 en progreso"
5. Notifica cuando esté listo para frontend
```

**Agente Testing (Chat 3):**
```
Trabaja en ISSUE-125: Tests de login

1. Lee contexto compartido
2. Espera a que ISSUE-123 y ISSUE-124 estén completos
3. Genera tests para frontend y backend
4. Verifica que tests pasen
5. Actualiza contexto: "ISSUE-125 completado"
```

**Agente Documentation (Chat 4):**
```
Trabaja en ISSUE-126: Documentación de login

1. Lee contexto compartido
2. Espera a que ISSUE-123 y ISSUE-124 estén completos
3. Documenta feature completa
4. Actualiza README si es necesario
5. Actualiza contexto: "ISSUE-126 completado"
```

#### 3. Fase de Consolidación (Agente Orquestador)

```
1. Lee contexto compartido
2. Verifica que todos los issues estén completos
3. Integra resultados de todos los agentes
4. Verifica que todo funcione junto
5. Cierra issues relacionados
```

### Workflow: Revisión Completa de Código

#### 1. Análisis Inicial (Agente Orquestador)

```
Código a revisar: Sistema de autenticación

1. Analizar código
2. Dividir revisión en aspectos:
   - Bugs y errores (Agente Code Review)
   - Performance (Agente Performance)
   - Seguridad (Agente Security)
   - Tests (Agente Testing)
   - Documentación (Agente Documentation)
3. Asignar revisión a agentes especializados
```

#### 2. Revisión Paralela (Agentes Especializados)

**Agente Code Review (Chat 1):**
```
Revisa código para bugs y errores:

1. Analiza código buscando bugs
2. Identifica errores lógicos
3. Crea issues en Linear para bugs encontrados
4. Actualiza contexto compartido
```

**Agente Performance (Chat 2):**
```
Revisa código para performance:

1. Analiza código buscando problemas de performance
2. Identifica queries lentas, operaciones bloqueantes
3. Crea issues en Linear para optimizaciones
4. Actualiza contexto compartido
```

**Agente Security (Chat 3):**
```
Revisa código para vulnerabilidades:

1. Analiza código buscando vulnerabilidades
2. Identifica problemas de seguridad
3. Crea issues urgentes en Linear para vulnerabilidades
4. Actualiza contexto compartido
```

**Agente Testing (Chat 4):**
```
Revisa tests y cobertura:

1. Analiza tests existentes
2. Identifica tests faltantes
3. Verifica cobertura de código
4. Crea issues en Linear para tests faltantes
5. Actualiza contexto compartido
```

**Agente Documentation (Chat 5):**
```
Revisa documentación:

1. Analiza documentación existente
2. Identifica documentación faltante o desactualizada
3. Crea issues en Linear para documentación
4. Actualiza contexto compartido
```

#### 3. Consolidación (Agente Orquestador)

```
1. Lee contexto compartido
2. Consolida issues de todos los agentes
3. Prioriza issues según severidad:
   - Urgent: Vulnerabilidades de seguridad
   - High: Bugs críticos
   - Normal: Performance y mejoras
4. Genera reporte de revisión
5. Actualiza contexto compartido con reporte
```

### Workflow: Pipeline de Desarrollo Completo

#### 1. Desarrollo (Agentes Especializados)

```
Feature: Sistema de Notificaciones

Agente Frontend:
- Diseña UI de notificaciones
- Implementa componentes React
- Crea ISSUE-127: UI de notificaciones

Agente Backend:
- Diseña API de notificaciones
- Implementa endpoints
- Crea ISSUE-128: API de notificaciones
```

#### 2. Testing (Agente Testing)

```
Agente Testing:
- Espera ISSUE-127 y ISSUE-128
- Genera tests para frontend y backend
- Verifica que tests pasen
- Crea ISSUE-129: Tests de notificaciones
```

#### 3. Code Review (Agente Code Review)

```
Agente Code Review:
- Revisa código de ISSUE-127 y ISSUE-128
- Identifica bugs y mejoras
- Crea issues para problemas encontrados
- Aproba o solicita cambios
```

#### 4. Documentation (Agente Documentation)

```
Agente Documentation:
- Documenta feature completa
- Actualiza README
- Documenta API endpoints
- Crea ISSUE-130: Documentación de notificaciones
```

#### 5. Deployment (Agente DevOps)

```
Agente DevOps:
- Verifica que CI/CD pase
- Prepara deployment
- Ejecuta deployment
- Verifica que deployment sea exitoso
```

## Coordinación de Contexto

### 1. Contexto Compartido

Todos los agentes leen y actualizan `.cursor/memory/shared-context.md`:

```markdown
# Contexto Compartido

## Estado del Proyecto
- Feature actual: Sistema de notificaciones
- Issues activos:
  - ISSUE-127: UI de notificaciones (In Progress - Frontend)
  - ISSUE-128: API de notificaciones (In Progress - Backend)
  - ISSUE-129: Tests de notificaciones (Todo - Testing)
  - ISSUE-130: Documentación (Todo - Documentation)

## Dependencias
- ISSUE-129 depende de ISSUE-127 y ISSUE-128
- ISSUE-130 depende de ISSUE-127 y ISSUE-128

## Bloqueos
- Ninguno actualmente

## Próximos Pasos
1. Completar ISSUE-127 y ISSUE-128
2. Iniciar ISSUE-129 cuando ISSUE-127 y ISSUE-128 estén completos
3. Iniciar ISSUE-130 cuando ISSUE-127 y ISSUE-128 estén completos
```

### 2. Sincronización

Agentes actualizan contexto cuando:
- Inician trabajo en un issue
- Completan un issue
- Identifican un bloqueo
- Hacen una decisión importante

## Ejemplos de Uso

### Ejemplo 1: Feature Completa

```
Orquestador: Desarrolla feature "Sistema de Login"

1. Divide en subtareas
2. Asigna a agentes:
   - Frontend: Diseño UI
   - Backend: API de autenticación
   - Testing: Tests
   - Documentation: Documentación
3. Coordina ejecución
4. Consolida resultados
```

### Ejemplo 2: Revisión Completa

```
Orquestador: Revisa código del sistema

1. Divide revisión en aspectos
2. Asigna a agentes:
   - Code Review: Bugs
   - Performance: Optimizaciones
   - Security: Vulnerabilidades
   - Testing: Tests
3. Coordina revisión paralela
4. Consolida issues encontrados
```

## Mejores Prácticas

### 1. División de Trabajo

- ✅ Divide tareas claramente
- ✅ Asigna según expertise
- ✅ Establece dependencias
- ❌ No asignes tareas sin contexto claro

### 2. Coordinación

- ✅ Usa contexto compartido
- ✅ Actualiza contexto regularmente
- ✅ Comunica bloqueos y decisiones
- ❌ No trabajes sin leer contexto compartido

### 3. Consolidación

- ✅ Consolida resultados de todos los agentes
- ✅ Verifica que todo funcione junto
- ✅ Prioriza issues según severidad
- ❌ No ignores resultados de agentes

## Referencias

- Ver contexto compartido en `docs/agentization/shared-context.md`
- Ver gestión de memoria en `docs/agentization/memory-management.md`
- Ver agentes expertos en `docs/agents/expert-agents.md`

