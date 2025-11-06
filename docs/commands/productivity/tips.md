> **⚠️⚠️⚠️ EXPERIMENTAL ⚠️⚠️⚠️**
> 
> **Este comando es EXPERIMENTAL y está en desarrollo. No confiar ciegamente.**
> 
> **Para comandos FUNCIONALES, usa los comandos de Linear en `.cursor/commands/`:**
> - ✅ [Inicializar Contexto del Proyecto](../../../.cursor/commands/initialize-project-context.md)
> - ✅ [Crear Issues](../../../.cursor/commands/create-issues.md)
> - ✅ [Completar Issues](../../../.cursor/commands/complete-issues.md)
> - ✅ [Revisar Issues](../../../.cursor/commands/review-issues.md)
> - ✅ [Crear Proyectos](../../../.cursor/commands/create-projects.md)
> - ✅ [Listar y Buscar](../../../.cursor/commands/list-search.md)

# Consejos de Productividad

Guía profesional de consejos y técnicas para maximizar la productividad con Cursor y Linear, basada en mejores prácticas y experiencia real.

## Filosofía: Maximizar Productividad

La productividad no es solo velocidad, es **eficiencia y calidad**. Actúa como un **desarrollador profesional** que:

1. **Automatiza tareas repetitivas** para enfocarse en lo importante
2. **Organiza el trabajo** para reducir fricción
3. **Usa herramientas apropiadamente** según el contexto
4. **Mantiene contexto actualizado** para decisiones informadas
5. **Documenta decisiones** para referencia futura

## Proceso de Mejora de Productividad

### Paso 1: Organización Profesional

**⚠️ REGLA CRÍTICA: La organización es la base de la productividad:**

#### 1. Usar Templates de Prompts

**Problema:** Repetir los mismos prompts una y otra vez.

**Solución:** Guarda prompts comunes en `.cursorrules` o archivos de ejemplos:

```markdown
## Linear Templates

Cuando digas "crear bug", crea un issue con:
- Título: "bug: [descripción]"
- Prioridad: "High"
- Labels: "bug"
- Equipo: "Engineering"
```

**Uso profesional:**
- Crea templates para tareas comunes
- Personaliza templates según tu proyecto
- Actualiza templates cuando cambien las convenciones

#### 2. Abreviar Nombres de Equipo

**Problema:** Nombres de equipo largos ralentizan comandos.

**Solución:** Usa el ID del equipo o abreviaciones:

```bash
@linear create issue "Título" --team "ENG"
```

**Uso profesional:**
- Usa abreviaciones consistentes
- Documenta abreviaciones para referencia
- Crea aliases mentales para equipos frecuentes

#### 3. Usar Labels Consistentes

**Problema:** Labels inconsistentes dificultan búsqueda y filtrado.

**Solución:** Crea un conjunto estándar de labels y úsalos consistentemente:

```bash
--labels "bug,frontend,urgent"
```

**Convenciones de labels:**
- **Tipos**: `bug`, `feature`, `refactor`, `docs`, `chore`
- **Áreas**: `frontend`, `backend`, `api`, `database`
- **Severidad**: `urgent`, `high-priority`, `low-priority`

**Uso profesional:**
- Establece convenciones de labels al inicio del proyecto
- Documenta convenciones en `.cursorrules`
- Revisa y actualiza convenciones regularmente

### Paso 2: Automatización Inteligente

**⚠️ REGLA CRÍTICA: La automatización elimina fricción y errores:**

#### 4. Automatizar con Agentes

**Problema:** Tareas repetitivas consumen tiempo y energía.

**Solución:** Configura agentes especializados que automáticamente:
- Crean issues desde errores
- Actualizan issues desde commits
- Generan reportes de progreso
- Monitorean dependencias

**Uso profesional:**
- Identifica tareas repetitivas en tu flujo
- Crea agentes especializados para cada tarea
- Documenta agentes para referencia futura

#### 5. Crear Workflows Reutilizables

**Problema:** Flujos de trabajo complejos se repiten frecuentemente.

**Solución:** Define workflows comunes para tareas repetitivas:

```
Workflow: Crear Issue desde Error
1. Analiza el error
2. Crea issue con contexto técnico
3. Prioriza según severidad
4. Asigna al equipo correcto
```

**Uso profesional:**
- Identifica flujos de trabajo frecuentes
- Crea workflows reutilizables
- Personaliza workflows según necesidades

#### 6. Usar Roles de Agentes

**Problema:** Agentes genéricos no son eficientes para tareas específicas.

**Solución:** Aprovecha roles especializados para diferentes tareas:
- **Revisor de Código**: Para encontrar bugs
- **Project Manager**: Para coordinar proyectos
- **Arquitecto**: Para diseñar features
- **Developer**: Para desarrollo diario

**Uso profesional:**
- Activa roles apropiados según la tarea
- Crea roles personalizados para tu proyecto
- Documenta roles para referencia

### Paso 3: Comandos Rápidos y Eficientes

**⚠️ REGLA CRÍTICA: Los comandos rápidos aceleran significativamente el trabajo:**

#### 7. Crear Aliases Mentales

**Problema:** Comandos largos ralentizan el trabajo.

**Solución:** Crea aliases mentales para comandos frecuentes:

- `"mis issues"` → `@linear list issues --assignee "me"`
- `"issue urgente"` → `@linear list issues --priority "Urgent"`
- `"issues de hoy"` → `@linear list issues --created-after "-P1D"`

**Uso profesional:**
- Crea aliases para comandos que usas frecuentemente
- Documenta aliases para referencia
- Comparte aliases útiles con el equipo

#### 8. Combinar Comandos

**Problema:** Ejecutar múltiples comandos secuencialmente es lento.

**Solución:** Ejecuta múltiples comandos en una sola solicitud:

```
Lista mis issues en progreso y crea un issue nuevo para la tarea X
```

**Uso profesional:**
- Combina comandos relacionados
- Usa lenguaje natural para comandos complejos
- Deja que el agente interprete y ejecute

#### 9. Usar Variables Especiales

**Problema:** Referencias largas ralentizan comandos.

**Solución:** Aprovecha variables útiles:
- `"me"` para auto-asignación
- `-P1D` para fechas relativas
- Estados predefinidos

**Uso profesional:**
- Usa `"me"` constantemente para auto-asignación
- Las fechas relativas (`-P1D`) son más útiles que fechas absolutas
- Combina variables para comandos más expresivos

### Paso 4: Contextualización Profesional

**⚠️ REGLA CRÍTICA: El contexto correcto mejora significativamente los resultados:**

#### 10. Contextualizar Agentes Apropiadamente

**Problema:** Agentes sin contexto producen resultados genéricos.

**Solución:** Contextualiza agentes con información relevante:
- Contexto del proyecto
- Convenciones del equipo
- Objetivos del sprint
- Reglas específicas

**Uso profesional:**
- Contextualiza agentes al inicio de cada sesión
- Actualiza contexto cuando cambie el proyecto
- Documenta contexto importante para referencia

#### 11. Usar .cursorrules

**Problema:** Reglas y convenciones se olvidan o se aplican inconsistentemente.

**Solución:** Crea archivos `.cursorrules` para:
- Reglas globales del proyecto
- Convenciones de creación de issues
- Labels estándar
- Prioridades por defecto

**Uso profesional:**
- Crea `.cursorrules` al inicio del proyecto
- Actualiza `.cursorrules` cuando cambien las convenciones
- Revisa `.cursorrules` regularmente

#### 12. Mantener Contexto Actualizado

**Problema:** Contexto desactualizado produce decisiones incorrectas.

**Solución:** Actualiza el contexto del agente según:
- Cambios en el proyecto
- Nuevas convenciones
- Objetivos actuales
- Feedback recibido

**Uso profesional:**
- Actualiza contexto al inicio de cada sesión
- Documenta cambios importantes en contexto
- Revisa contexto regularmente

### Paso 5: Flujos de Trabajo Eficientes

**⚠️ REGLA CRÍTICA: Los flujos de trabajo eficientes multiplican la productividad:**

#### 13. Crear Issues Antes de Trabajar

**Problema:** Trabajar sin issues dificulta tracking y documentación.

**Solución:** Crea issues antes de empezar a trabajar:
1. Define la tarea claramente
2. Establece criterios de aceptación
3. Prioriza apropiadamente
4. Asigna al equipo correcto

**Uso profesional:**
- Crea issues para todo el trabajo
- Usa [Crear Issues](../../../.cursor/commands/create-issues.md) para crear issues profesionalmente
- Actualiza issues regularmente durante el trabajo

#### 14. Actualizar Issues Regularmente

**Problema:** Issues desactualizados dificultan tracking y colaboración.

**Solución:** Mantén issues actualizados:
- Actualiza estado al empezar trabajo
- Añade comentarios con progreso
- Completa issues cuando terminas
- Documenta decisiones importantes

**Uso profesional:**
- Actualiza estado inmediatamente al cambiar
- Añade comentarios con contexto técnico
- Usa [Completar Issues](../../../.cursor/commands/complete-issues.md) para completar issues profesionalmente

#### 15. Buscar Issues Antes de Crear

**Problema:** Issues duplicados crean confusión y trabajo redundante.

**Solución:** Siempre busca issues similares antes de crear uno nuevo:
- Evita duplicados
- Actualiza issues existentes si aplica
- Agrupa issues relacionados

**Uso profesional:**
- Busca antes de crear
- Usa [Listar y Buscar](../../../.cursor/commands/list-search.md) para búsquedas avanzadas
- Actualiza issues existentes en lugar de crear duplicados

### Paso 6: Mejores Prácticas

**⚠️ REGLA CRÍTICA: Las mejores prácticas aseguran calidad y consistencia:**

#### 16. Títulos Descriptivos

**Problema:** Títulos vagos dificultan búsqueda y comprensión.

**Solución:** Usa títulos claros y descriptivos:
- ✅ `bug: Login fails with OAuth2 tokens`
- ❌ `Fix bug`

**Uso profesional:**
- Usa prefijos descriptivos (`bug:`, `feature:`, `docs:`)
- Incluye contexto técnico en el título
- Mantén títulos concisos pero informativos

#### 17. Descripciones Completas

**Problema:** Descripciones incompletas dificultan implementación y revisión.

**Solución:** Incluye contexto técnico completo:
- Pasos para reproducir
- Comportamiento esperado vs actual
- Código relevante
- Referencias a archivos

**Uso profesional:**
- Incluye contexto técnico suficiente
- Añade ejemplos cuando sea útil
- Referencia código y archivos relevantes

#### 18. Priorizar Correctamente

**Problema:** Todo marcado como Urgent hace que nada sea urgente.

**Solución:** No marques todo como Urgent:
- `Urgent`: Solo bugs críticos que bloquean producción
- `High`: Features importantes o bugs significativos
- `Normal`: Trabajo regular
- `Low`: Mejoras menores

**Uso profesional:**
- Usa prioridades apropiadamente
- Revisa prioridades regularmente
- Ajusta prioridades según contexto

#### 19. Usar Labels Apropiadamente

**Problema:** Labels inconsistentes o excesivos dificultan filtrado.

**Solución:** Usa labels consistentemente:
- Máximo 5 labels por issue
- Combina tipos con áreas
- Evita labels redundantes

**Uso profesional:**
- Establece convenciones de labels
- Usa labels consistentemente
- Revisa y actualiza convenciones regularmente

#### 20. Documentar Cambios

**Problema:** Cambios sin documentación dificultan tracking y revisión.

**Solución:** Añade comentarios explicando:
- Cambios realizados
- Razones de decisiones
- Referencias a commits
- Próximos pasos

**Uso profesional:**
- Documenta cambios importantes
- Incluye referencias a commits y PRs
- Explica razones de decisiones técnicas

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Estos consejos complementan los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Usa estos consejos al crear issues
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Aplica estos consejos al completar issues
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Usa estos consejos al revisar issues
- [Crear Proyectos](../../../.cursor/commands/create-projects.md) - Aplica estos consejos al crear proyectos
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Usa estos consejos al buscar issues

**Cuándo usar cada uno:**
- **Consejos (este documento)**: Para mejorar productividad general
- **Comandos FUNCIONALES**: Para procesos completos y trabajo profesional

## Checklist de Profesionalismo

### ⚠️ Al Trabajar

- [ ] ¿He creado issues antes de empezar a trabajar?
- [ ] ¿Estoy usando labels consistentemente?
- [ ] ¿Estoy actualizando issues regularmente?
- [ ] ¿Estoy documentando decisiones importantes?

### Antes de Crear Issue

- [ ] ¿He buscado issues similares para evitar duplicados?
- [ ] ¿Estoy usando títulos descriptivos?
- [ ] ¿Estoy añadiendo descripciones completas con contexto?
- [ ] ¿Estoy priorizando correctamente?

## Consejos Finales

1. **⚠️ Organiza primero** - La organización es la base de la productividad
2. **Automatiza tareas repetitivas** - Elimina fricción y errores
3. **Usa comandos rápidos** - Acelera significativamente el trabajo
4. **Mantén contexto actualizado** - Mejora significativamente los resultados
5. **Sigue mejores prácticas** - Asegura calidad y consistencia
6. **Integra con comandos FUNCIONALES** - Para procesos completos y trabajo profesional

---
_Hecho por Cursor_
