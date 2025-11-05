# Comandos de Contextualización de Agentes

Comandos para contextualizar agentes (chats) con información específica, compatible con los comandos de Linear.

## Contextualizar Agente con Rol

### Agente Especializado en Linear

```
Contextualiza este agente como experto en Linear:
- Rol: Gestor de issues
- Funciones: Crear, actualizar, buscar issues
- Comandos: @linear create, @linear update, @linear list
- Reglas: Usar títulos descriptivos, añadir contexto técnico
```

### Agente Revisor de Código

```
Contextualiza este agente como revisor de código:
- Rol: Revisor experto
- Funciones: Revisar código, identificar bugs, crear issues
- Comandos: @linear create issue (para bugs encontrados)
- Reglas: Analizar código antes de crear issues, priorizar según severidad
```

### Agente Arquitecto

```
Contextualiza este agente como arquitecto de software:
- Rol: Diseñador de arquitectura
- Funciones: Diseñar sistemas, dividir features, crear issues de arquitectura
- Comandos: @linear create issue (para tareas de diseño)
- Reglas: Dividir features grandes, establecer dependencias
```

## Contextualización con Información del Proyecto

### Añadir Contexto del Proyecto

```
Contextualiza este agente con información del proyecto:
- Proyecto: Sistema de autenticación
- Equipo: Engineering
- Labels estándar: backend, frontend, security
- Prioridad por defecto: Normal
```

Cuando crees issues, usa esta información:
- Asigna al equipo "Engineering"
- Usa los labels especificados
- Prioriza según el contexto del proyecto

### Contextualización con Código

```
Contextualiza este agente con el código del proyecto:
- Archivos relevantes: [lista de archivos]
- Estructura: [descripción de arquitectura]
- Convenciones: [estándares del proyecto]
```

Al crear issues:
- Referencia archivos específicos
- Usa terminología del proyecto
- Sigue las convenciones establecidas

## Contextualización Dinámica

### Cambiar Rol del Agente

```
Cambia el rol de este agente a:
- Nuevo rol: Project Manager
- Nuevas funciones: Coordinar equipo, generar reportes
- Comandos disponibles: @linear list issues, @linear search
```

### Añadir Contexto Temporal

```
Añade contexto temporal:
- Sprint actual: Sprint 5
- Fecha objetivo: 2025-12-31
- Prioridad del sprint: High
```

Al crear issues:
- Considera la fecha objetivo
- Prioriza según el sprint
- Añade información de sprint en descripciones

## Contextualización con Reglas Específicas

### Reglas de Creación de Issues

```
Define reglas para crear issues:
1. Título: Formato "[Type]: [Descripción]"
2. Descripción: Incluir contexto técnico, pasos para reproducir
3. Asignación: Equipo "Engineering" por defecto
4. Labels: Usar "bug", "feature", "refactor" según tipo
5. Prioridad: Evaluar según severidad del problema
```

### Reglas de Actualización de Issues

```
Define reglas para actualizar issues:
1. Añadir comentarios explicando cambios
2. Actualizar estado según flujo de trabajo
3. Incluir referencias a commits cuando actualices desde código
4. Documentar decisiones importantes
```

## Integración con Comandos de Linear

### Crear Issue con Contexto

```
Crea un issue en Linear usando el contexto del agente:
- Título: "bug: Error en autenticación"
- Descripción: [El agente usa el contexto del proyecto para añadir detalles]
- Equipo: [Usa el equipo del contexto]
- Labels: [Usa los labels estándar del contexto]
```

### Actualizar Issues con Contexto

```
Actualiza el issue ISSUE-123 usando el contexto del agente:
- Estado: "Done"
- Comentario: [El agente añade comentario usando terminología del proyecto]
```

## Contextualización Combinada

### Agente Multi-Rol

```
Contextualiza este agente con múltiples roles:
- Rol principal: Revisor de código
- Rol secundario: Gestor de issues
- Contexto del proyecto: Sistema de autenticación
- Reglas: Priorizar bugs de seguridad, usar labels estándar
```

Funciones combinadas:
- Revisar código y crear issues automáticamente
- Gestionar issues existentes
- Usar contexto del proyecto en todas las operaciones

### Agente con Workflow Completo

```
Contextualiza este agente con workflow completo:
1. Revisar código
2. Identificar problemas
3. Crear issues en Linear (@linear create issue)
4. Monitorear progreso (@linear list issues)
5. Actualizar estados (@linear update issue)
6. Generar reportes
```

## Ejemplos de Uso

### Configurar Agente para Nuevo Proyecto

```
Contextualiza este agente para el proyecto "E-commerce Platform":
- Equipo: "Engineering"
- Labels: "backend", "frontend", "api", "database"
- Prioridad por defecto: "Normal"
- Formato de títulos: "[Type]: [Descripción]"
- Comandos: Todos los comandos de @linear
```

### Añadir Contexto de Sprint

```
Añade contexto del sprint actual:
- Sprint: 5
- Objetivos: Completar autenticación, mejorar performance
- Prioridad: Alta para features de autenticación
- Fecha fin: 2025-12-15
```

Al crear issues:
- Prioriza issues de autenticación como "High"
- Añade información de sprint en descripciones
- Considera fecha fin del sprint

### Contextualizar para Revisión de Código

```
Contextualiza este agente para revisión de código:
- Buscar: Bugs, vulnerabilidades, malas prácticas
- Crear issues: Para cada problema encontrado
- Prioridad: Urgent para bugs críticos, High para bugs regulares
- Labels: "bug", "security", "refactor" según tipo
```

## Consejos

- Contextualiza antes de empezar a trabajar
- Añade contexto del proyecto para mejor precisión
- Combina roles cuando sea necesario
- Actualiza contexto según necesidades
- Usa contexto con comandos de Linear para máxima efectividad

