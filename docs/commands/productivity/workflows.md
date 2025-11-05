# Flujos de Trabajo Rápidos

Flujos de trabajo comunes y rápidos para tareas frecuentes.

## Flujos de Trabajo Básicos

### Crear Issue desde Error

```
1. Analiza el error proporcionado
2. Identifica la causa raíz
3. Crea issue en Linear:
   @linear create issue "bug: [descripción del error]" \
     --team "Engineering" \
     --labels "bug" \
     --priority "High" \
     --description "[análisis técnico completo]"
```

### Completar Issue Actual

```
1. Actualiza estado:
   @linear update issue ISSUE_ID --state "Done"
2. Añade comentario:
   @linear create comment ISSUE_ID "Completado: [resumen]"
```

### Revisar Issues Pendientes

```
@linear list issues --assignee "me" --state "In Progress"
```

## Flujos de Trabajo con Agentes

### Crear Issue con Contexto del Agente

```
Crea un issue en Linear con el título "[título]" para el equipo "[equipo]" 
basándote en el error que estamos viendo en el código.
```

El agente:
1. Analiza el código y el error
2. Crea issue con contexto técnico completo
3. Prioriza según severidad
4. Asigna labels apropiados

### Actualizar Issue desde Commit

```
Basándome en este commit, actualiza el issue ISSUE_ID con un comentario 
describiendo los cambios realizados.
```

El agente:
1. Identifica el issue relacionado
2. Actualiza estado si corresponde
3. Añade comentario con hash del commit
4. Incluye resumen de cambios

### Buscar Issues Relacionados

```
Busca issues relacionados con "[término]" y muéstrame los que están abiertos.
```

El agente:
1. Busca issues similares
2. Filtra por estado abierto
3. Proporciona resumen
4. Sugiere actualizar issues existentes si aplica

## Flujos de Trabajo de Desarrollo

### Iniciar Trabajo en Issue

```
1. Obtener issue:
   @linear get issue ISSUE_ID
2. Actualizar estado:
   @linear update issue ISSUE_ID --state "In Progress"
3. Añadir comentario:
   @linear create comment ISSUE_ID "Empezando a trabajar"
```

### Completar Trabajo en Issue

```
1. Actualizar estado:
   @linear update issue ISSUE_ID --state "Done"
2. Añadir comentario:
   @linear create comment ISSUE_ID "Completado: [resumen de cambios]"
3. Incluir referencia a commit si aplica
```

### Crear Issue desde Bug Encontrado

```
1. Analizar el bug
2. Crear issue:
   @linear create issue "bug: [descripción]" \
     --team "Engineering" \
     --priority "[según severidad]" \
     --labels "bug,[área]"
3. Añadir descripción técnica completa
```

## Flujos de Trabajo de Revisión

### Revisar Código y Crear Issues

```
1. Revisar código proporcionado
2. Identificar problemas (bugs, vulnerabilidades, mejoras)
3. Para cada problema, crear issue:
   @linear create issue "bug: [problema]" \
     --description "[ubicación, descripción técnica, impacto]"
4. Priorizar según severidad
```

### Verificar Fix de Bug

```
1. Buscar issue relacionado:
   @linear search issues "[descripción del bug]"
2. Verificar que el fix esté implementado
3. Actualizar issue:
   @linear update issue ISSUE_ID --state "Done"
   @linear create comment ISSUE_ID "Fix verificado en [commit]"
```

## Flujos de Trabajo de Project Management

### Generar Reporte de Sprint

```
1. Listar issues del sprint:
   @linear list issues --team "[equipo]" --created-after "[fecha inicio]"
2. Analizar:
   - Issues completados
   - Issues en progreso
   - Issues bloqueados
3. Generar resumen con sugerencias
```

### Reasignar Tareas

```
1. Analizar carga de trabajo:
   @linear list issues --assignee "[usuario]"
2. Identificar desbalances
3. Reasignar:
   @linear update issue ISSUE_ID --assignee "[nuevo asignado]"
```

## Consejos

- Guarda workflows comunes en `.cursorrules`
- Personaliza workflows según necesidades del proyecto
- Combina workflows para procesos complejos
- Usa agentes para automatizar workflows repetitivos

