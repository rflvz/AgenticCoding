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
>     
>     Estos comandos se activan en tu proyecto simplemente poniendo:
>     `/el-comando`
>     Por ejemplo: `/create-issues`, `/complete-issues`, `/review-issues`

# Variables Útiles

Guía profesional para recordar usar estados y características al crear issues en Linear, asegurando que los issues no se creen vacíos.

## Filosofía: Crear Issues Completos

**⚠️ REGLA CRÍTICA: Los issues deben crearse con toda la información necesaria, NO vacíos:**

Cuando crees issues en Linear, **NO** los dejes vacíos. Actúa como un **desarrollador profesional** que:

1. **Usa estados apropiados** al crear issues
2. **Asigna prioridades** según la importancia
3. **Añade labels** para mejor organización
4. **Asigna a usuarios** cuando sea apropiado
5. **Añade descripciones completas** con contexto técnico

## Proceso de Uso Profesional

### Paso 1: Estados de Issues

**⚠️ REGLA CRÍTICA: Siempre asigna un estado apropiado al crear issues:**

#### Estados Disponibles

- `Backlog` - Pendiente, no iniciado
- `Todo` - Por hacer, listo para empezar
- `In Progress` - En progreso, trabajo activo
- `In Review` - En revisión, esperando aprobación
- `Done` - Completado
- `Canceled` - Cancelado

**Uso profesional:**
- Usa `Todo` para issues nuevos que están listos para empezar
- Usa `In Progress` cuando empieces a trabajar en el issue
- Usa `In Review` cuando el trabajo esté completo y esperando revisión
- Usa `Done` solo cuando el issue esté completamente completado y aprobado

### Paso 2: Prioridades

**⚠️ REGLA CRÍTICA: Siempre asigna una prioridad apropiada:**

#### Prioridades Disponibles

- `Urgent` - Urgente (solo bugs críticos que bloquean producción)
- `High` - Alta (features importantes o bugs significativos)
- `Normal` - Normal (por defecto, trabajo regular)
- `Low` - Baja (mejoras menores)

**Uso profesional:**
- No marques todo como Urgent
- Usa prioridades apropiadamente según la importancia
- Revisa prioridades regularmente

### Paso 3: Labels

**⚠️ REGLA CRÍTICA: Usa labels para mejor organización:**

#### Labels Comunes

- **Tipos**: `bug`, `feature`, `refactor`, `docs`, `chore`
- **Áreas**: `frontend`, `backend`, `api`, `database`
- **Severidad**: `urgent`, `high-priority`, `low-priority`

**Uso profesional:**
- Usa labels consistentemente según convenciones del proyecto
- Combina tipos con áreas para mejor organización
- Usa máximo 5 labels por issue

### Paso 4: Asignación

**⚠️ REGLA CRÍTICA: Asigna issues a usuarios apropiados:**

#### Asignación

- Asigna a usuarios específicos cuando sea apropiado
- Usa `"me"` para auto-asignación
- Deja sin asignar si no está claro quién debe trabajar en el issue

**Uso profesional:**
- Asigna issues cuando sepas quién debe trabajar en ellos
- Usa auto-asignación cuando vayas a trabajar en el issue tú mismo
- Reasigna si es necesario durante el desarrollo

### Paso 5: Descripciones Completas

**⚠️ REGLA CRÍTICA: Añade descripciones completas con contexto técnico:**

#### Información a Incluir

- Contexto técnico completo
- Pasos para reproducir (si es un bug)
- Comportamiento esperado vs actual
- Código relevante
- Referencias a archivos

**Uso profesional:**
- Incluye contexto técnico suficiente
- Añade ejemplos cuando sea útil
- Referencia código y archivos relevantes

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Usa estos recordatorios al usar los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Usa estados, prioridades, labels y descripciones completas al crear issues
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Actualiza estados apropiadamente durante el proceso
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Verifica que los issues tengan toda la información necesaria

**Cuándo usar cada uno:**
- **Estados**: Al crear issues y durante el proceso de desarrollo
- **Prioridades**: Al crear issues para indicar importancia
- **Labels**: Al crear issues para mejor organización
- **Descripciones**: Siempre al crear issues para proporcionar contexto

## Checklist de Profesionalismo

### ⚠️ Al Crear Issues

- [ ] ¿He asignado un estado apropiado?
- [ ] ¿He asignado una prioridad apropiada?
- [ ] ¿He añadido labels apropiados?
- [ ] ¿He asignado a un usuario apropiado?
- [ ] ¿He añadido una descripción completa con contexto técnico?

### Antes de Completar Issues

- [ ] ¿He actualizado el estado apropiadamente?
- [ ] ¿He añadido comentarios con contexto técnico?
- [ ] ¿He incluido referencias a commits y PRs?

## Consejos Finales

1. **⚠️ Nunca crees issues vacíos** - Siempre incluye estado, prioridad, labels y descripción
2. **Usa estados apropiadamente** - Indica claramente el estado del issue
3. **Asigna prioridades correctamente** - No marques todo como Urgent
4. **Usa labels consistentemente** - Sigue convenciones del proyecto
5. **Añade descripciones completas** - Proporciona contexto técnico suficiente
6. **Integra con comandos FUNCIONALES** - Para procesos completos y trabajo profesional

---
_Hecho por Cursor_
