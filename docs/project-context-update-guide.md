# Guía de Actualización del Documento de Contexto

Guía para mantener actualizado el documento centralizado de contexto del proyecto (`docs/project-context.md`).

## Propósito

El documento de contexto (`docs/project-context.md`) es la fuente única de verdad para información del proyecto y trabajo en Linear. Esta guía explica cómo mantenerlo actualizado.

## Cuándo Actualizar

### Actualizaciones Requeridas

Actualiza el documento cuando:

1. **Cambios en el proyecto:**
   - Nueva estructura de directorios
   - Cambios en tecnologías o herramientas
   - Nuevas decisiones arquitectónicas
   - Cambios en objetivos o estado del proyecto

2. **Cambios en Linear:**
   - Nuevos proyectos creados
   - Nuevos issues creados o completados
   - Cambios en prioridades de issues
   - Cambios en estado de issues (In Progress, Done, etc.)
   - Nuevos bloqueos o dependencias identificados

3. **Cambios en convenciones:**
   - Nuevas convenciones de commits
   - Cambios en estructura de branches
   - Actualizaciones en estándares de documentación
   - Cambios en convenciones de issues

4. **Decisiones importantes:**
   - Decisiones arquitectónicas
   - Cambios en estrategia
   - Nuevos procesos o workflows

### Frecuencia de Actualización

- **Actualización mínima:** Semanal
- **Actualización recomendada:** Después de cambios significativos
- **Actualización automática:** Idealmente automática (cuando se implemente)

## Proceso de Actualización

### 1. Recopilar Información

#### Información del Proyecto

1. **Revisar estructura del proyecto:**
   ```bash
   # Ver estructura de directorios
   tree -L 2 -I 'node_modules|.git'
   ```

2. **Revisar README:**
   - Leer `README.md` para verificar cambios en descripción o objetivos
   - Verificar cambios en estructura de documentación

3. **Revisar cambios recientes:**
   ```bash
   # Ver commits recientes
   git log --oneline -10
   ```

#### Información de Linear

1. **Listar proyectos activos:**
   - Usar: `mcp_Linear_list_projects` con `team: "DAW"`
   - Verificar nuevos proyectos, cambios en prioridades, estados

2. **Listar issues activos:**
   - Usar: `mcp_Linear_list_issues` con `team: "DAW"`, `state: "In Progress"` o `state: "Todo"`
   - Verificar nuevos issues, cambios en prioridades, estados, asignaciones

3. **Obtener detalles de issues importantes:**
   - Usar: `mcp_Linear_get_issue` para issues relevantes
   - Verificar cambios en descripciones, criterios de aceptación, dependencias

### 2. Actualizar Documento

#### Sección: Información del Proyecto

Actualiza cuando:
- Cambie la estructura del proyecto
- Cambien las tecnologías o herramientas
- Cambien los objetivos o estado del proyecto

**Ejemplo de actualización:**
```markdown
### Estado Actual del Proyecto

- **Fase:** Desarrollo activo
- **Enfoque:** Documentación y mejora de comandos
- **Prioridad:** Alta
- **Última actualización:** 2025-11-05
```

#### Sección: Información de Linear

Actualiza cuando:
- Se creen nuevos proyectos
- Cambien prioridades de proyectos
- Se creen o completen issues
- Cambien prioridades de issues

**Ejemplo de actualización:**
```markdown
### Issues Activos (En Progreso)

#### DAW-XX: Título del Issue

- **ID:** `uuid-del-issue`
- **Prioridad:** High
- **Estado:** In Progress
- **Asignado:** Usuario
- **Proyecto:** Nombre del proyecto
- **Labels:** label1, label2
- **Branch:** `feature/DAW-XX-descripcion`
- **Objetivo:** Descripción breve del objetivo
- **URL:** https://linear.app/...
```

#### Sección: Prioridades y Focos

Actualiza cuando:
- Cambien prioridades de issues o proyectos
- Se identifiquen nuevos focos

#### Sección: Decisiones Arquitectónicas

Añade nuevas decisiones cuando:
- Se tome una decisión arquitectónica importante
- Se cambie una decisión previa

**Formato:**
```markdown
### Decisión: Nombre de la Decisión

**Fecha:** YYYY-MM-DD  
**Decisión:** Descripción de la decisión.  
**Razón:** Razón de la decisión.  
**Impacto:** Impacto en el proyecto.
```

#### Sección: Bloqueos y Dependencias

Actualiza cuando:
- Se identifique un nuevo bloqueo
- Se resuelva un bloqueo
- Cambien dependencias entre issues

#### Sección: Próximos Pasos

Actualiza cuando:
- Se completen pasos
- Se identifiquen nuevos pasos
- Cambien prioridades de pasos

### 3. Actualizar Fecha de Última Actualización

Siempre actualiza:
```markdown
**Última actualización:** YYYY-MM-DD
```

## Automatización

### Actualización Manual (Actual)

Actualmente el documento se actualiza manualmente siguiendo este proceso.

### Actualización Automática (Futuro)

**Idealmente**, el documento debería actualizarse automáticamente:

1. **Script de actualización:**
   - Consulta Linear API para obtener información actualizada
   - Actualiza secciones relevantes del documento
   - Mantiene historial de cambios

2. **Triggers automáticos:**
   - Cuando se crea un issue en Linear
   - Cuando cambia el estado de un issue
   - Cuando se crea un proyecto
   - Cuando cambia una prioridad

3. **Integración con comandos:**
   - Los comandos actualizan el documento automáticamente
   - Los agentes actualizan el documento cuando completan tareas

## Verificación

Antes de considerar el documento actualizado, verifica:

- [ ] ¿La fecha de última actualización está actualizada?
- [ ] ¿Los proyectos activos están listados correctamente?
- [ ] ¿Los issues activos están listados correctamente?
- [ ] ¿Las prioridades están correctas?
- [ ] ¿Los bloqueos y dependencias están actualizados?
- [ ] ¿Los próximos pasos reflejan el estado actual?
- [ ] ¿Las decisiones arquitectónicas están documentadas?

## Ejemplos de Actualización

### Ejemplo 1: Nuevo Issue Creado

**Antes:**
```markdown
### Issues Activos (En Progreso)

#### DAW-21: Acceso centralizado a documento de contexto
...
```

**Después:**
```markdown
### Issues Activos (En Progreso)

#### DAW-21: Acceso centralizado a documento de contexto
...

#### DAW-22: Nueva funcionalidad

- **ID:** `uuid-del-issue`
- **Prioridad:** High
- **Estado:** In Progress
- **Asignado:** Rafa
- **Proyecto:** Agentización con Linear en Cursor
- **Labels:** feature, agentization
- **Branch:** `feature/DAW-22-nueva-funcionalidad`
- **Objetivo:** Descripción del objetivo
- **URL:** https://linear.app/...
```

### Ejemplo 2: Issue Completado

**Antes:**
```markdown
### Issues Activos (En Progreso)

#### DAW-21: Acceso centralizado a documento de contexto
...
```

**Después:**
```markdown
### Issues Activos (En Progreso)

*(DAW-21 completado y movido a "Done")*

### Issues Recientemente Completados

#### DAW-21: Acceso centralizado a documento de contexto
- **Completado:** 2025-11-05
- **Estado Final:** Done
```

### Ejemplo 3: Nueva Decisión Arquitectónica

**Antes:**
```markdown
## Decisiones Arquitectónicas

### Decisión: Documento Centralizado de Contexto
...
```

**Después:**
```markdown
## Decisiones Arquitectónicas

### Decisión: Documento Centralizado de Contexto
...

### Decisión: Nueva Estructura de Comandos

**Fecha:** 2025-11-05  
**Decisión:** Reorganizar comandos en subcarpetas por categoría.  
**Razón:** Mejorar navegación y mantenimiento.  
**Impacto:** Todos los comandos deben moverse a nuevas ubicaciones.
```

## Mejores Prácticas

1. **Actualiza regularmente:** No dejes el documento desactualizado por mucho tiempo
2. **Sé preciso:** Asegúrate de que la información sea exacta y actual
3. **Mantén estructura:** Respeta la estructura del documento para facilitar lectura
4. **Documenta decisiones:** Siempre documenta decisiones importantes
5. **Verifica información:** Verifica que la información de Linear sea correcta antes de actualizar

## Referencias

- [Documento de Contexto](./project-context.md)
- [Comandos de Linear](./commands/linear/)
- [Contexto Compartido](./agentization/shared-context.md)

---

**Última actualización:** 2025-11-05

