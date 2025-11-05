# Comandos para Crear Issues

Referencia rápida de comandos para crear issues en Linear desde Cursor.

## Crear Issue Básico

```
@linear create issue "Título del issue" --team "Nombre del equipo"
```

## Crear Issue con Descripción

```
@linear create issue "Título" --description "Descripción detallada" --team "Equipo"
```

## Crear Issue con Asignado

```
@linear create issue "Título" --team "Equipo" --assignee "usuario@email.com"
```

## Crear Issue con Prioridad

```
@linear create issue "Título" --team "Equipo" --priority "Urgent"
```

Opciones de prioridad: `Urgent`, `High`, `Normal`, `Low`

## Crear Issue con Estado

```
@linear create issue "Título" --team "Equipo" --state "In Progress"
```

## Crear Issue con Labels

```
@linear create issue "Título" --team "Equipo" --labels "bug,frontend"
```

## Crear Issue con Proyecto

```
@linear create issue "Título" --team "Equipo" --project "Nombre del proyecto"
```

## Crear Issue con Fecha de Vencimiento

```
@linear create issue "Título" --team "Equipo" --due-date "2025-12-31"
```

## Crear Issue Completo

```
@linear create issue "Implementar autenticación" \
  --team "Engineering" \
  --description "Implementar sistema de autenticación OAuth2" \
  --assignee "dev@example.com" \
  --priority "High" \
  --labels "backend,security" \
  --project "Auth System" \
  --due-date "2025-12-15"
```

## Usando MCP Functions

Desde un chat, puedes usar las funciones MCP directamente:

```
Crear un issue en Linear con título "Corregir bug" en el equipo "Engineering"
```

El agente usará automáticamente `mcp_Linear_create_issue` con los parámetros correctos.

## Ejemplos de Uso en Prompts

### Para Agentes Especializados

```
Cuando necesites crear un issue, usa:
- Título claro y descriptivo
- Descripción con contexto técnico
- Asigna al equipo correcto
- Añade labels relevantes
```

## Consejos

- Usa nombres de equipo exactos (case-sensitive)
- Los labels deben existir previamente en Linear
- El formato de fecha es `YYYY-MM-DD`
- Puedes usar `"me"` como assignee para asignarte a ti mismo

