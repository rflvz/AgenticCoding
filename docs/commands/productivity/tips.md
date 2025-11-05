# Consejos de Productividad

Consejos y técnicas para maximizar la productividad con Cursor y Linear.

## Organización

### 1. Usar Templates de Prompts

Guarda prompts comunes en `.cursorrules` o en archivos de ejemplos:

```markdown
## Linear Templates

Cuando digas "crear bug", crea un issue con:
- Título: "bug: [descripción]"
- Prioridad: "High"
- Labels: "bug"
- Equipo: "Engineering"
```

### 2. Abreviar Nombres de Equipo

Si tu equipo tiene un nombre largo, usa el ID del equipo:

```
@linear create issue "Título" --team "ENG"
```

### 3. Usar Labels Consistentes

Crea un conjunto estándar de labels y úsalos consistentemente:

```
--labels "bug,frontend,urgent"
```

Establece convenciones de labels:
- Tipos: `bug`, `feature`, `refactor`, `docs`, `chore`
- Áreas: `frontend`, `backend`, `api`, `database`
- Severidad: `urgent`, `high-priority`, `low-priority`

## Automatización

### 4. Automatizar con Agentes

Configura agentes especializados que automáticamente:
- Crean issues desde errores
- Actualizan issues desde commits
- Generan reportes de progreso
- Monitorean dependencias

### 5. Crear Workflows Reutilizables

Define workflows comunes para tareas repetitivas:

```
Workflow: Crear Issue desde Error
1. Analiza el error
2. Crea issue con contexto técnico
3. Prioriza según severidad
4. Asigna al equipo correcto
```

### 6. Usar Roles de Agentes

Aprovecha roles especializados para diferentes tareas:
- **Revisor de Código**: Para encontrar bugs
- **Project Manager**: Para coordinar proyectos
- **Arquitecto**: Para diseñar features
- **Developer**: Para desarrollo diario

## Comandos Rápidos

### 7. Crear Aliases Mentales

Crea aliases mentales para comandos frecuentes:

- `"mis issues"` → `@linear list issues --assignee "me"`
- `"issue urgente"` → `@linear list issues --priority "Urgent"`
- `"issues de hoy"` → `@linear list issues --created-after "-P1D"`

### 8. Combinar Comandos

Ejecuta múltiples comandos en una sola solicitud:

```
Lista mis issues en progreso y crea un issue nuevo para la tarea X
```

### 9. Usar Variables Especiales

Aprovecha variables útiles:
- `"me"` para auto-asignación
- `-P1D` para fechas relativas
- Estados predefinidos

## Contextualización

### 10. Contextualizar Agentes Apropiadamente

Contextualiza agentes con información relevante:
- Contexto del proyecto
- Convenciones del equipo
- Objetivos del sprint
- Reglas específicas

### 11. Usar .cursorrules

Crea archivos `.cursorrules` para:
- Reglas globales del proyecto
- Convenciones de creación de issues
- Labels estándar
- Prioridades por defecto

### 12. Mantener Contexto Actualizado

Actualiza el contexto del agente según:
- Cambios en el proyecto
- Nuevas convenciones
- Objetivos actuales
- Feedback recibido

## Flujos de Trabajo

### 13. Crear Issues Antes de Trabajar

Crea issues antes de empezar a trabajar:
1. Define la tarea claramente
2. Establece criterios de aceptación
3. Prioriza apropiadamente
4. Asigna al equipo correcto

### 14. Actualizar Issues Regularmente

Mantén issues actualizados:
- Actualiza estado al empezar trabajo
- Añade comentarios con progreso
- Completa issues cuando terminas
- Documenta decisiones importantes

### 15. Buscar Issues Antes de Crear

Siempre busca issues similares antes de crear uno nuevo:
- Evita duplicados
- Actualiza issues existentes si aplica
- Agrupa issues relacionados

## Mejores Prácticas

### 16. Títulos Descriptivos

Usa títulos claros y descriptivos:
- ✅ `bug: Login fails with OAuth2 tokens`
- ❌ `Fix bug`

### 17. Descripciones Completas

Incluye contexto técnico completo:
- Pasos para reproducir
- Comportamiento esperado vs actual
- Código relevante
- Referencias a archivos

### 18. Priorizar Correctamente

No marques todo como Urgent:
- `Urgent`: Solo bugs críticos que bloquean producción
- `High`: Features importantes o bugs significativos
- `Normal`: Trabajo regular
- `Low`: Mejoras menores

### 19. Usar Labels Apropiadamente

Usa labels consistentemente:
- Máximo 5 labels por issue
- Combina tipos con áreas
- Evita labels redundantes

### 20. Documentar Cambios

Añade comentarios explicando:
- Cambios realizados
- Razones de decisiones
- Referencias a commits
- Próximos pasos

