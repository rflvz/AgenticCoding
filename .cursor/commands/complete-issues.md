# Comandos para Completar Issues

Referencia rápida de comandos para completar y actualizar issues en Linear desde Cursor.

## Completar Issue (Cambiar Estado)

```
@linear update issue ISSUE_ID --state "Done"
```

## Cambiar Estado a "In Progress"

```
@linear update issue ISSUE_ID --state "In Progress"
```

## Actualizar Descripción

```
@linear update issue ISSUE_ID --description "Nueva descripción actualizada"
```

## Añadir Comentario

```
@linear create comment ISSUE_ID "Texto del comentario"
```

## Actualizar Asignado

```
@linear update issue ISSUE_ID --assignee "nuevo@email.com"
```

## Actualizar Prioridad

```
@linear update issue ISSUE_ID --priority "Urgent"
```

## Añadir Labels

```
@linear update issue ISSUE_ID --labels "bug,hotfix"
```

## Actualizar Múltiples Campos

```
@linear update issue ISSUE_ID \
  --state "Done" \
  --description "Completado: implementación terminada" \
  --priority "Low"
```

## Completar y Añadir Comentario

```
@linear update issue ISSUE_ID --state "Done"
@linear create comment ISSUE_ID "Issue completado con éxito"
```

## Usando MCP Functions

Desde un chat, puedes solicitar actualizaciones directamente:

```
Completa el issue ISSUE-123 y añade un comentario indicando que está listo para QA
```

El agente usará automáticamente:
- `mcp_Linear_update_issue` para cambiar el estado
- `mcp_Linear_create_comment` para añadir el comentario

## Actualizar Issue Recurrente

Para issues recurrentes, especifica el scope:

```
@linear update issue ISSUE_ID --state "Done" --scope "thisEventOnly"
```

Opciones de scope:
- `thisEventOnly` - Solo este evento
- `thisAndFollowing` - Este y siguientes
- `all` - Todos los eventos

## Buscar y Completar

```
@linear search issues "mi busqueda" --update-state "Done"
```

## Ejemplos de Flujo de Trabajo

### Completar Issue con Resumen

```
1. @linear update issue ISSUE_ID --state "Done"
2. @linear create comment ISSUE_ID "Completado: [resumen de cambios]"
```

### Marcar como En Revisión

```
@linear update issue ISSUE_ID --state "In Review" --assignee "reviewer@email.com"
```

## Consejos

- Usa IDs completos de issues (ej: `PROJ-123`)
- Los estados deben existir en tu workspace de Linear
- Puedes combinar múltiples actualizaciones en una sola solicitud al agente
- Usa comentarios para documentar cambios importantes

