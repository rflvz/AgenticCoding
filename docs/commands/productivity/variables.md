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

# Variables Útiles

Guía profesional de variables y parámetros especiales para usar en comandos de Linear y agentización, diseñada para simplificar y acelerar el trabajo.

## Filosofía: Simplificar con Variables

Las variables especiales **simplifican y aceleran** comandos. Actúa como un **desarrollador profesional** que:

1. **Usa variables especiales** para simplificar comandos
2. **Memoriza variables frecuentes** para uso diario
3. **Combina variables** para comandos más expresivos
4. **Documenta variables personalizadas** para referencia
5. **Aprovecha variables predefinidas** cuando sea posible

## Proceso de Uso Profesional de Variables

### Paso 1: Variables de Usuario (Esenciales)

**⚠️ REGLA CRÍTICA: Estas variables son las MÁS USADAS - memorízalas primero:**

#### Usar "me" como Assignee

**Problema:** Referencias largas a usuarios ralentizan comandos.

**Solución:** La palabra `"me"` se refiere automáticamente a tu usuario actual:

```bash
@linear list issues --assignee "me"
@linear create issue "Título" --assignee "me"
@linear update issue ISSUE_ID --assignee "me"
```

**Uso profesional:**
- Usa `"me"` constantemente para auto-asignación
- Simplifica comandos significativamente
- Funciona en todos los comandos de Linear

#### Referencias Especiales

**Variables disponibles:**
- `"me"` - Tu usuario actual (la más usada)
- `"usuario@email.com"` - Usuario específico por email
- `"Nombre Usuario"` - Usuario por nombre

**Uso profesional:**
- `"me"` es la variable más útil - úsala constantemente
- Usa email o nombre cuando necesites referenciar otros usuarios
- Documenta referencias especiales para referencia

### Paso 2: Fechas Relativas (Muy Útiles)

**⚠️ REGLA CRÍTICA: Las fechas relativas son más útiles que fechas absolutas:**

#### Formatos ISO 8601

**Problema:** Fechas absolutas requieren actualización constante.

**Solución:** Usa duraciones ISO 8601 para fechas relativas:

- `-P1D` - Último día (Past 1 Day)
- `-P7D` - Última semana (Past 7 Days)
- `-P30D` - Último mes (Past 30 Days)
- `-P1W` - Última semana (Past 1 Week)
- `-P1M` - Último mes (Past 1 Month)

**Ejemplos de uso:**
```bash
@linear list issues --created-after "-P1D"
@linear list issues --created-after "-P7D"
@linear list issues --updated-after "-P30D"
```

**Uso profesional:**
- Las fechas relativas se adaptan automáticamente
- No requieren actualización constante
- Son más expresivas que fechas absolutas

#### Fechas Absolutas

**Cuándo usar:** Para fechas específicas o rangos históricos:

```bash
@linear list issues --created-after "2025-01-01"
@linear list issues --due-before "2025-12-31"
```

**Formato:** `YYYY-MM-DD`

**Uso profesional:**
- Usa fechas absolutas para rangos históricos específicos
- Usa fechas relativas para rangos dinámicos
- Combina ambos según necesidades

### Paso 3: Prioridades (Importantes)

**⚠️ REGLA CRÍTICA: Las prioridades correctas mejoran la gestión de trabajo:**

#### Valores de Prioridad

**Variables disponibles:**
- `Urgent` - Urgente (solo bugs críticos que bloquean producción)
- `High` - Alta (features importantes o bugs significativos)
- `Normal` - Normal (por defecto, trabajo regular)
- `Low` - Baja (mejoras menores)

**Ejemplos:**
```bash
@linear create issue "Título" --priority "Urgent"
@linear update issue ISSUE_ID --priority "High"
@linear list issues --priority "High"
```

**Uso profesional:**
- Usa prioridades apropiadamente
- No marques todo como Urgent
- Revisa prioridades regularmente

### Paso 4: Estados (Fundamentales)

**⚠️ REGLA CRÍTICA: Los estados correctos permiten tracking preciso:**

#### Estados Comunes

**Variables disponibles:**
- `Backlog` - Pendiente
- `Todo` - Por hacer
- `In Progress` - En progreso
- `In Review` - En revisión
- `Done` - Completado
- `Canceled` - Cancelado

**Ejemplos:**
```bash
@linear create issue "Título" --state "Todo"
@linear update issue ISSUE_ID --state "In Progress"
@linear list issues --state "Done"
```

**Uso profesional:**
- Actualiza estados inmediatamente al cambiar
- Usa estados consistentemente según tu flujo
- Consulta [Completar Issues](../../../.cursor/commands/complete-issues.md) para proceso completo

### Paso 5: Labels (Organización)

**⚠️ REGLA CRÍTICA: Los labels consistentes mejoran organización y búsqueda:**

#### Uso de Labels

**Problema:** Labels inconsistentes dificultan búsqueda y filtrado.

**Solución:** Separa múltiples labels con comas:

```bash
@linear create issue "Título" --labels "bug,frontend,urgent"
@linear update issue ISSUE_ID --labels "bug,hotfix"
@linear list issues --label "bug"
```

#### Labels Comunes

**Convenciones recomendadas:**
- **Tipos**: `bug`, `feature`, `refactor`, `docs`, `chore`
- **Áreas**: `frontend`, `backend`, `api`, `database`
- **Severidad**: `urgent`, `high-priority`, `low-priority`

**Uso profesional:**
- Establece convenciones de labels al inicio del proyecto
- Usa máximo 5 labels por issue
- Combina tipos con áreas para mejor organización

### Paso 6: Parámetros de Búsqueda (Avanzados)

**⚠️ REGLA CRÍTICA: Los parámetros de búsqueda permiten filtrado preciso:**

#### Ordenamiento

**Variables disponibles:**
- `createdAt` - Ordenar por fecha de creación
- `updatedAt` - Ordenar por fecha de actualización

**Ejemplos:**
```bash
@linear list issues --order-by "createdAt"
@linear list issues --order-by "updatedAt"
```

**Uso profesional:**
- Usa `updatedAt` para ver issues más recientes
- Usa `createdAt` para ver issues más antiguos
- Combina con otros filtros para búsquedas precisas

#### Límites

**Problema:** Listas muy largas dificultan revisión.

**Solución:** Usa límites para controlar resultados:

```bash
@linear list issues --limit 50
```

**Por defecto:** 50, **Máximo:** 250

**Uso profesional:**
- Usa límites apropiados según necesidades
- Aumenta límite solo cuando sea necesario
- Combina con filtros para resultados más precisos

### Paso 7: Scope para Issues Recurrentes (Especiales)

**⚠️ REGLA CRÍTICA: El scope correcto es crucial para issues recurrentes:**

#### Opciones de Scope

**Variables disponibles:**
- `thisEventOnly` - Solo este evento
- `thisAndFollowing` - Este y siguientes
- `all` - Todos los eventos

**Ejemplos:**
```bash
@linear update issue ISSUE_ID --state "Done" --scope "thisEventOnly"
@linear update issue ISSUE_ID --scope "thisAndFollowing"
```

**Uso profesional:**
- Usa `thisEventOnly` para actualizar solo un evento específico
- Usa `thisAndFollowing` para actualizar desde un evento en adelante
- Usa `all` con precaución - afecta todos los eventos

## Integración con Comandos FUNCIONALES

**⚠️ IMPORTANTE: Estas variables funcionan perfectamente con los comandos FUNCIONALES de Linear:**

**Referencias a comandos FUNCIONALES:**
- [Crear Issues](../../../.cursor/commands/create-issues.md) - Usa estas variables al crear issues
- [Completar Issues](../../../.cursor/commands/complete-issues.md) - Aplica estas variables al completar issues
- [Revisar Issues](../../../.cursor/commands/review-issues.md) - Usa estas variables al revisar issues
- [Listar y Buscar](../../../.cursor/commands/list-search.md) - Aprovecha estas variables para búsquedas avanzadas

**Cuándo usar cada uno:**
- **Variables (este documento)**: Para simplificar y acelerar comandos
- **Comandos FUNCIONALES**: Para procesos completos y trabajo profesional

## Flujos de Trabajo con Variables

### Flujo 1: Listar Mis Issues Recientes

```bash
@linear list issues --assignee "me" --created-after "-P7D" --state "In Progress"
```

**Variables usadas:**
- `"me"` - Mis issues
- `-P7D` - Última semana
- `"In Progress"` - Estado

### Flujo 2: Crear Issue Urgente

```bash
@linear create issue "bug: Critical error" --assignee "me" --priority "Urgent" --labels "bug,critical"
```

**Variables usadas:**
- `"me"` - Auto-asignar
- `"Urgent"` - Prioridad
- `"bug,critical"` - Labels

### Flujo 3: Actualizar Issue a Revisión

```bash
@linear update issue ISSUE_ID --state "In Review" --assignee "me"
```

**Variables usadas:**
- `"In Review"` - Estado
- `"me"` - Reasignar

## Checklist de Profesionalismo

### ⚠️ Al Usar Variables

- [ ] ¿Estoy usando `"me"` para auto-asignación cuando es apropiado?
- [ ] ¿Estoy usando fechas relativas (`-P1D`) en lugar de fechas absolutas cuando es posible?
- [ ] ¿Estoy usando prioridades apropiadamente?
- [ ] ¿Estoy usando estados consistentemente?
- [ ] ¿Estoy usando labels según convenciones del proyecto?

### Antes de Crear Issue

- [ ] ¿Estoy usando `"me"` para auto-asignación?
- [ ] ¿Estoy usando prioridad apropiada?
- [ ] ¿Estoy usando labels según convenciones?
- [ ] ¿Estoy usando estado inicial apropiado?

## Consejos Finales

1. **⚠️ Memoriza primero las esenciales** - `"me"`, `-P1D`, estados y prioridades son las más usadas
2. **Usa fechas relativas** - Son más útiles que fechas absolutas
3. **Combina variables** - Los comandos más expresivos combinan múltiples variables
4. **Sigue convenciones** - Usa labels y prioridades según convenciones del proyecto
5. **Documenta personalizaciones** - Guarda variables personalizadas para referencia
6. **Integra con comandos FUNCIONALES** - Para procesos completos y trabajo profesional

---
_Hecho por Cursor_
