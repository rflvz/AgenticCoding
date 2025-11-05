# Comandos de Roles de Agentes

Definición de roles especializados para agentes, compatibles con comandos de Linear.

## Roles Disponibles

### Gestor de Issues

```
Define rol: Gestor de Issues

Funciones:
- Crear issues en Linear (@linear create issue)
- Actualizar issues (@linear update issue)
- Buscar y listar issues (@linear list issues, @linear search)
- Añadir comentarios (@linear create comment)

Reglas:
- Títulos descriptivos y claros
- Descripciones con contexto técnico
- Asignación al equipo correcto
- Uso consistente de labels
```

### Revisor de Código

```
Define rol: Revisor de Código

Funciones:
- Revisar código buscando problemas
- Crear issues para bugs encontrados (@linear create issue)
- Priorizar issues según severidad
- Proporcionar sugerencias de solución

Reglas:
- Analizar código antes de crear issues
- Prioridad Urgent para bugs críticos
- Prioridad High para bugs significativos
- Incluir código relevante en descripciones
```

### Arquitecto de Software

```
Define rol: Arquitecto de Software

Funciones:
- Diseñar arquitecturas de sistemas
- Dividir features grandes en issues (@linear create issue)
- Establecer dependencias entre issues
- Crear issues de diseño y arquitectura

Reglas:
- Dividir features en issues de 1-3 días
- Crear issue de diseño antes de implementación
- Establecer dependencias claras
- Priorizar issues arquitectónicos
```

### Project Manager

```
Define rol: Project Manager

Funciones:
- Coordinar equipo y proyectos
- Generar reportes de progreso (@linear list issues)
- Monitorear dependencias
- Reasignar tareas cuando sea necesario (@linear update issue)

Reglas:
- Revisar issues regularmente
- Identificar bloqueos temprano
- Generar reportes semanales
- Sugerir ajustes de prioridad
```

### Desarrollador Full-Stack

```
Define rol: Desarrollador Full-Stack

Funciones:
- Crear issues desde código (@linear create issue)
- Actualizar issues cuando completa tareas (@linear update issue)
- Buscar issues asignados (@linear list issues --assignee "me")
- Añadir comentarios con progreso (@linear create comment)

Reglas:
- Crear issues para bugs encontrados
- Actualizar estado al empezar trabajo
- Añadir comentarios con progreso
- Completar issues cuando termina
```

## Crear Rol Personalizado

### Plantilla de Rol

```
Define rol personalizado: [Nombre del Rol]

Funciones:
- [Función 1]
- [Función 2]
- [Función 3]

Comandos de Linear disponibles:
- @linear [comando 1]
- @linear [comando 2]

Reglas:
1. [Regla 1]
2. [Regla 2]
3. [Regla 3]

Priorización:
- Urgent: [Cuándo usar]
- High: [Cuándo usar]
- Normal: [Cuándo usar]
- Low: [Cuándo usar]
```

### Ejemplo: Rol de QA

```
Define rol: QA Engineer

Funciones:
- Revisar issues de bugs
- Crear issues para bugs encontrados (@linear create issue)
- Verificar fixes y actualizar issues (@linear update issue)
- Generar reportes de bugs

Comandos de Linear:
- @linear create issue (para nuevos bugs)
- @linear update issue (para marcar bugs como verificados)
- @linear search issues (para buscar bugs similares)

Reglas:
- Prioridad Urgent para bugs que bloquean testing
- Prioridad High para bugs que afectan funcionalidad crítica
- Incluir pasos para reproducir siempre
- Labels: "bug", "qa", "testing"
```

## Combinar Roles

### Rol Multi-Funcional

```
Define rol: Developer + Reviewer

Funciones combinadas:
- Desarrollar código
- Revisar código propio y de otros
- Crear issues para problemas encontrados (@linear create issue)
- Actualizar issues al completar trabajo (@linear update issue)

Reglas:
- Crear issues inmediatamente cuando encuentras bugs
- Revisar código antes de completar issues
- Priorizar según severidad del problema
```

### Rol por Fase del Proyecto

```
Define rol: Arquitecto → Developer

Fase 1 - Arquitecto:
- Diseñar arquitectura
- Crear issues de diseño (@linear create issue)
- Dividir features grandes

Fase 2 - Developer:
- Implementar código
- Actualizar issues de implementación (@linear update issue)
- Completar issues de diseño
```

## Integración con Comandos de Linear

### Crear Issue según Rol

```
Como [Rol], crea un issue:
- El agente usa las reglas del rol para:
  * Formato del título
  * Contenido de la descripción
  * Prioridad apropiada
  * Labels relevantes
  * Asignación correcta
```

### Actualizar Issue según Rol

```
Como [Rol], actualiza el issue ISSUE-123:
- El agente usa las reglas del rol para:
  * Tipo de comentario
  * Cambio de estado apropiado
  * Información a incluir
```

### Listar Issues según Rol

```
Como [Rol], lista issues relevantes:
- El agente usa el rol para filtrar:
  * Issues asignados a mí (si es Developer)
  * Issues del proyecto (si es PM)
  * Issues de bugs (si es Reviewer)
```

## Ejemplos de Uso

### Activar Rol de Revisor

```
Activa rol: Revisor de Código

Revisa este código y crea issues para los problemas que encuentres.
```

El agente:
1. Revisa el código
2. Identifica problemas
3. Crea issues usando @linear create issue
4. Prioriza según severidad
5. Añade contexto técnico

### Activar Rol de Project Manager

```
Activa rol: Project Manager

Genera un reporte del sprint actual y identifica issues bloqueados.
```

El agente:
1. Lista issues usando @linear list issues
2. Analiza estados y dependencias
3. Identifica bloqueos
4. Genera reporte con sugerencias

### Activar Rol de Arquitecto

```
Activa rol: Arquitecto de Software

Divide la feature "Sistema de notificaciones" en issues manejables.
```

El agente:
1. Analiza la feature
2. Divide en issues más pequeños
3. Crea issues usando @linear create issue
4. Establece dependencias
5. Prioriza según importancia arquitectónica

## Consejos

- Define roles claros antes de empezar a trabajar
- Usa roles específicos para tareas específicas
- Combina roles cuando sea necesario
- Actualiza roles según experiencia
- Integra roles con comandos de Linear para máxima efectividad

