# Revisar Issues Profesionalmente

Guía profesional para revisar issues en Linear que están en estado "In Review" actuando como un revisor de código/project manager experto. **NO solo apruebes el issue sin revisar**. Revisa el trabajo de manera profesional, verificando el código, Pull Requests, tests, y criterios de aceptación antes de aprobar o solicitar cambios.

## Filosofía: Revisar Profesionalmente

Cuando revises un issue, **NO** solo lo apruebes sin revisar. Actúa como un **revisor de código profesional** que:

1. **Analiza completamente el issue** antes de revisar
2. **Revisa el código implementado** y Pull Requests
3. **Verifica que cumple los criterios de aceptación** del issue
4. **Ejecuta y verifica tests** si aplica
5. **Verifica que funciona correctamente** antes de aprobar
6. **Solicita cambios** si algo no está correcto
7. **Aprueba profesionalmente** cuando todo está correcto
8. **Actualiza el estado del issue** apropiadamente según el resultado
9. **Documenta la revisión** realizada

## Proceso Profesional de Revisión de Issues

### Paso 1: Análisis Profundo del Issue en "In Review"

**ANTES de revisar:**

1. **Obtener detalles completos del issue:**
   - Usa: `get_issue`
   - Parámetros: `id` (ID del issue, ej: "ISSUE-123")
   - Revisa toda la información: título, descripción, estado, asignado, labels, criterios de aceptación, etc.

2. **Verificar que está en estado "In Review":**
   - El issue debe estar en estado "In Review" para ser revisado
   - Si no está en "In Review", usa `list_issue_statuses` para verificar estados disponibles
   - Si está en otro estado, informa al usuario antes de proceder

3. **Analizar el contenido del issue:**
   - ¿Qué requiere exactamente el issue?
   - ¿Cuáles son los criterios de aceptación claros?
   - ¿Hay dependencias o sub-issues relacionados?
   - ¿Hay referencias a código existente?
   - ¿Hay contexto técnico suficiente?

4. **Identificar recursos de revisión:**
   - ¿Hay Pull Request asociado? (verificar enlaces o comentarios)
   - ¿Hay commits relacionados? (verificar en comentarios)
   - ¿Hay código implementado en el repositorio?
   - ¿Hay tests asociados?

### Paso 2: Revisar Código Implementado

**Revisar el código profesionalmente:**

1. **Localizar el código implementado:**
   - Si hay Pull Request, revisar los cambios en el PR
   - Si no hay PR, buscar archivos modificados/creados mencionados en comentarios
   - Verificar la estructura del código según el issue

2. **Revisar calidad del código:**
   - ¿El código sigue las convenciones del proyecto?
   - ¿Está bien estructurado y organizado?
   - ¿Tiene comentarios apropiados cuando es necesario?
   - ¿Está documentado correctamente?
   - ¿Sigue las mejores prácticas?

3. **Verificar implementación:**
   - ¿El código implementa exactamente lo que requiere el issue?
   - ¿Cumple con todos los requisitos mencionados?
   - ¿Hay código innecesario o no relacionado?
   - ¿Está completo o hay partes pendientes?

### Paso 3: Verificar Criterios de Aceptación

**Verificar que cumple los criterios de aceptación:**

1. **Revisar criterios de aceptación del issue:**
   - Lee la sección "Criterios de Aceptación" en la descripción del issue
   - Identifica cada criterio como checkbox `- [ ]`
   - Verifica que cada criterio esté cumplido

2. **Verificar cada criterio:**
   - Para cada criterio, verifica que está implementado correctamente
   - Si un criterio no está cumplido, documenta el problema
   - Si todos los criterios están cumplidos, procede con la siguiente verificación

3. **Documentar verificación:**
   - Añade comentario en el issue indicando qué criterios se verificaron
   - Menciona si hay criterios que no se cumplen

### Paso 4: Ejecutar y Verificar Tests

**Verificar que los tests pasan:**

1. **Identificar tests relacionados:**
   - ¿Hay tests unitarios para el código implementado?
   - ¿Hay tests de integración si aplica?
   - ¿Hay tests mencionados en el issue o PR?

2. **Ejecutar tests:**
   - Si hay tests, ejecútalos para verificar que pasan
   - Verifica que no hay tests fallidos
   - Verifica que la cobertura de tests es apropiada (si aplica)

3. **Verificar funcionalidad:**
   - Prueba manualmente la funcionalidad si es posible
   - Verifica que funciona como se espera según el issue
   - Verifica que no rompe funcionalidad existente

4. **Documentar resultados de tests:**
   - Si los tests pasan, documenta en el comentario
   - Si los tests fallan, documenta los problemas específicos
   - Si no hay tests, menciona si se requieren según el tipo de código

### Paso 5: Revisar Pull Request (si aplica)

**Revisar Pull Request profesionalmente:**

1. **Localizar Pull Request:**
   - Buscar enlaces a PR en comentarios del issue
   - Verificar si hay PR asociado en el repositorio
   - Si hay PR, revisar los cambios propuestos

2. **Revisar cambios del PR:**
   - ¿Los cambios son apropiados para el issue?
   - ¿Hay cambios no relacionados con el issue?
   - ¿Los commits están bien estructurados?
   - ¿El PR tiene descripción clara?

3. **Verificar integración:**
   - ¿El PR se integra correctamente con el código base?
   - ¿Hay conflictos que necesitan resolverse?
   - ¿El PR está actualizado con la rama principal?

4. **Documentar revisión del PR:**
   - Menciona el PR en el comentario de revisión
   - Indica si el PR está listo o necesita cambios

### Paso 6: Decisión de Aprobación o Solicitud de Cambios

**Tomar decisión profesional basada en la revisión:**

#### Criterios para Aprobar

**Aprueba el issue cuando:**
- ✅ El código implementa correctamente lo requerido
- ✅ Todos los criterios de aceptación están cumplidos
- ✅ Los tests pasan (si aplica)
- ✅ El código sigue las convenciones del proyecto
- ✅ La funcionalidad funciona correctamente
- ✅ No rompe funcionalidad existente
- ✅ El PR está listo (si aplica)

#### Criterios para Solicitar Cambios

**Solicita cambios cuando:**
- ❌ El código no implementa completamente lo requerido
- ❌ Hay criterios de aceptación no cumplidos
- ❌ Los tests fallan
- ❌ El código no sigue las convenciones del proyecto
- ❌ La funcionalidad no funciona correctamente
- ❌ Rompe funcionalidad existente
- ❌ El PR tiene problemas o conflictos
- ❌ Falta documentación o comentarios necesarios
- ❌ Hay código innecesario o no relacionado

### Paso 7: Actualizar Estado del Issue y Documentar Revisión

**Actualizar el issue según el resultado de la revisión:**

#### Si Aprobar

1. **Actualizar estado a "Done":**
   - Usa: `update_issue` con `id` (ID del issue), `state: "Done"`
   - **Solo aprueba si todo está correcto y verificado**

2. **Añadir comentario profesional de aprobación:**
   - Usa: `create_comment`
   - Incluye:
     - Resumen de la revisión realizada
     - Confirmación de que cumple los criterios de aceptación
     - Mención de tests ejecutados (si aplica)
     - Mención de PR revisado (si aplica)
     - Confirmación de que está listo para producción
   - **IMPORTANTE**: Siempre añade al final: `---\n_Hecho por Cursor_`

3. **Marcar criterios de aceptación como completados:**
   - Si es posible, actualiza la descripción del issue marcando los criterios como `- [x]`
   - Usa: `update_issue` con `id` y `description` actualizada

#### Si Solicitar Cambios

1. **Mantener estado "In Review" o cambiar según necesidad:**
   - Por defecto, mantén en "In Review"
   - Si requiere trabajo significativo, puedes cambiar a "In Progress" (consulta con el usuario)

2. **Añadir comentario profesional solicitando cambios:**
   - Usa: `create_comment`
   - Incluye:
     - Resumen de la revisión realizada
     - Lista específica de problemas encontrados
     - Criterios de aceptación no cumplidos
     - Sugerencias para mejorar el código
     - Tests fallidos (si aplica)
     - Pasos específicos para resolver los problemas
   - **IMPORTANTE**: Siempre añade al final: `---\n_Hecho por Cursor_`

3. **Documentar problemas específicos:**
   - Sé específico sobre qué necesita cambiar
   - Proporciona ejemplos cuando sea posible
   - Indica prioridad de los cambios (crítico, importante, menor)

### Paso 8: Actualizar Issue Padre (si aplica)

**Si el issue revisado es un sub-issue:**

1. **Verificar progreso del issue padre:**
   - Obtén el issue padre: `get_issue` con `id` del `parentId`
   - Lista sub-issues: `list_issues` con `parentId` del issue padre
   - Calcula progreso: cuenta cuántos sub-issues tienen `state: "Done"` vs total

2. **Actualizar issue padre con progreso:**
   - Si se aprobó el sub-issue, actualiza descripción del padre con progreso
   - Añade comentario: `create_comment` con `issueId` del padre y mensaje de progreso
   - **IMPORTANTE**: Siempre añade al final del comentario: `---\n_Hecho por Cursor_`

## Herramientas de Referencia

### Obtener Issue

**Herramienta:** `get_issue`

**Parámetros:**
- `id` (requerido): ID del issue (ej: "ISSUE-123")

**Retorna:** Información completa del issue incluyendo título, descripción, estado, asignado, labels, parentId, criterios de aceptación, etc.

### Actualizar Issue

**Herramienta:** `update_issue`

**Parámetros:**
- `id` (requerido): ID del issue
- `state` (opcional): Nuevo estado (ej: "Done", "In Progress", "In Review")
- `description` (opcional): Descripción actualizada (para marcar criterios como completados)

**Uso:** Actualiza el estado a "Done" cuando apruebas, o mantén en "In Review" cuando solicitas cambios.

### Añadir Comentario

**Herramienta:** `create_comment`

**Parámetros:**
- `issueId` (requerido): ID del issue
- `body` (requerido): Contenido del comentario (soporta Markdown)
- `parentId` (opcional): ID de comentario padre para respuestas

**IMPORTANTE - Formato de Comentarios:**
- **Siempre** incluye al final de cada comentario: `---\n_Hecho por Cursor_`
- Esto indica que el trabajo fue realizado por Cursor y permite tracking

**Formato de Comentario de Aprobación:**
```markdown
## ✅ Revisión Completada - Aprobado

He revisado el código implementado y puedo confirmar:

- ✅ Todos los criterios de aceptación están cumplidos
- ✅ El código sigue las convenciones del proyecto
- ✅ Los tests pasan correctamente
- ✅ La funcionalidad funciona como se espera
- ✅ No hay problemas detectados

**Pull Request:** [Enlace al PR si aplica]
**Tests:** Todos los tests pasan ✓

El issue está listo para producción.

---
_Hecho por Cursor_
```

**Formato de Comentario Solicitando Cambios:**
```markdown
## ⚠️ Revisión Completada - Se Requieren Cambios

He revisado el código implementado y encontré los siguientes problemas:

### Problemas Críticos:
- ❌ [Descripción del problema crítico]
- ❌ [Descripción del problema crítico]

### Problemas Importantes:
- ⚠️ [Descripción del problema importante]
- ⚠️ [Descripción del problema importante]

### Mejoras Sugeridas:
- 💡 [Sugerencia de mejora]
- 💡 [Sugerencia de mejora]

### Criterios de Aceptación No Cumplidos:
- [ ] Criterio 1: [Razón]
- [ ] Criterio 2: [Razón]

Por favor, realiza los cambios necesarios y vuelve a poner el issue en "In Review" cuando esté listo.

---
_Hecho por Cursor_
```

### Listar Issues (Incluye Sub-issues)

**Herramienta:** `list_issues`

**Parámetros útiles:**
- `parentId`: Filtrar por issue padre (para obtener sub-issues)
- `team`: Filtrar por equipo
- `state`: Filtrar por estado (ej: "In Review" para listar issues pendientes de revisión)
- `assignee`: Filtrar por asignado
- `priority`: Filtrar por prioridad
- `label`: Filtrar por label
- `project`: Filtrar por proyecto

**Uso:** Úsalo para listar issues en "In Review" que necesitan revisión, o para obtener sub-issues de un issue padre.

### Listar Estados Disponibles

**Herramienta:** `list_issue_statuses`

**Parámetros:**
- `team` (requerido): Nombre o ID del equipo

**Retorna:** Lista de estados disponibles para el equipo, incluyendo nombres y tipos

**Uso:** Úsalo para verificar qué estados están disponibles antes de actualizar un issue, especialmente para verificar si "In Review" y "Done" existen en el equipo.

## Checklist de Profesionalismo

### ⚠️ Antes de Revisar

**Antes de revisar un issue, verifica:**
- [ ] ¿He obtenido los detalles completos del issue?
- [ ] ¿He verificado que está en estado "In Review"?
- [ ] ¿He analizado los criterios de aceptación?
- [ ] ¿He identificado recursos de revisión (PR, commits, código)?

### Durante la Revisión

**Durante la revisión, verifica:**
- [ ] ¿He revisado el código implementado?
- [ ] ¿He verificado que cumple todos los criterios de aceptación?
- [ ] ¿He ejecutado los tests (si aplica)?
- [ ] ¿He verificado que la funcionalidad funciona correctamente?
- [ ] ¿He revisado el Pull Request (si aplica)?
- [ ] ¿He documentado todos los problemas encontrados?

### ⚠️ Al Aprobar o Solicitar Cambios

**Al aprobar o solicitar cambios, verifica:**
- [ ] ¿He tomado una decisión clara basada en la revisión?
- [ ] ¿He actualizado el estado del issue apropiadamente?
- [ ] ¿He añadido un comentario profesional con la revisión?
- [ ] ¿He incluido "_Hecho por Cursor_" al final del comentario?
- [ ] ¿He actualizado el issue padre si es un sub-issue?

## Consejos Finales

1. **⚠️ NUNCA apruebes sin revisar** - Siempre revisa el código y verifica los criterios
2. **Sé específico en comentarios** - Proporciona detalles concretos sobre problemas o aprobaciones
3. **Verifica criterios de aceptación** - Asegúrate de que todos estén cumplidos antes de aprobar
4. **Ejecuta tests cuando sea posible** - Verifica que los tests pasan antes de aprobar
5. **Revisa Pull Requests** - Si hay PR, revísalo como parte del proceso
6. **Solicita cambios cuando sea necesario** - No apruebes código que no cumple los criterios
7. **Documenta la revisión** - Añade comentarios profesionales que expliquen la decisión
8. **SIEMPRE incluye "_Hecho por Cursor_"** - Permite tracking y transparencia
9. **Actualiza issue padre** - Si es un sub-issue, actualiza el progreso del padre

