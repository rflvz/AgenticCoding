# Variables Útiles

Variables y parámetros especiales para usar en comandos de Linear y agentización.

## Variables de Usuario

### Usar "me" como Assignee

La palabra `"me"` se refiere automáticamente a tu usuario actual:

```
@linear list issues --assignee "me"
@linear create issue "Título" --assignee "me"
@linear update issue ISSUE_ID --assignee "me"
```

### Referencias Especiales

- `"me"` - Tu usuario actual
- `"usuario@email.com"` - Usuario específico por email
- `"Nombre Usuario"` - Usuario por nombre

## Fechas Relativas

### Formatos ISO 8601

Usa duraciones ISO 8601 para fechas relativas:

- `-P1D` - Último día (Past 1 Day)
- `-P7D` - Última semana (Past 7 Days)
- `-P30D` - Último mes (Past 30 Days)
- `-P1W` - Última semana (Past 1 Week)
- `-P1M` - Último mes (Past 1 Month)

### Ejemplos de Uso

```
@linear list issues --created-after "-P1D"
@linear list issues --created-after "-P7D"
@linear list issues --updated-after "-P30D"
```

### Fechas Absolutas

También puedes usar fechas absolutas:

```
@linear list issues --created-after "2025-01-01"
@linear list issues --due-before "2025-12-31"
```

Formato: `YYYY-MM-DD`

## Prioridades

### Valores de Prioridad

- `Urgent` - Urgente
- `High` - Alta
- `Normal` - Normal (por defecto)
- `Low` - Baja

### Ejemplos

```
@linear create issue "Título" --priority "Urgent"
@linear update issue ISSUE_ID --priority "High"
@linear list issues --priority "High"
```

## Estados

### Estados Comunes

- `Backlog` - Pendiente
- `Todo` - Por hacer
- `In Progress` - En progreso
- `In Review` - En revisión
- `Done` - Completado
- `Canceled` - Cancelado

### Ejemplos

```
@linear create issue "Título" --state "Todo"
@linear update issue ISSUE_ID --state "In Progress"
@linear list issues --state "Done"
```

## Labels

### Uso de Labels

Separa múltiples labels con comas:

```
@linear create issue "Título" --labels "bug,frontend,urgent"
@linear update issue ISSUE_ID --labels "bug,hotfix"
@linear list issues --label "bug"
```

### Labels Comunes

- **Tipos**: `bug`, `feature`, `refactor`, `docs`, `chore`
- **Áreas**: `frontend`, `backend`, `api`, `database`
- **Severidad**: `urgent`, `high-priority`, `low-priority`

## Parámetros de Búsqueda

### Ordenamiento

```
@linear list issues --order-by "createdAt"
@linear list issues --order-by "updatedAt"
```

### Límites

```
@linear list issues --limit 50
```

Por defecto: 50, Máximo: 250

## Scope para Issues Recurrentes

### Opciones de Scope

- `thisEventOnly` - Solo este evento
- `thisAndFollowing` - Este y siguientes
- `all` - Todos los eventos

### Ejemplos

```
@linear update issue ISSUE_ID --state "Done" --scope "thisEventOnly"
@linear update issue ISSUE_ID --scope "thisAndFollowing"
```

## Consejos

- Usa `"me"` para filtrar por tus issues automáticamente
- Las fechas relativas (`-P1D`) son más útiles que fechas absolutas
- Combina múltiples labels para filtros precisos
- Usa estados apropiados según tu flujo de trabajo

