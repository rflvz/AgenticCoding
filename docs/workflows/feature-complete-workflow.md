# Workflow de Feature Completa

Guía para desarrollar una feature completa desde diseño hasta deployment usando múltiples agentes coordinados.

## Concepto

El workflow de feature completa coordina múltiples agentes especializados para desarrollar una feature completa, desde diseño hasta deployment, asegurando calidad y completitud.

## Fases del Workflow

### Fase 1: Planificación y Diseño

#### Agente Orquestador

```
Feature: Sistema de Autenticación

1. Analizar requisitos
2. Crear issues en Linear:
   - ISSUE-123: Diseño de sistema de autenticación
   - ISSUE-124: Diseño UI de login
   - ISSUE-125: Diseño API de autenticación
3. Asignar a agentes:
   - Agente Arquitecto: ISSUE-123
   - Agente Frontend: ISSUE-124
   - Agente Backend: ISSUE-125
4. Actualizar contexto compartido
```

#### Agentes Especializados

**Agente Arquitecto:**
```
Trabaja en ISSUE-123: Diseño de sistema de autenticación

1. Diseña arquitectura del sistema
2. Define componentes y flujos
3. Establece dependencias entre componentes
4. Documenta diseño
5. Actualiza contexto: "ISSUE-123 completado"
```

**Agente Frontend:**
```
Trabaja en ISSUE-124: Diseño UI de login

1. Lee diseño de arquitectura (ISSUE-123)
2. Diseña UI de login
3. Define componentes necesarios
4. Documenta diseño UI
5. Actualiza contexto: "ISSUE-124 completado"
```

**Agente Backend:**
```
Trabaja en ISSUE-125: Diseño API de autenticación

1. Lee diseño de arquitectura (ISSUE-123)
2. Diseña API de autenticación
3. Define endpoints y contratos
4. Documenta diseño API
5. Actualiza contexto: "ISSUE-125 completado"
```

### Fase 2: Desarrollo

#### Agente Orquestador

```
1. Verifica que diseño esté completo
2. Crea issues de implementación:
   - ISSUE-126: Implementar UI de login
   - ISSUE-127: Implementar API de autenticación
   - ISSUE-128: Implementar integración frontend-backend
3. Asigna a agentes:
   - Agente Frontend: ISSUE-126
   - Agente Backend: ISSUE-127
   - Agente Frontend + Backend: ISSUE-128
4. Actualiza contexto compartido
```

#### Agentes Especializados

**Agente Frontend:**
```
Trabaja en ISSUE-126: Implementar UI de login

1. Lee diseño UI (ISSUE-124)
2. Implementa componente Login.tsx
3. Implementa hooks necesarios (useAuth)
4. Integra con API cuando esté lista
5. Actualiza contexto: "ISSUE-126 completado"
```

**Agente Backend:**
```
Trabaja en ISSUE-127: Implementar API de autenticación

1. Lee diseño API (ISSUE-125)
2. Implementa endpoints de autenticación
3. Implementa lógica de autenticación
4. Implementa validación y seguridad
5. Actualiza contexto: "ISSUE-127 completado"
```

**Agente Frontend + Backend:**
```
Trabaja en ISSUE-128: Integración frontend-backend

1. Espera ISSUE-126 y ISSUE-127
2. Integra frontend con backend
3. Verifica que integración funcione
4. Ajusta según sea necesario
5. Actualiza contexto: "ISSUE-128 completado"
```

### Fase 3: Testing

#### Agente Orquestador

```
1. Verifica que implementación esté completa
2. Crea issues de testing:
   - ISSUE-129: Tests unitarios de frontend
   - ISSUE-130: Tests unitarios de backend
   - ISSUE-131: Tests de integración
   - ISSUE-132: Tests E2E
3. Asigna a Agente Testing
4. Actualiza contexto compartido
```

#### Agente Testing

```
Trabaja en ISSUE-129-132: Tests completos

1. Espera ISSUE-126, ISSUE-127, ISSUE-128
2. Genera tests unitarios para frontend (ISSUE-129)
3. Genera tests unitarios para backend (ISSUE-130)
4. Genera tests de integración (ISSUE-131)
5. Genera tests E2E (ISSUE-132)
6. Verifica que todos los tests pasen
7. Actualiza contexto: "ISSUE-129-132 completados"
```

### Fase 4: Code Review

#### Agente Code Review

```
Revisa código completo de feature:

1. Revisa ISSUE-126: UI de login
   - Busca bugs
   - Verifica mejores prácticas
   - Verifica accesibilidad
   
2. Revisa ISSUE-127: API de autenticación
   - Busca bugs
   - Verifica seguridad
   - Verifica performance
   
3. Revisa ISSUE-128: Integración
   - Verifica que integración funcione
   - Busca problemas de integración
   
4. Crea issues para problemas encontrados
5. Aprueba o solicita cambios
6. Actualiza contexto compartido
```

### Fase 5: Documentación

#### Agente Documentation

```
Trabaja en ISSUE-133: Documentación de feature

1. Espera ISSUE-126, ISSUE-127, ISSUE-128 completados
2. Documenta feature completa:
   - Descripción de feature
   - Guía de uso
   - Ejemplos de código
   - Documentación de API
3. Actualiza README si es necesario
4. Actualiza contexto: "ISSUE-133 completado"
```

### Fase 6: Deployment

#### Agente DevOps

```
Trabaja en ISSUE-134: Deployment de feature

1. Verifica que CI/CD pase
2. Verifica que todos los tests pasen
3. Prepara deployment:
   - Verifica configuración
   - Verifica variables de entorno
   - Verifica dependencias
4. Ejecuta deployment
5. Verifica que deployment sea exitoso
6. Monitorea después de deployment
7. Actualiza contexto: "ISSUE-134 completado"
```

## Contexto Compartido

Durante todo el workflow, todos los agentes leen y actualizan `.cursor/memory/shared-context.md`:

```markdown
# Contexto Compar tido - Feature: Sistema de Autenticación

## Fase Actual
- Fase: Desarrollo
- Issues activos:
  - ISSUE-126: UI de login (In Progress - Frontend)
  - ISSUE-127: API de autenticación (In Progress - Backend)
  - ISSUE-128: Integración (Todo - Frontend + Backend)

## Dependencias
- ISSUE-128 depende de ISSUE-126 y ISSUE-127
- ISSUE-129-132 (Tests) dependen de ISSUE-126, ISSUE-127, ISSUE-128
- ISSUE-133 (Documentación) depende de ISSUE-126, ISSUE-127, ISSUE-128
- ISSUE-134 (Deployment) depende de todos los issues anteriores

## Bloqueos
- Ninguno actualmente

## Próximos Pasos
1. Completar ISSUE-126 y ISSUE-127
2. Iniciar ISSUE-128 cuando ISSUE-126 y ISSUE-127 estén completos
3. Iniciar ISSUE-129-132 cuando ISSUE-128 esté completo
```

## Ejemplo Completo

### Feature: Sistema de Notificaciones

```
Fase 1: Planificación (Agente Orquestador)
├─ ISSUE-123: Diseño de sistema (Agente Arquitecto)
├─ ISSUE-124: Diseño UI (Agente Frontend)
└─ ISSUE-125: Diseño API (Agente Backend)

Fase 2: Desarrollo
├─ ISSUE-126: UI de notificaciones (Agente Frontend)
├─ ISSUE-127: API de notificaciones (Agente Backend)
└─ ISSUE-128: Integración (Agente Frontend + Backend)

Fase 3: Testing
├─ ISSUE-129: Tests unitarios frontend (Agente Testing)
├─ ISSUE-130: Tests unitarios backend (Agente Testing)
├─ ISSUE-131: Tests de integración (Agente Testing)
└─ ISSUE-132: Tests E2E (Agente Testing)

Fase 4: Code Review
└─ Revisión completa (Agente Code Review)

Fase 5: Documentación
└─ ISSUE-133: Documentación (Agente Documentation)

Fase 6: Deployment
└─ ISSUE-134: Deployment (Agente DevOps)
```

## Mejores Prácticas

### 1. Planificación

- ✅ Planifica antes de desarrollar
- ✅ Define dependencias claramente
- ✅ Establece prioridades
- ❌ No empieces desarrollo sin diseño

### 2. Desarrollo

- ✅ Desarrolla según diseño
- ✅ Mantén contexto compartido actualizado
- ✅ Comunica bloqueos y decisiones
- ❌ No cambies diseño sin coordinar

### 3. Testing

- ✅ Prueba cada componente
- ✅ Prueba integración completa
- ✅ Verifica que todos los tests pasen
- ❌ No deploys sin tests

### 4. Deployment

- ✅ Verifica que todo esté completo
- ✅ Verifica que CI/CD pase
- ✅ Monitorea después de deployment
- ❌ No deploys sin verificación

## Referencias

- Ver orquestación multi-agente en `docs/workflows/multi-agent-orchestration.md`
- Ver contexto compartido en `docs/agentization/shared-context.md`
- Ver gestión de memoria en `docs/agentization/memory-management.md`

