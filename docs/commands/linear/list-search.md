# Comandos para Listar y Buscar Issues

Referencia rápida de comandos para listar y buscar issues en Linear desde Cursor.

## Listar Issues

### Listar Todos los Issues

```
@linear list issues
```

### Listar Issues Asignados a Mí

```
@linear list issues --assignee "me"
```

### Listar Issues de un Equipo

```
@linear list issues --team "Engineering"
```

### Listar Issues por Estado

```
@linear list issues --state "In Progress"
```

### Listar Issues por Prioridad

```
@linear list issues --priority "Urgent"
```

### Listar Issues de un Proyecto

```
@linear list issues --project "Nombre del proyecto"
```

### Listar Issues con Labels

```
@linear list issues --label "bug"
```

## Buscar Issues

### Búsqueda por Texto

```
@linear search issues "autenticación"
```

Busca en título y descripción.

### Búsqueda con Filtros

```
@linear search issues "bug" --team "Engineering" --state "Open"
```

### Búsqueda por Creador

```
@linear list issues --created-by "usuario@email.com"
```

### Búsqueda por Fechas

```
@linear list issues --created-after "2025-01-01"
@linear list issues --updated-after "2025-01-01"
```

Usa formato ISO: `YYYY-MM-DD` o duraciones como `-P7D` (últimos 7 días).

## Obtener Issue Específico

```
@linear get issue ISSUE_ID
```

Ejemplo: `@linear get issue PROJ-123`

## Listar Teams

```
@linear list teams
```

## Listar Proyectos

```
@linear list projects
```

## Listar Estados Disponibles

```
@linear list statuses --team "Engineering"
```

## Listar Labels

```
@linear list labels
```

O por equipo:

```
@linear list labels --team "Engineering"
```

## Usando MCP Functions

Desde un chat, puedes hacer consultas complejas:

```
Muéstrame todos los issues urgentes asignados a mí que están en progreso
```

El agente usará `list_issues` con los filtros apropiados.

## Ejemplos de Consultas Útiles

### Issues Pendientes de Revisión

```
@linear list issues --state "In Review" --assignee "me"
```

### Issues Vencidos

```
@linear list issues --assignee "me" --due-before "2025-01-01"
```

### Issues Creados Hoy

```
@linear list issues --created-after "-P1D"
```

### Issues Actualizados Recientemente

```
@linear list issues --updated-after "-P7D" --order-by "updatedAt"
```

## Combinando Filtros

Puedes combinar múltiples filtros:

```
@linear list issues \
  --team "Engineering" \
  --state "In Progress" \
  --assignee "me" \
  --priority "High"
```

## Ordenamiento

```
@linear list issues --order-by "createdAt"
@linear list issues --order-by "updatedAt"
```

## Límites

```
@linear list issues --limit 50
```

Por defecto muestra 50, máximo 250.

## Consejos

- Usa `"me"` como assignee para filtrar por tus issues
- Las fechas pueden usar formato ISO o duraciones ISO 8601
- Los nombres de equipos y estados son case-sensitive
- Combina múltiples filtros para consultas precisas
- Usa búsqueda de texto para encontrar issues por contenido

