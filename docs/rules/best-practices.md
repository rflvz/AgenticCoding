# Reglas y Mejores Prácticas

Reglas, patrones recomendados y anti-patterns para usar Cursor con Linear de manera efectiva.

## Reglas de Uso

### 1. Títulos de Issues

**✅ Correcto:**
```
[Type]: Descripción clara y específica
```

Ejemplos:
- `bug: El login falla con tokens OAuth2`
- `feature: Añadir toggle de modo oscuro`
- `refactor: Simplificar flujo de autenticación`

**❌ Incorrecto:**
```
Fix bug
Issue
Problem
```

### 2. Descripciones de Issues

**✅ Correcto:**
- Contexto técnico detallado
- Pasos para reproducir (si aplica)
- Comportamiento esperado vs actual
- Código relevante o referencias

**❌ Incorrecto:**
- Descripciones vagas
- Sin contexto técnico
- Sin referencias a código

### 3. Asignación de Issues

**✅ Correcto:**
- Asigna al equipo correcto
- Asigna a persona específica cuando sea necesario
- Usa `"me"` para auto-asignación

**❌ Incorrecto:**
- Asignar al equipo incorrecto
- Dejar issues sin asignar cuando requieren acción

### 4. Uso de Labels

**✅ Correcto:**
- Usa labels consistentes
- Combina labels relevantes
- Crea un conjunto estándar de labels

**❌ Incorrecto:**
- Labels inconsistentes
- Demasiados labels (más de 5)
- Labels sin significado claro

### 5. Priorización

**✅ Correcto:**
- Usa prioridades apropiadas
- Urgent solo para bugs críticos
- Normal para trabajo regular

**❌ Incorrecto:**
- Marcar todo como Urgent
- No priorizar adecuadamente

## Patrones Recomendados

### Patrón 1: Crear Issue desde Error

```markdown
Proceso:
1. Analiza el error
2. Identifica la causa raíz
3. Crea issue con:
   - Título: "bug: [descripción del error]"
   - Descripción: Contexto técnico + stack trace
   - Labels: "bug", "[área]"
   - Prioridad: Según severidad
```

### Patrón 2: Dividir Features Grandes

```markdown
Proceso:
1. Crea issue padre para la feature
2. Divide en issues más pequeños:
   - Diseño/Arquitectura
   - Implementación backend
   - Implementación frontend
   - Tests
   - Documentación
3. Establece dependencias entre issues
```

### Patrón 3: Actualizar Issue desde Commit

```markdown
Proceso:
1. Al hacer commit relacionado con issue
2. Actualiza el issue:
   - Comentario con hash del commit
   - Cambiar estado si corresponde
   - Añadir información relevante
```

### Patrón 4: Flujo de Trabajo Estándar

```markdown
1. Crear issue → Estado: "Backlog"
2. Asignar → Estado: "Todo"
3. Empezar trabajo → Estado: "In Progress"
4. Enviar a revisión → Estado: "In Review"
5. Completar → Estado: "Done"
```

### Patrón 5: Generar Reportes

```markdown
Regularmente:
- Issues completados en el período
- Issues bloqueados
- Issues urgentes pendientes
- Velocidad del equipo
```

## Anti-Patterns a Evitar

### ❌ Anti-Pattern 1: Issues Vagos

**Evitar:**
```
Título: "Corregir bug"
Descripción: "Algo está mal"
```

**Hacer:**
```
Título: "bug: El login falla con error 401 usando OAuth2"
Descripción: "Cuando los usuarios intentan iniciar sesión con OAuth2, obtienen error 401.
Stack trace: [trace]
Esperado: El usuario debería iniciar sesión exitosamente
Actual: Error 401 No autorizado"
```

### ❌ Anti-Pattern 2: Issues Sin Contexto

**Evitar:**
- Crear issues sin contexto técnico
- No proporcionar información relevante
- Sin referencias a código

**Hacer:**
- Incluir contexto completo
- Referencias a archivos de código
- Stack traces cuando aplica
- Pasos para reproducir

### ❌ Anti-Pattern 3: Sobrecarga de Labels

**Evitar:**
```
Labels: "bug,frontend,ui,urgent,hotfix,critical,high-priority"
```

**Hacer:**
```
Labels: "bug,frontend,urgent"
```

### ❌ Anti-Pattern 4: Issues Sin Seguimiento

**Evitar:**
- Crear issues y olvidarlos
- No actualizar estados
- No añadir comentarios relevantes

**Hacer:**
- Actualizar estado regularmente
- Añadir comentarios con progreso
- Cerrar issues cuando se completan

### ❌ Anti-Pattern 5: Múltiples Issues para lo Mismo

**Evitar:**
- Crear issues duplicados
- No buscar issues existentes antes de crear

**Hacer:**
- Buscar issues similares primero
- Actualizar issues existentes si aplica
- Usar comentarios para añadir información

### ❌ Anti-Pattern 6: Comandos Mal Formateados

**Evitar:**
```
@linear create issue "bug" --team engineering
```

**Hacer:**
```
@linear create issue "bug: Login fails with OAuth2" \
  --team "Engineering" \
  --description "Detailed description" \
  --labels "bug,authentication"
```

## Reglas para Agentes

### Regla 1: Siempre Contextualizar

Antes de crear un issue, el agente debe:
- Buscar issues similares
- Analizar el contexto del código
- Proporcionar información completa

### Regla 2: Validar Información

El agente debe:
- Verificar que los equipos existan
- Confirmar que los labels existan
- Validar formatos de fechas

### Regla 3: Seguir Convenciones

El agente debe:
- Usar el formato de títulos establecido
- Seguir las reglas de labels
- Mantener consistencia en descripciones

### Regla 4: Documentar Cambios

El agente debe:
- Añadir comentarios cuando actualiza issues
- Explicar razones de cambios
- Mantener historial claro

## Checklist de Calidad

Antes de crear un issue, verifica:

- [ ] Título descriptivo y claro
- [ ] Descripción con contexto técnico
- [ ] Equipo correcto asignado
- [ ] Labels apropiados
- [ ] Prioridad correcta
- [ ] Estado inicial apropiado
- [ ] Referencias a código si aplica
- [ ] Pasos para reproducir (si es bug)

## Reglas de Comunicación

### Con el Agente

**✅ Correcto:**
```
Crea un issue para el bug que estamos viendo en el login.
El error es: [error]
Ocurre cuando: [situación]
```

**❌ Incorrecto:**
```
Crea un issue
```

### Actualizaciones

**✅ Correcto:**
```
Actualiza el issue ISSUE-123 con un comentario indicando que 
el fix está en el commit abc123 y está listo para QA.
```

**❌ Incorrecto:**
```
Actualiza el issue
```

## Referencias

- Ver comandos en `docs/commands/`
- Ver técnicas de agentes en `docs/agents/expert-agents.md`
- Ver ejemplos en `examples/`

