# Comandos de Agente Orquestador

Comandos para crear y gestionar un agente orquestador especializado en project management que coordina issues y tareas en Linear.

## Crear Agente Orquestador

### Configuración Básica

```
Crea un agente orquestador de project management que:
- Gestione el flujo de trabajo del equipo
- Coordine issues en Linear
- Asigne tareas según prioridades
- Genere reportes de progreso
- Monitoree dependencias entre issues
```

### Configuración Completa

```
Eres un agente orquestador de project management. Tu función es:

## Gestión de Proyectos

1. **Planificación**
   - Dividir features grandes en issues manejables
   - Establecer dependencias entre issues
   - Priorizar tareas según objetivos del proyecto
   - Asignar issues al equipo y personas apropiadas

2. **Coordinación**
   - Monitorear el estado de todos los issues
   - Identificar bloqueos y dependencias
   - Reasignar tareas cuando sea necesario
   - Coordinar entre diferentes equipos

3. **Reportes**
   - Generar reportes de progreso regularmente
   - Identificar issues bloqueados o atrasados
   - Analizar velocidad del equipo
   - Sugerir ajustes en priorización

## Comandos Disponibles

- @linear create issue - Crear nuevos issues
- @linear list issues - Listar issues con filtros
- @linear update issue - Actualizar issues
- @linear search issues - Buscar issues
- @linear create comment - Añadir comentarios

## Reglas de Orquestación

1. **División de Features**
   - Divide features grandes en issues de 1-3 días
   - Crea issue padre (Epic) para features complejas
   - Establece dependencias claras entre issues

2. **Priorización**
   - Urgent: Bugs críticos, bloqueadores
   - High: Features importantes, bugs significativos
   - Normal: Trabajo regular
   - Low: Mejoras, optimizaciones

3. **Asignación**
   - Asigna según habilidades del equipo
   - Considera carga de trabajo actual
   - Distribuye tareas equitativamente

4. **Monitoreo**
   - Revisa issues diariamente
   - Identifica bloqueos temprano
   - Sugiere ajustes cuando sea necesario
```

## Comandos de Orquestación

### Dividir Feature en Issues

```
@orchestrator divide feature "Sistema de autenticación" en issues manejables
```

El agente:
1. Crea issue padre (Epic)
2. Divide en issues más pequeños:
   - Diseño arquitectónico
   - Backend API
   - Frontend UI
   - Tests
   - Documentación
3. Establece dependencias entre issues
4. Asigna prioridades

### Generar Reporte de Proyecto

```
@orchestrator generate report --team "Engineering" --period "last-week"
```

El agente:
1. Lista issues completados
2. Identifica issues en progreso
3. Encuentra issues bloqueados
4. Calcula velocidad del equipo
5. Sugiere próximos pasos

### Reasignar Tareas

```
@orchestrator rebalance workload --team "Engineering"
```

El agente:
1. Analiza carga de trabajo actual
2. Identifica desbalances
3. Sugiere reasignaciones
4. Actualiza issues según sea necesario

### Monitorear Dependencias

```
@orchestrator check dependencies --project "Feature X"
```

El agente:
1. Lista todos los issues del proyecto
2. Identifica dependencias
3. Detecta bloqueos
4. Sugiere orden de ejecución

## Flujos de Trabajo Combinados

### Crear Feature Completa

```
@orchestrator create feature "Sistema de notificaciones" \
  --team "Engineering" \
  --assignee "dev@example.com" \
  --priority "High" \
  --divide
```

El agente:
1. Crea issue padre (Epic)
2. Divide en issues manejables
3. Establece dependencias
4. Asigna tareas
5. Crea todos los issues en Linear

### Actualizar Estado de Proyecto

```
@orchestrator update project status --project "Feature X"
```

El agente:
1. Busca todos los issues del proyecto
2. Actualiza estado padre según hijos
3. Añade comentarios con progreso
4. Identifica próximos pasos

## Integración con Linear

### Crear Issues desde Orquestador

```
@orchestrator create issues from tasks:
- "Implementar API de autenticación"
- "Crear UI de login"
- "Añadir tests"
--team "Engineering"
```

El agente:
1. Crea issues individuales usando @linear create issue
2. Agrupa en un proyecto
3. Establece dependencias
4. Asigna prioridades

### Actualizar Issues desde Orquestador

```
@orchestrator update issues --project "Feature X" --status "In Review"
```

El agente:
1. Busca todos los issues del proyecto
2. Actualiza estado usando @linear update issue
3. Añade comentarios explicando cambios

## Ejemplos de Uso

### Iniciar Nuevo Proyecto

```
@orchestrator iniciar proyecto "Sistema de autenticación OAuth2":
- Feature: Autenticación OAuth2
- Equipo: Engineering
- Prioridad: High
- Fecha objetivo: 2025-12-31
```

### Revisar Progreso del Sprint

```
@orchestrator revisar sprint actual:
- Lista issues completados
- Identifica bloqueos
- Sugiere ajustes de prioridad
- Genera reporte de progreso
```

### Coordinar Entre Equipos

```
@orchestrator coordinar entre equipos:
- Frontend: Issues de UI listos
- Backend: Issues de API listos
- Integración: Verificar dependencias
```

## Consejos

- Usa el orquestador para features grandes que requieren múltiples issues
- Genera reportes regularmente para mantener visibilidad
- Monitorea dependencias para evitar bloqueos
- Rebalancea carga de trabajo cuando sea necesario
- Combina con comandos de Linear para máxima efectividad

