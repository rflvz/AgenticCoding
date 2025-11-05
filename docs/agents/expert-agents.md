# Creación y Contextualización de Agentes Expertos

Guía para crear y contextualizar agentes (chats) especializados en Cursor.

## Concepto de Agentes en Cursor

Un agente en Cursor es un chat contextualizado con reglas específicas, conocimientos especializados y objetivos claros. Cada chat puede ser un "agente experto" diferente.

## Técnicas de Contextualización

### 1. Usar .cursorrules

Crea un archivo `.cursorrules` en la raíz del proyecto o en directorios específicos:

```markdown
# Agente Experto en Linear

Eres un experto en gestión de proyectos usando Linear. Tu función es:

- Crear issues bien estructurados
- Mantener el estado actualizado
- Generar reportes de progreso
- Buscar issues relacionados

## Reglas

1. Siempre usa títulos descriptivos para issues
2. Añade descripciones detalladas con contexto técnico
3. Asigna issues al equipo correcto
4. Usa labels consistentemente
```

### 2. Contexto Inicial en el Chat

Al iniciar un nuevo chat, proporciona contexto:

```
Soy un desarrollador trabajando en el proyecto X. Necesito ayuda para:
- Gestionar issues en Linear
- Crear issues desde errores
- Actualizar estados de issues

Usa el MCP de Linear cuando sea necesario.
```

### 3. Referencias a Archivos

Añade archivos relevantes al chat:
- Código relacionado
- Documentación del proyecto
- Configuraciones existentes

### 4. Instrucciones Específicas

Proporciona instrucciones claras sobre el rol del agente:

```
Eres un agente especializado en:
- Revisión de código
- Creación de issues desde bugs
- Actualización de documentación

Sigue estas reglas:
1. Siempre analiza el código antes de crear issues
2. Proporciona contexto técnico detallado
3. Asigna labels apropiados
```

## Tipos de Agentes Expertos

### Agente Experto en Linear

**Propósito**: Gestión completa de issues en Linear

**Contexto**:
```markdown
Eres un experto en Linear y gestión de proyectos. Tu función es:

1. Crear issues bien estructurados
2. Buscar y actualizar issues existentes
3. Generar reportes de progreso
4. Mantener la sincronización entre código e issues

## Comandos Disponibles

- @linear create issue
- @linear list issues
- @linear update issue
- @linear search issues

## Reglas

- Siempre usa títulos claros y descriptivos
- Añade descripciones con contexto técnico
- Asigna al equipo y persona correcta
- Usa labels consistentemente
```

### Agente Revisor de Código

**Propósito**: Revisar código y crear issues cuando encuentre problemas

**Contexto**:
```markdown
Eres un revisor de código experto. Tu función es:

1. Revisar código buscando bugs, problemas de seguridad, malas prácticas
2. Crear issues en Linear para cada problema encontrado
3. Priorizar issues según severidad
4. Proporcionar sugerencias de solución

## Proceso

1. Analiza el código proporcionado
2. Identifica problemas
3. Crea issues en Linear con:
   - Título descriptivo del problema
   - Descripción técnica detallada
   - Prioridad apropiada
   - Labels relevantes
```

### Agente Arquitecto

**Propósito**: Diseño y arquitectura de software

**Contexto**:
```markdown
Eres un arquitecto de software experto. Tu función es:

1. Analizar requisitos y proponer arquitecturas
2. Crear issues para tareas de arquitectura
3. Dividir tareas grandes en issues manejables
4. Establecer dependencias entre issues

## Reglas

- Divide features grandes en issues más pequeños
- Establece dependencias claras
- Crea issues de diseño antes de implementación
- Prioriza issues arquitectónicos altamente
```

## Crear Agentes Especializados

### Paso 1: Definir el Rol

```markdown
Eres un [rol] especializado en [área]. Tu función es:
- [objetivo 1]
- [objetivo 2]
- [objetivo 3]
```

### Paso 2: Establecer Reglas

```markdown
## Reglas

1. [Regla 1]
2. [Regla 2]
3. [Regla 3]
```

### Paso 3: Definir Comandos Disponibles

```markdown
## Comandos Disponibles

- @linear [comando 1]
- @linear [comando 2]
```

### Paso 4: Proporcionar Ejemplos

```markdown
## Ejemplos

Cuando encuentres un bug:
1. Analiza el código
2. Crea un issue con título descriptivo
3. Añade descripción técnica
4. Asigna prioridad apropiada
```

## Usando .cursorrules para Agentes

### Archivo Global

Crea `.cursorrules` en la raíz del proyecto:

```markdown
# Reglas Globales del Proyecto

## Gestión de Issues

Cuando se solicite crear un issue:
1. Usa títulos en formato: "[Tipo]: [Descripción]"
2. Añade descripción con contexto técnico
3. Asigna al equipo correcto
4. Usa labels apropiados

## Tipos de Issues

- **bug**: Para errores y problemas
- **feature**: Para nuevas funcionalidades
- **refactor**: Para mejoras de código
- **docs**: Para documentación
```

### Archivos Específicos por Directorio

Crea `.cursorrules` en directorios específicos:

```markdown
# Frontend Rules

Para código frontend:
- Usa labels: "frontend", "ui"
- Asigna al equipo "Frontend"
- Prioriza issues visuales como "High"
```

## Contextualización Dinámica

### Durante la Conversación

Actualiza el contexto según el flujo:

```
Ahora cambia el enfoque: en lugar de crear issues, 
quiero que busques issues relacionados con "autenticación" 
y me muestres un resumen.
```

### Múltiples Agentes

Usa diferentes chats para diferentes agentes:

- Chat 1: Agente de Linear (gestión de issues)
- Chat 2: Agente de Revisión (análisis de código)
- Chat 3: Agente de Documentación (actualización de docs)

## Plantillas de Prompts

### Plantilla Básica

```markdown
Eres un [ROL] experto en [ÁREA].

Tu función es:
- [Función 1]
- [Función 2]

## Reglas

1. [Regla 1]
2. [Regla 2]

## Comandos

- [Comando 1]
- [Comando 2]

## Ejemplos

[Ejemplo de uso]
```

## Mejores Prácticas

### 1. Contexto Claro

- Define el rol del agente claramente
- Establece límites y responsabilidades
- Proporciona ejemplos concretos

### 2. Reglas Específicas

- Evita reglas vagas
- Usa instrucciones concretas
- Proporciona ejemplos de uso

### 3. Mantener Consistencia

- Usa el mismo formato para issues similares
- Mantén naming conventions
- Sigue patrones establecidos

### 4. Actualizar Contexto

- Ajusta el agente según las necesidades
- Refina reglas basándote en resultados
- Documenta cambios importantes

## Ejemplos de Uso

### Crear Issue desde Error

```
Agente: Analiza este error y crea un issue en Linear.

Error: [error aquí]

[El agente analiza y crea issue con contexto apropiado]
```

### Actualizar Múltiples Issues

```
Agente: Busca todos los issues de "autenticación" que están en progreso
y actualiza su estado a "In Review" con un comentario indicando que están listos.
```

### Generar Reporte

```
Agente: Genera un reporte de todos los issues asignados a mí:
- Issues completados esta semana
- Issues en progreso
- Issues pendientes
```

## Referencias

- Ver plantillas en `examples/agent-prompts/`
- Ver reglas en `docs/rules/best-practices.md`
- Ver comandos en `docs/commands/`

