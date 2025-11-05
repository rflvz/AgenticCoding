<!-- 92ee2434-5ce3-4236-a835-84bc0e1998b4 2eb2626d-dd23-40a9-b17a-28a1ccea4156 -->
# Plan: Actualizar Comandos de Linear con Enfoque Profesional

## Objetivo

Transformar los comandos de Linear de simples referencias a guías profesionales que instruyan al agente a actuar como un project manager/programador experto, no solo como un usuario básico del MCP.

## Archivos a Actualizar

### 1. docs/commands/linear/create-issues.md

**Cambios principales:**

- Añadir instrucciones para actuar como project manager profesional
- Guía para crear issues con dependencias entre ellas
- Instrucciones para usar divide y vencerás para simplificar tareas grandes
- Guía para crear sub-issues (issues hijos) para organizarse bien
- Instrucciones para crear labels si no existen
- Proceso de clarificación de dudas antes de crear issues
- Estructura profesional como prompt engineer

### 2. docs/commands/linear/complete-issues.md

**Cambios principales:**

- Añadir instrucciones para completar issues de manera profesional
- Integración con GitHub: trabajar en repositorios, crear ramas
- Crear repositorio si hace falta
- Trabajar con ramas como profesional de control de versiones
- Proceso completo de implementación antes de marcar como done
- Verificación de que el trabajo está realmente completo
- Aclaración de dudas durante el proceso
- Documentación profesional del trabajo realizado

## Estructura de las Instrucciones

### Para crear-issues.md:

1. **Introducción**: Actuar como project manager/programador experto
2. **Proceso de Planificación**: 

- Analizar la tarea antes de crear issues
- Aclarar dudas con el usuario
- Identificar si es una tarea grande que requiere división

3. **Divide y Vencerás**: 

- Detectar tareas grandes
- Dividir en sub-tareas manejables
- Crear issues padre (Epic) y sub-issues

4. **Dependencias**: 

- Identificar dependencias entre tareas
- Establecer relaciones entre issues
- Usar parentId para crear jerarquía

5. **Labels**: 

- Verificar si existen labels necesarios
- Crear labels si no existen usando mcp_Linear_create_issue_label
- Usar labels consistentemente

6. **Proceso de Creación**: 

- Crear issues con toda la información necesaria
- Establecer dependencias claras
- Priorizar apropiadamente

### Para complete-issues.md:

1. **Introducción**: Completar issues profesionalmente, no solo marcarlos
2. **Análisis del Issue**: 

- Revisar qué requiere el issue
- Aclarar dudas si es necesario
- Verificar que entiendes completamente la tarea

3. **Integración con GitHub**: 

- Verificar si existe repositorio
- Crear repositorio si hace falta
- Trabajar con ramas profesionales
- Crear rama desde el issue
- Hacer commits apropiados

4. **Implementación**: 

- Implementar la solución completa
- Verificar que funciona
- Añadir tests si aplica
- Documentar cambios

5. **Completar el Issue**: 

- Actualizar estado a "Done"
- Añadir comentario profesional con resumen
- Incluir referencias a commits/PRs
- Verificar que sub-issues también están completados

## Características Clave

### Profesionalismo

- Actuar como experto, no como usuario básico
- Proceso completo, no solo comandos simples
- Verificación y validación en cada paso

### Clarificación de Dudas

- Preguntar antes de crear issues si algo no está claro
- Aclarar dudas durante la implementación
- Confirmar entendimiento antes de proceder

### Gestión de Dependencias

- Identificar dependencias entre tareas
- Crear issues con dependencias claras
- Gestionar orden de ejecución

### Divide y Vencerás

- Detectar tareas grandes automáticamente
- Dividir en sub-tareas manejables (1-3 días)
- Crear jerarquía de issues (padre/hijo)

### Labels Dinámicos

- Verificar existencia de labels
- Crear labels si no existen
- Usar labels consistentemente

### Integración GitHub

- Verificar repositorio existente
- Crear repositorio si hace falta
- Trabajar con ramas profesionales
- Hacer commits apropiados
- Crear PRs cuando aplique

### Control de Versiones Profesional

- Crear ramas con nombres descriptivos
- Hacer commits con mensajes claros
- Seguir convenciones de commits
- Integrar con issues de Linear

## Formato de Prompt Engineer

- Instrucciones claras y estructuradas
- Ejemplos concretos
- Procesos paso a paso
- Validaciones en cada etapa
- Manejo de errores y casos edge

### To-dos

- [ ] Actualizar create-issues.md con instrucciones profesionales: project manager, dependencias, divide y vencerás, sub-issues, labels dinámicos, clarificación de dudas
- [ ] Actualizar complete-issues.md con proceso profesional: integración GitHub, creación de repositorios, ramas profesionales, implementación completa, verificación