# Agentes de Contexto por Directorio

Guía para crear agentes que se adaptan automáticamente según la estructura de directorios del proyecto, proporcionando contexto específico según la ubicación del código.

## Concepto

Los agentes de contexto por directorio utilizan la estructura de carpetas del proyecto para proporcionar contexto automático y reglas específicas según dónde se está trabajando.

## Implementación

### 1. Estructura de Directorios

Organiza tu proyecto con una estructura clara para aprovechar el contexto automático:

```
proyecto/
├── .cursorrules (reglas globales)
├── src/
│   ├── components/
│   │   └── .cursorrules (reglas de componentes)
│   ├── hooks/
│   │   └── .cursorrules (reglas de hooks)
│   ├── utils/
│   │   └── .cursorrules (reglas de utilidades)
│   ├── services/
│   │   └── .cursorrules (reglas de servicios)
│   └── types/
│       └── .cursorrules (reglas de tipos)
├── tests/
│   └── .cursorrules (reglas de testing)
└── docs/
    └── .cursorrules (reglas de documentación)
```

### 2. Reglas por Directorio

#### `components/.cursorrules`

```markdown
# Reglas para Componentes

Eres un experto en desarrollo de componentes trabajando en este directorio.

## Contexto del Directorio

Este directorio contiene componentes React reutilizables.

## Estructura Esperada

- Un componente por archivo
- Componente principal exportado como default
- Props tipadas con TypeScript
- Tests en archivo `.test.tsx` junto al componente

## Reglas Específicas

1. **Componentes Funcionales**
   - Usa componentes funcionales con hooks
   - Evita componentes de clase

2. **Props**
   - Tipa todas las props con TypeScript
   - Usa interfaces para props
   - Documenta props complejas con comentarios

3. **Composición**
   - Componentes pequeños y enfocados
   - Reutiliza componentes existentes
   - Evita duplicación de código

4. **Performance**
   - Usa React.memo para componentes pesados
   - Memoiza callbacks con useCallback
   - Memoiza valores costosos con useMemo

## Análisis de Código

Cuando analices componentes:
- Busca componentes que puedan optimizarse
- Identifica props drilling excesivo
- Verifica accesibilidad (a11y)
- Sugiere mejoras de composición

## Crear Issues

Al crear issues en Linear:
- Labels: "frontend", "component", "react"
- Tipo: "refactor" para mejoras de código
- Tipo: "performance" para optimizaciones
- Incluye ejemplo del componente mejorado
```

#### `hooks/.cursorrules`

```markdown
# Reglas para Hooks

Eres un experto en hooks personalizados trabajando en este directorio.

## Contexto del Directorio

Este directorio contiene hooks personalizados de React.

## Estructura Esperada

- Un hook por archivo
- Nombre del hook empieza con "use"
- Exportado como función nombrada
- Tests en archivo `.test.ts` junto al hook

## Reglas Específicas

1. **Nombres**
   - Nombres empiezan con "use"
   - Nombres descriptivos y claros

2. **Lógica**
   - Hooks deben ser reutilizables
   - Lógica compleja separada en hooks
   - Evita efectos colaterales innecesarios

3. **Dependencias**
   - Incluye todas las dependencias en useEffect
   - Usa useCallback/useMemo cuando sea apropiado
   - Limpia efectos con cleanup functions

4. **Type Safety**
   - Tipa el valor de retorno del hook
   - Tipa parámetros del hook
   - Usa generics cuando sea apropiado

## Análisis de Código

Cuando analices hooks:
- Busca dependencias faltantes
- Identifica efectos colaterales innecesarios
- Verifica cleanup de efectos
- Sugiere mejoras de reutilización

## Crear Issues

Al crear issues en Linear:
- Labels: "frontend", "hook", "react"
- Tipo: "bug" para errores en hooks
- Tipo: "refactor" para mejoras
- Incluye ejemplo del hook mejorado
```

#### `services/.cursorrules`

```markdown
# Reglas para Servicios

Eres un experto en servicios y lógica de negocio trabajando en este directorio.

## Contexto del Directorio

Este directorio contiene servicios que encapsulan lógica de negocio y comunicación con APIs.

## Estructura Esperada

- Un servicio por archivo o módulo
- Funciones exportadas nombradas
- Tests en directorio `__tests__/` o `.test.ts`

## Reglas Específicas

1. **Separación de Responsabilidades**
   - Servicios solo contienen lógica de negocio
   - No contienen lógica de UI
   - Comunicación con APIs separada

2. **Error Handling**
   - Maneja errores apropiadamente
   - Lanza errores descriptivos
   - Usa tipos de error específicos

3. **Type Safety**
   - Tipa funciones y parámetros
   - Tipa valores de retorno
   - Usa tipos para datos de API

4. **Testing**
   - Tests unitarios para cada servicio
   - Mocking de dependencias externas
   - Tests de edge cases

## Análisis de Código

Cuando analices servicios:
- Busca lógica que pueda extraerse
- Identifica manejo de errores insuficiente
- Verifica type safety
- Sugiere mejoras de testing

## Crear Issues

Al crear issues en Linear:
- Labels: "backend", "service", "api"
- Tipo: "bug" para errores en servicios
- Tipo: "refactor" para mejoras
- Incluye ejemplo del servicio mejorado
```

#### `tests/.cursorrules`

```markdown
# Reglas para Tests

Eres un experto en testing trabajando en este directorio.

## Contexto del Directorio

Este directorio contiene tests para el proyecto.

## Estructura Esperada

- Tests en archivos `.test.ts` o `.spec.ts`
- Tests organizados por componente/servicio
- Fixtures en `__fixtures__/`
- Mocks en `__mocks__/`

## Reglas Específicas

1. **Organización**
   - Un archivo de test por componente/servicio
   - Tests organizados con describe/it
   - Nombres descriptivos para tests

2. **Cobertura**
   - Tests para código crítico
   - Tests de edge cases
   - Tests de integración cuando sea necesario

3. **Mocking**
   - Mock de dependencias externas
   - Fixtures para datos de prueba
   - Evita mocks innecesarios

4. **Aserciones**
   - Aserciones claras y específicas
   - Un concepto por test
   - Mensajes de error descriptivos

## Análisis de Código

Cuando analices tests:
- Busca tests faltantes
- Identifica tests que pueden mejorarse
- Verifica cobertura de código crítico
- Sugiere mejoras de testing

## Crear Issues

Al crear issues en Linear:
- Labels: "test", "testing"
- Tipo: "chore" para tests faltantes
- Tipo: "refactor" para mejoras de tests
- Incluye ejemplo del test mejorado
```

### 3. Contexto Compuesto

Puedes combinar contexto de directorio con tipo de archivo:

```
components/
├── .cursorrules (reglas de componentes)
├── Button/
│   ├── Button.tsx
│   ├── Button.test.tsx
│   └── Button.module.css
└── Modal/
    ├── Modal.tsx
    └── Modal.test.tsx
```

El agente usará:
1. Reglas de `components/.cursorrules`
2. Reglas de tipo de archivo (`.cursorrules.tsx` si existe)
3. Reglas globales de `.cursorrules`

## Ejemplos de Uso

### Trabajar en Directorio de Componentes

Cuando abres un archivo en `components/`:

1. Cursor detecta `components/.cursorrules`
2. El agente se contextualiza como experto en componentes
3. Sabe sobre la estructura esperada de componentes
4. Proporciona sugerencias específicas de componentes
5. Crea issues con labels y formato apropiados

### Trabajar en Directorio de Tests

Cuando abres un archivo de test:

1. Cursor detecta `tests/.cursorrules`
2. El agente se contextualiza como experto en testing
3. Sabe sobre las convenciones de testing del proyecto
4. Sugiere mejoras de tests
5. Crea issues para tests faltantes o mejoras

## Mejores Prácticas

### 1. Estructura Clara

- ✅ Organiza directorios por funcionalidad
- ✅ Crea `.cursorrules` en directorios clave
- ✅ Mantén consistencia en estructura

### 2. Contexto Específico

- ✅ Incluye información específica del directorio
- ✅ Documenta convenciones del directorio
- ✅ Actualiza cuando cambian convenciones

### 3. Herencia de Reglas

- ✅ Reglas globales en raíz
- ✅ Reglas específicas en subdirectorios
- ✅ Las reglas específicas sobrescriben las globales

## Referencias

- Ver agentes por tipo de archivo en `docs/agents/context-aware/file-type-agents.md`
- Ver configuración de agentes en `docs/agents/expert-agents.md`
- Ver ejemplos en `examples/cursorrules-templates/`

