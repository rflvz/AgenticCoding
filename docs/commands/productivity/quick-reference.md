# Referencia Rápida

Comandos rápidos y referencias esenciales para trabajar con Linear y agentización.

## Comandos Rápidos de Linear

### Crear Issue

```
@linear create issue "Título" --team "Equipo"
```

### Listar Issues

```
@linear list issues --assignee "me"
```

### Buscar Issues

```
@linear search issues "término"
```

### Actualizar Issue

```
@linear update issue ISSUE_ID --state "Done"
```

### Añadir Comentario

```
@linear create comment ISSUE_ID "Texto"
```

## Aliases Mentales Útiles

### Issues Míos

```
@linear list issues --assignee "me"
```

### Issues Urgentes

```
@linear list issues --priority "Urgent"
```

### Issues de Hoy

```
@linear list issues --created-after "-P1D"
```

### Issues en Progreso

```
@linear list issues --state "In Progress" --assignee "me"
```

## Comandos de Agentes Rápidos

### Contextualizar Agente

```
Contextualiza este agente como [rol]: [descripción]
```

### Activar Rol

```
Activa rol: [Nombre del Rol]
```

### Ejecutar Workflow

```
Ejecuta workflow: [Nombre del Workflow]
```

## Referencias de Comandos

### Linear

- **Crear**: `@linear create issue "Título" --team "Equipo"`
- **Listar**: `@linear list issues --assignee "me"`
- **Buscar**: `@linear search issues "término"`
- **Actualizar**: `@linear update issue ID --state "Done"`
- **Comentar**: `@linear create comment ID "Texto"`

### Agentes

- **Orquestador**: `@orchestrator [comando]`
- **Contexto**: `Contextualiza este agente: [descripción]`
- **Rol**: `Activa rol: [nombre]`
- **Workflow**: `Ejecuta workflow: [nombre]`

## Combinaciones Útiles

### Comandos Encadenados

```
@linear get issue ISSUE-123
@linear update issue ISSUE-123 --state "In Progress"
@linear create comment ISSUE-123 "Empezando"
```

### Múltiples Comandos en Uno

```
Lista mis issues en progreso y crea un issue nuevo para la tarea X
```

## Variables Especiales

- `"me"` - Referencia a tu usuario
- `-P1D` - Último día
- `-P7D` - Última semana
- `-P30D` - Último mes

