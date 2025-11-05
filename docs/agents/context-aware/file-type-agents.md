# Agentes de Contexto por Tipo de Archivo

Guía para crear agentes que se adaptan automáticamente según el tipo de archivo con el que se está trabajando, usando `.cursorrules` dinámicos.

## Concepto

Los agentes de contexto por tipo de archivo se adaptan automáticamente según la extensión del archivo o el tipo de código con el que trabajas, proporcionando reglas y conocimientos específicos relevantes.

## Implementación

### 1. .cursorrules por Extensión

Crea archivos `.cursorrules` específicos para diferentes tipos de archivos:

#### `.cursorrules.ts` (TypeScript)

```markdown
# Reglas para Archivos TypeScript

Eres un experto en TypeScript cuando trabajas con archivos .ts, .tsx.

## Reglas Específicas

- Usa tipos estrictos, evita `any`
- Usa interfaces para objetos, tipos para uniones
- Aprovecha utility types (Partial, Pick, Omit)
- Exporta tipos e interfaces cuando sean reutilizables
- Usa generics cuando sea apropiado

## Análisis de Código

Cuando analices código TypeScript:
- Busca uso de `any` que pueda mejorarse
- Identifica tipos que puedan ser más específicos
- Verifica type safety en funciones críticas
- Sugiere mejoras de tipos

## Crear Issues

Al crear issues en Linear para código TypeScript:
- Usa label: "typescript"
- Tipo: "refactor" para mejoras de tipos
- Tipo: "bug" para errores de tipos
- Incluye ejemplos de tipos mejorados en descripción
```

#### `.cursorrules.py` (Python)

```markdown
# Reglas para Archivos Python

Eres un experto en Python cuando trabajas con archivos .py.

## Reglas Específicas

- Usa type hints en todas las funciones
- Sigue PEP 8 style guide
- Usa docstrings (Google o NumPy style)
- Maneja excepciones apropiadamente
- Usa pathlib para rutas de archivos
- Usa f-strings para formateo

## Análisis de Código

Cuando analices código Python:
- Busca funciones sin type hints
- Identifica código que no sigue PEP 8
- Verifica manejo de excepciones
- Sugiere mejoras de código

## Crear Issues

Al crear issues en Linear para código Python:
- Usa label: "python"
- Tipo: "refactor" para mejoras de código
- Tipo: "bug" para errores
- Incluye ejemplos de código mejorado
```

#### `.cursorrules.jsx` (React)

```markdown
# Reglas para Archivos React/JSX

Eres un experto en React cuando trabajas con archivos .jsx, .tsx.

## Reglas Específicas

- Usa componentes funcionales con hooks
- Props tipadas con TypeScript
- Componentes pequeños y reutilizables
- Usa React.memo para componentes pesados
- Implementa accesibilidad (a11y)

## Análisis de Código

Cuando analices código React:
- Busca componentes que puedan optimizarse
- Identifica hooks que puedan mejorarse
- Verifica accesibilidad
- Sugiere mejoras de performance

## Crear Issues

Al crear issues en Linear para código React:
- Usa label: "react", "frontend"
- Tipo: "performance" para optimizaciones
- Tipo: "refactor" para mejoras de código
- Incluye ejemplos de componentes mejorados
```

### 2. .cursorrules por Directorio

Crea archivos `.cursorrules` en directorios específicos:

#### `frontend/.cursorrules`

```markdown
# Reglas para Frontend

Eres un experto en desarrollo frontend trabajando en este directorio.

## Contexto del Directorio

- Framework: React/Next.js
- Estilo: CSS Modules / Tailwind
- Estado: Context API / Zustand
- Testing: Jest + React Testing Library

## Reglas Específicas

- Componentes en `components/`
- Hooks en `hooks/`
- Utilidades en `utils/`
- Tipos en `types/`

## Crear Issues

Al crear issues:
- Asigna a equipo: "Frontend"
- Usa labels: "frontend", "ui"
- Prioriza issues visuales como "High"
```

#### `backend/.cursorrules`

```markdown
# Reglas para Backend

Eres un experto en desarrollo backend trabajando en este directorio.

## Contexto del Directorio

- Framework: Django/FastAPI
- Base de datos: PostgreSQL
- API: RESTful
- Testing: pytest

## Reglas Específicas

- Models en `models/`
- Views/Controllers en `views/` o `controllers/`
- Servicios en `services/`
- Tests en `tests/`

## Crear Issues

Al crear issues:
- Asigna a equipo: "Backend"
- Usa labels: "backend", "api"
- Prioriza issues de seguridad como "Urgent"
```

### 3. Configuración Automática

Cursor detecta automáticamente los archivos `.cursorrules` más cercanos al archivo actual. El orden de prioridad es:

1. `.cursorrules` en el mismo directorio
2. `.cursorrules` en el directorio padre
3. `.cursorrules` en la raíz del proyecto

## Ejemplos de Uso

### Trabajar con Archivo TypeScript

Cuando abres un archivo `.ts` o `.tsx`:

1. Cursor detecta `.cursorrules.ts` si existe
2. El agente se contextualiza como experto en TypeScript
3. Proporciona sugerencias específicas de TypeScript
4. Crea issues con labels y formato apropiados

### Trabajar en Directorio Frontend

Cuando trabajas en `frontend/`:

1. Cursor detecta `frontend/.cursorrules`
2. El agente se contextualiza como experto en frontend
3. Sabe sobre el stack frontend del proyecto
4. Crea issues con asignación y labels apropiados

## Plantillas de .cursorrules

### Plantilla Base

```markdown
# Reglas para [Tipo de Archivo/Directorio]

Eres un experto en [Tecnología] cuando trabajas con [archivos/directorio].

## Contexto

[Información sobre el contexto específico]

## Reglas Específicas

- [Regla 1]
- [Regla 2]
- [Regla 3]

## Análisis de Código

Cuando analices código:
- [Qué buscar]
- [Qué verificar]
- [Qué sugerir]

## Crear Issues

Al crear issues en Linear:
- Labels: [lista de labels]
- Tipo: [tipo por defecto]
- Asignación: [equipo/persona]
- Incluye: [qué incluir en descripción]
```

## Mejores Prácticas

### 1. Especificidad

- ✅ Crea reglas específicas para cada tipo de archivo
- ✅ Incluye contexto del proyecto
- ❌ Evita reglas demasiado genéricas

### 2. Mantenimiento

- ✅ Actualiza reglas cuando cambia el stack
- ✅ Documenta cambios importantes
- ✅ Mantén consistencia entre reglas relacionadas

### 3. Organización

- ✅ Usa múltiples archivos `.cursorrules` para diferentes contextos
- ✅ Organiza por tipo de archivo o directorio
- ✅ Mantén reglas globales en la raíz

## Ejemplos de Configuración

### Proyecto Fullstack

```
proyecto/
├── .cursorrules (reglas globales)
├── frontend/
│   ├── .cursorrules (reglas frontend)
│   └── src/
│       ├── components/
│       └── hooks/
├── backend/
│   ├── .cursorrules (reglas backend)
│   └── src/
│       ├── models/
│       └── views/
└── docs/
```

### Archivos Específicos

```
proyecto/
├── .cursorrules.ts (TypeScript)
├── .cursorrules.py (Python)
├── .cursorrules.jsx (React)
├── .cursorrules.test (Tests)
└── src/
```

## Referencias

- Ver configuración de agentes en `docs/agents/expert-agents.md`
- Ver mejores prácticas en `docs/rules/best-practices.md`
- Ver ejemplos en `examples/cursorrules-templates/`

