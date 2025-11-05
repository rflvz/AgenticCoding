# Comandos de Flujos de Trabajo de Agentes

Flujos de trabajo que combinan agentización con comandos de Linear para automatizar procesos completos.

## Flujos de Trabajo Básicos

### Workflow: Crear Issue desde Error

```
Workflow: Crear Issue desde Error

1. Analiza el error proporcionado
2. Identifica la causa raíz
3. Crea issue en Linear:
   @linear create issue "bug: [descripción del error]" \
     --team "Engineering" \
     --description "[análisis técnico completo]" \
     --priority "[según severidad]" \
     --labels "bug,[área afectada]"
4. Añade stack trace si está disponible
5. Incluye pasos para reproducir
```

### Workflow: Completar Issue con Commit

```
Workflow: Completar Issue desde Commit

1. Analiza el commit proporcionado
2. Identifica issues relacionados
3. Actualiza issue en Linear:
   @linear update issue ISSUE_ID \
     --state "Done" \
     --description "[descripción actualizada con cambios]"
4. Añade comentario:
   @linear create comment ISSUE_ID \
     "Completado en commit [hash]. Cambios: [resumen]"
5. Incluye referencias al código modificado
```

### Workflow: Revisar Código y Crear Issues

```
Workflow: Revisar y Crear Issues

1. Revisa el código proporcionado
2. Identifica problemas (bugs, vulnerabilidades, mejoras)
3. Para cada problema:
   @linear create issue "bug: [problema]" \
     --team "Engineering" \
     --description "[ubicación, descripción técnica, impacto]" \
     --priority "[según severidad]" \
     --labels "bug,[área],[severidad]"
4. Proporciona resumen de issues creados
```

## Flujos de Trabajo Avanzados

### Workflow: Dividir Feature en Issues

```
Workflow: Dividir Feature

1. Analiza la feature propuesta
2. Crea issue padre (Epic):
   @linear create issue "feature: [nombre]" \
     --team "Engineering" \
     --description "[visión general, requisitos]"
3. Divide en issues más pequeños:
   - Diseño: @linear create issue "docs: Diseño de [feature]"
   - Backend: @linear create issue "feature: Backend - [componente]"
   - Frontend: @linear create issue "feature: Frontend - [componente]"
   - Tests: @linear create issue "chore: Tests para [feature]"
4. Establece dependencias en descripciones
5. Prioriza según importancia
```

### Workflow: Actualizar Estado de Proyecto

```
Workflow: Actualizar Estado de Proyecto

1. Busca todos los issues del proyecto:
   @linear list issues --project "[nombre del proyecto]"
2. Analiza estados de issues hijos
3. Actualiza issue padre según progreso:
   @linear update issue PARENT_ID \
     --description "[estado actualizado con progreso]"
4. Identifica issues bloqueados
5. Sugiere próximos pasos
```

### Workflow: Generar Reporte de Sprint

```
Workflow: Reporte de Sprint

1. Lista issues del sprint:
   @linear list issues --team "[equipo]" --created-after "[fecha inicio]"
2. Analiza:
   - Issues completados
   - Issues en progreso
   - Issues bloqueados
   - Velocidad del equipo
3. Genera reporte con:
   - Resumen ejecutivo
   - Lista de issues por estado
   - Identificación de bloqueos
   - Sugerencias para próximo sprint
```

## Flujos de Trabajo Combinados

### Workflow: Desarrollo Completo

```
Workflow: Desarrollo Completo

1. Contextualizar agente como Developer
2. Buscar issues asignados:
   @linear list issues --assignee "me" --state "Todo"
3. Para cada issue:
   a. Actualizar a "In Progress":
      @linear update issue ISSUE_ID --state "In Progress"
   b. Desarrollar código
   c. Revisar código
   d. Si hay bugs, crear issues:
      @linear create issue "bug: [descripción]"
   e. Completar issue:
      @linear update issue ISSUE_ID --state "Done"
      @linear create comment ISSUE_ID "Completado: [resumen]"
4. Generar reporte de progreso
```

### Workflow: Revisión de Código Completa

```
Workflow: Revisión Completa

1. Contextualizar agente como Code Reviewer
2. Revisar código proporcionado
3. Para cada problema encontrado:
   a. Crear issue:
      @linear create issue "bug: [problema]" \
        --priority "[según severidad]"
   b. Añadir comentario con sugerencias
4. Buscar issues similares:
   @linear search issues "[término relacionado]"
5. Agrupar issues relacionados si aplica
6. Generar resumen de revisión
```

### Workflow: Project Management Completo

```
Workflow: PM Completo

1. Contextualizar agente como Project Manager
2. Generar reporte del proyecto:
   @linear list issues --project "[proyecto]"
3. Analizar:
   - Progreso general
   - Dependencias
   - Bloqueos
   - Velocidad
4. Actualizar issues según necesidad:
   @linear update issue ISSUE_ID --priority "[nueva prioridad]"
5. Reasignar tareas si es necesario:
   @linear update issue ISSUE_ID --assignee "[nuevo asignado]"
6. Generar reporte ejecutivo
```

## Flujos de Trabajo Especializados

### Workflow: Fix de Bug Crítico

```
Workflow: Bug Crítico

1. Crear issue urgente:
   @linear create issue "bug: [descripción]" \
     --priority "Urgent" \
     --labels "bug,critical,hotfix"
2. Asignar a desarrollador:
   @linear update issue ISSUE_ID --assignee "[dev]"
3. Monitorear progreso:
   @linear get issue ISSUE_ID
4. Cuando se complete:
   @linear update issue ISSUE_ID --state "Done"
   @linear create comment ISSUE_ID "Fix aplicado en [commit]"
5. Verificar fix
6. Cerrar issue
```

### Workflow: Feature Request Completo

```
Workflow: Feature Request

1. Analizar requisitos
2. Crear issue de diseño:
   @linear create issue "docs: Diseño de [feature]" \
     --team "[equipo]" \
     --labels "feature,design"
3. Dividir en issues de implementación
4. Crear issues hijos:
   @linear create issue "feature: [componente]" \
     --project "[feature]"
5. Establecer dependencias
6. Asignar tareas
7. Monitorear progreso
```

## Ejemplos de Uso

### Ejecutar Workflow de Revisión

```
Ejecuta workflow: Revisar Código y Crear Issues

Código a revisar:
[archivo.js]

El agente ejecuta:
1. Revisa el código
2. Identifica problemas
3. Crea issues para cada problema
4. Proporciona resumen
```

### Ejecutar Workflow de Desarrollo

```
Ejecuta workflow: Desarrollo Completo

Issues a trabajar:
- ISSUE-123: Implementar autenticación
- ISSUE-124: Crear UI de login

El agente ejecuta:
1. Actualiza issues a "In Progress"
2. Trabaja en los issues
3. Crea issues para bugs encontrados
4. Completa issues cuando termina
5. Genera reporte
```

### Ejecutar Workflow de PM

```
Ejecuta workflow: Project Management Completo

Proyecto: "Sistema de Autenticación"
Equipo: "Engineering"

El agente ejecuta:
1. Genera reporte del proyecto
2. Analiza progreso
3. Identifica bloqueos
4. Sugiere ajustes
5. Actualiza issues según necesidad
```

## Consejos

- Combina workflows para procesos complejos
- Personaliza workflows según necesidades del proyecto
- Usa workflows para automatizar tareas repetitivas
- Integra workflows con comandos de Linear
- Documenta workflows personalizados para reutilización

