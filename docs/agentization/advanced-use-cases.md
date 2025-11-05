# Casos de Uso Avanzados y Mejores Prácticas

Guía completa sobre casos de uso avanzados de agentización con Linear en Cursor y mejores prácticas para su implementación efectiva.

## Concepto

Una vez comprendidos los fundamentos de la agentización con Linear, es importante documentar patrones avanzados y mejores prácticas que permitan maximizar el valor de esta integración.

## Casos de Uso Avanzados

### 1. Gestión de Proyectos Multi-Equipo

**Escenario:**

Proyecto que involucra múltiples equipos (frontend, backend, DevOps) trabajando en diferentes aspectos del mismo proyecto.

**Solución con agentización:**

- Agente orquestador lee proyecto en Linear
- Identifica tareas por equipo usando labels
- Asigna trabajo a agentes especializados por equipo
- Coordina dependencias entre equipos
- Sincroniza progreso en Linear

**Implementación:**

```markdown
# Flujo de Gestión Multi-Equipo

1. Agente Orquestador lee proyecto en Linear:
   - Usa list_issues con filtro por proyecto
   - Identifica tareas por equipo usando labels (frontend, backend, devops)

2. Asigna trabajo a agentes especializados:
   - Agente Frontend: Trabaja en issues con label "frontend"
   - Agente Backend: Trabaja en issues con label "backend"
   - Agente DevOps: Trabaja en issues con label "devops"

3. Coordina dependencias:
   - Agente Orquestador lee dependencias entre issues
   - Coordina ejecución en orden correcto
   - Sincroniza progreso en Linear

4. Sincroniza progreso:
   - Cada agente actualiza Linear con su progreso
   - Agente Orquestador monitorea estado general
   - Proyecto completo cuando todas las tareas están listas
```

**Ejemplo:**

```
Proyecto: Sistema de E-commerce

Issues con labels:
- DAW-20: "Implementar carrito de compras" [frontend]
- DAW-21: "API de carrito de compras" [backend]
- DAW-22: "Deploy de carrito" [devops]

Agente Frontend:
- Lee DAW-20
- Implementa UI de carrito
- Espera a que DAW-21 esté en "In Review"
- Actualiza Linear con progreso

Agente Backend:
- Lee DAW-21
- Implementa API de carrito
- Actualiza Linear con endpoints
- Cambia estado a "In Review"

Agente DevOps:
- Lee DAW-22
- Espera a que DAW-20 y DAW-21 estén en "In Review"
- Implementa deployment
- Actualiza Linear con estado de deployment
```

**Beneficios:**

- ✅ Coordinación efectiva entre múltiples equipos
- ✅ Trabajo paralelo eficiente
- ✅ Gestión automática de dependencias
- ✅ Visibilidad completa del proyecto

### 2. Refactoring Complejo con Trazabilidad

**Escenario:**

Refactorizar código legacy manteniendo trazabilidad completa de cambios y decisiones técnicas.

**Solución con agentización:**

- Crear issue padre en Linear para el refactoring
- Dividir en sub-issues por módulo/componente
- Cada sub-issue documenta decisiones técnicas
- El agente implementa cambios manteniendo referencias a issues originales
- Historial completo de cambios en Linear

**Implementación:**

```markdown
# Flujo de Refactoring con Trazabilidad

1. Crear issue padre:
   - Issue principal: "Refactorizar módulo de autenticación"
   - Documenta objetivo y alcance del refactoring

2. Dividir en sub-issues:
   - DAW-30-1: "Refactorizar servicio de autenticación"
   - DAW-30-2: "Refactorizar middleware de autenticación"
   - DAW-30-3: "Refactorizar componentes de UI de autenticación"

3. Documentar decisiones técnicas:
   - Cada sub-issue documenta decisiones técnicas
   - Incluye razonamiento y alternativas consideradas
   - Referencias a código original

4. Implementar cambios:
   - Agente implementa cambios manteniendo referencias a issues
   - Documenta cambios en comentarios de issues
   - Mantiene trazabilidad completa

5. Historial completo:
   - Todo el historial de cambios documentado en Linear
   - Decisiones técnicas disponibles para futuros agentes
   - Trazabilidad completa del refactoring
```

**Ejemplo:**

```
Issue Padre: DAW-30 "Refactorizar módulo de autenticación"

Sub-issues:
- DAW-30-1: "Refactorizar servicio de autenticación"
  - Decisión: Migrar de callback a async/await
  - Razón: Mejor legibilidad y manejo de errores
  - Alternativas consideradas: Promises, Observables
  - Referencias: src/services/auth.js (líneas 45-120)

- DAW-30-2: "Refactorizar middleware de autenticación"
  - Decisión: Separar en middlewares específicos
  - Razón: Mejor modularidad y testabilidad
  - Referencias: src/middleware/auth.js

Agente:
1. Lee DAW-30-1
2. Implementa refactoring
3. Documenta cambios en comentario del issue
4. Actualiza estado a "In Review"
```

**Beneficios:**

- ✅ Trazabilidad completa de cambios
- ✅ Decisiones técnicas documentadas
- ✅ Historial completo disponible
- ✅ Mejor comprensión del refactoring

### 3. Desarrollo de Features con CI/CD Integrado

**Escenario:**

Feature que requiere cambios en múltiples capas (frontend, backend, tests, deployment) con integración continua.

**Solución con agentización:**

- Issue en Linear contiene especificación completa
- Agente divide en sub-tareas por capa
- Implementa cambios en orden correcto
- Actualiza Linear con resultados de tests
- Crea PRs y actualiza Linear con estado de CI/CD

**Implementación:**

```markdown
# Flujo de Feature con CI/CD

1. Issue principal en Linear:
   - Especificación completa de la feature
   - Criterios de aceptación
   - Dependencias identificadas

2. Agente divide en sub-tareas:
   - DAW-40-1: "Implementar backend"
   - DAW-40-2: "Implementar frontend"
   - DAW-40-3: "Escribir tests"
   - DAW-40-4: "Configurar CI/CD"

3. Implementa cambios:
   - Backend implementado primero
   - Frontend implementado después
   - Tests escritos para ambas capas
   - CI/CD configurado

4. Actualiza Linear con resultados:
   - Resultados de tests documentados
   - Estado de CI/CD actualizado
   - PRs creados y enlazados

5. Monitoreo:
   - Agente monitorea estado de CI/CD
   - Actualiza Linear con resultados
   - Feature completa cuando todo pasa
```

**Ejemplo:**

```
Feature: Sistema de Notificaciones Push

Issue: DAW-40 "Implementar sistema de notificaciones push"

Sub-tareas:
- DAW-40-1: Backend - API de notificaciones
- DAW-40-2: Frontend - UI de notificaciones
- DAW-40-3: Tests - Tests de integración
- DAW-40-4: CI/CD - Configuración de deployment

Agente:
1. Implementa backend (DAW-40-1)
2. Ejecuta tests, actualiza Linear con resultados
3. Implementa frontend (DAW-40-2)
4. Ejecuta tests, actualiza Linear con resultados
5. Crea PR para backend
6. Crea PR para frontend
7. Monitorea CI/CD, actualiza Linear con estado
8. Feature completa cuando CI/CD pasa
```

**Beneficios:**

- ✅ Integración completa con CI/CD
- ✅ Resultados de tests documentados
- ✅ Estado de deployment visible
- ✅ Feature completa cuando todo está listo

### 4. Gestión de Bugs Críticos en Producción

**Escenario:**

Bug crítico detectado en producción que requiere respuesta rápida y solución inmediata.

**Solución con agentización:**

- Agente crea issue urgente en Linear automáticamente
- Asigna prioridad y notifica al equipo
- Implementa hotfix
- Actualiza Linear con solución y causa raíz
- Crea issue de seguimiento para prevención

**Implementación:**

```markdown
# Flujo de Bug Crítico

1. Detección:
   - Bug detectado en producción
   - Usuario reporta o sistema alerta

2. Agente crea issue urgente:
   - Issue creado automáticamente con prioridad "Urgent"
   - Labels: "bug", "critical", "production"
   - Notificación al equipo

3. Implementa hotfix:
   - Agente analiza el bug
   - Implementa solución inmediata
   - Documenta solución en Linear

4. Actualiza Linear:
   - Solución documentada
   - Causa raíz identificada
   - Estado actualizado

5. Seguimiento:
   - Issue de seguimiento creado
   - Prevención de bugs similares
   - Mejoras sugeridas
```

**Ejemplo:**

```
Bug Crítico: Error 500 en endpoint de autenticación

Agente:
1. Crea issue urgente: DAW-50 "Bug crítico: Error 500 en autenticación"
   - Prioridad: Urgent
   - Labels: bug, critical, production
   - Notifica al equipo

2. Analiza el bug:
   - Lee logs de error
   - Identifica causa: Null pointer exception
   - Implementa hotfix inmediato

3. Actualiza Linear:
   - Solución documentada
   - Causa raíz: Falta de validación de token
   - Hotfix implementado

4. Crea issue de seguimiento:
   - DAW-51 "Mejorar validación de tokens"
   - Prevención de bugs similares
   - Mejoras sugeridas
```

**Beneficios:**

- ✅ Respuesta rápida a bugs críticos
- ✅ Solución documentada inmediatamente
- ✅ Causa raíz identificada
- ✅ Prevención de bugs similares

### 5. Documentación Técnica Automática

**Escenario:**

Mantener documentación técnica actualizada con el código de manera automática.

**Solución con agentización:**

- Issues en Linear para documentación de features
- Agente lee código y genera documentación
- Actualiza Linear con enlaces a documentación
- Verifica que documentación esté sincronizada

**Implementación:**

```markdown
# Flujo de Documentación Automática

1. Issue de documentación:
   - Issue creado cuando se completa feature
   - Especifica qué documentar

2. Agente lee código:
   - Analiza código implementado
   - Identifica funciones, clases, módulos
   - Genera documentación técnica

3. Genera documentación:
   - Documenta APIs
   - Documenta funciones
   - Documenta decisiones técnicas
   - Actualiza documentación existente

4. Actualiza Linear:
   - Enlaces a documentación añadidos
   - Verificación de sincronización
   - Estado actualizado
```

**Ejemplo:**

```
Feature: Sistema de Autenticación OAuth2

Issue: DAW-60 "Documentar sistema de autenticación OAuth2"

Agente:
1. Lee código implementado:
   - src/services/auth.js
   - src/middleware/auth.js
   - src/routes/auth.js

2. Genera documentación:
   - Documenta API de autenticación
   - Documenta funciones principales
   - Documenta flujo de autenticación
   - Actualiza README

3. Actualiza Linear:
   - Enlaces a documentación
   - Verificación de sincronización
   - Estado actualizado a "Done"
```

**Beneficios:**

- ✅ Documentación siempre sincronizada
- ✅ Generación automática de documentación
- ✅ Reducción de documentación desactualizada
- ✅ Mejor calidad de documentación

## Mejores Prácticas

### 1. Estructura de Issues

**Mejor Práctica:**

Usar estructura jerárquica (Epic → Feature → Task) para organizar issues.

**Ejemplo:**

```
Epic: Sistema de Autenticación
  ├── Feature: Autenticación OAuth2
  │   ├── Task: Implementar backend
  │   ├── Task: Implementar frontend
  │   ├── Task: Escribir tests
  │   └── Task: Documentar
  └── Feature: Autenticación JWT
      ├── Task: Implementar backend
      ├── Task: Implementar frontend
      └── Task: Escribir tests
```

**Beneficio:**

Los agentes pueden entender mejor la estructura y priorizar correctamente.

**Implementación:**

```markdown
# Crear estructura jerárquica

1. Crear Epic:
   - Issue principal con tipo "Epic"
   - Documenta objetivo general

2. Crear Features:
   - Sub-issues con parentId del Epic
   - Documenta features específicas

3. Crear Tasks:
   - Sub-issues con parentId del Feature
   - Documenta tareas específicas

4. Agentes leen estructura:
   - Entienden jerarquía
   - Priorizan correctamente
   - Coordinan trabajo
```

### 2. Labels Consistentes

**Mejor Práctica:**

Usar labels consistentes y bien definidos para categorizar issues.

**Categorías de Labels:**

- **Tipo**: `feature`, `bug`, `refactor`, `docs`, `chore`
- **Área**: `frontend`, `backend`, `api`, `database`, `infrastructure`
- **Prioridad**: `critical`, `high-priority`, `low-priority`
- **Estado**: `blocked`, `needs-review`, `in-progress`

**Beneficio:**

Los agentes pueden filtrar y organizar issues automáticamente.

**Implementación:**

```markdown
# Usar labels consistentes

1. Definir conjunto de labels:
   - Tipo: feature, bug, refactor, docs, chore
   - Área: frontend, backend, api, database
   - Prioridad: critical, high-priority, low-priority

2. Aplicar labels a issues:
   - Cada issue tiene labels apropiados
   - Labels consistentes en todo el proyecto

3. Agentes usan labels:
   - Filtran issues por labels
   - Organizan trabajo basado en labels
   - Priorizan según labels
```

### 3. Descripciones Completas

**Mejor Práctica:**

Incluir en descripciones toda la información necesaria para que los agentes tomen decisiones inteligentes.

**Contenido de Descripción:**

- Objetivo claro
- Contexto técnico
- Criterios de aceptación
- Dependencias
- Notas técnicas

**Ejemplo de Descripción Completa:**

```markdown
# Feature: Sistema de Autenticación OAuth2

## Objetivo
Implementar autenticación OAuth2 para permitir a usuarios iniciar sesión usando proveedores externos (Google, GitHub).

## Contexto Técnico
- Stack: Node.js, Express, Passport.js
- Base de datos: PostgreSQL
- Frontend: React

## Criterios de Aceptación
- [ ] Usuarios pueden iniciar sesión con Google
- [ ] Usuarios pueden iniciar sesión con GitHub
- [ ] Tokens JWT generados correctamente
- [ ] Tests de integración pasan

## Dependencias
- Requiere: DAW-20 (Configuración de base de datos)
- Bloquea: DAW-30 (Sistema de permisos)

## Notas Técnicas
- Usar Passport.js para OAuth2
- Tokens JWT con expiración de 7 días
- Refresh tokens con expiración de 30 días
```

**Beneficio:**

Los agentes tienen contexto suficiente para tomar decisiones inteligentes.

### 4. Actualización Proactiva

**Mejor Práctica:**

Actualizar Linear frecuentemente durante el desarrollo para mantener el estado sincronizado.

**Frecuencia de Actualización:**

- Al iniciar trabajo: Cambiar estado a "In Progress"
- Durante el trabajo: Actualizar con progreso
- Al completar: Cambiar estado a "In Review"
- Al finalizar: Cambiar estado a "Done"

**Beneficio:**

El estado en Linear siempre refleja la realidad, permitiendo mejores decisiones.

### 5. Uso de Proyectos

**Mejor Práctica:**

Organizar issues relacionados en proyectos para proporcionar contexto completo.

**Beneficio:**

Los agentes pueden entender mejor el contexto del proyecto completo.

## Anti-Patrones a Evitar

### ❌ Evitar: Issues Vagos

**Mal:**

```
Issue: "Mejorar el código"
```

**Bueno:**

```
Issue: "feature: Refactorizar módulo de autenticación para mejorar rendimiento"
```

**Problema:**

Los agentes no pueden entender qué hacer con issues vagos.

**Solución:**

Usar títulos descriptivos y específicos.

### ❌ Evitar: Sin Estructura

**Mal:**

```
Issues planos sin jerarquía:
- DAW-10: "Implementar autenticación"
- DAW-11: "Implementar backend"
- DAW-12: "Implementar frontend"
```

**Bueno:**

```
Epic: DAW-10 "Sistema de Autenticación"
  ├── Feature: DAW-11 "Backend de autenticación"
  └── Feature: DAW-12 "Frontend de autenticación"
```

**Problema:**

Sin estructura jerárquica, los agentes no pueden entender dependencias.

**Solución:**

Usar estructura jerárquica con parentId.

### ❌ Evitar: Documentación Incompleta

**Mal:**

```
Issue: "Implementar login"
Descripción: (vacía)
```

**Bueno:**

```
Issue: "feature: Implementar sistema de login"
Descripción: 
## Objetivo
Implementar sistema de login con autenticación JWT.

## Contexto Técnico
- Stack: Node.js, Express
- Base de datos: PostgreSQL

## Criterios de Aceptación
- [ ] Usuarios pueden iniciar sesión
- [ ] Tokens JWT generados correctamente
- [ ] Tests pasan
```

**Problema:**

Sin documentación, los agentes no tienen contexto suficiente.

**Solución:**

Incluir descripción completa con toda la información necesaria.

### ❌ Evitar: Labels Inconsistentes

**Mal:**

```
Labels diferentes para conceptos similares:
- DAW-10: [feature]
- DAW-11: [new-feature]
- DAW-12: [funcionalidad]
```

**Bueno:**

```
Labels consistentes:
- DAW-10: [feature]
- DAW-11: [feature]
- DAW-12: [feature]
```

**Problema:**

Labels inconsistentes dificultan la organización automática.

**Solución:**

Usar conjunto consistente de labels bien definidos.

## Plantillas Reutilizables

### Plantilla para Feature

```markdown
# Feature: [Título de la Feature]

## Objetivo
[Descripción clara del objetivo]

## Contexto Técnico
- Stack: [Stack utilizado]
- Dependencias: [Dependencias técnicas]

## Criterios de Aceptación
- [ ] Criterio 1
- [ ] Criterio 2
- [ ] Criterio 3

## Dependencias
- Requiere: [Issues requeridos]
- Bloquea: [Issues bloqueados]

## Notas Técnicas
[Notas técnicas relevantes]
```

### Plantilla para Bug

```markdown
# Bug: [Título del Bug]

## Descripción
[Descripción del bug]

## Pasos para Reproducir
1. Paso 1
2. Paso 2
3. Paso 3

## Comportamiento Esperado
[Comportamiento esperado]

## Comportamiento Actual
[Comportamiento actual]

## Contexto Técnico
- Stack: [Stack utilizado]
- Versión: [Versión]

## Solución Propuesta
[Solución propuesta]
```

## Referencias

- Ver automatización de tareas en `docs/agentization/task-automation.md`
- Ver orquestación de flujos en `docs/workflows/workflow-orchestration.md`
- Ver contexto compartido en `docs/agentization/persistent-memory.md`
- Ver productividad en `docs/agentization/productivity-improvement.md`

## Próximos Pasos

1. **Implementar casos de uso avanzados**: Comenzar con casos de uso más simples
2. **Seguir mejores prácticas**: Aplicar mejores prácticas en todos los issues
3. **Evitar anti-patrones**: Identificar y evitar anti-patrones comunes
4. **Usar plantillas**: Usar plantillas para consistencia

---

_Hecho por Cursor_

