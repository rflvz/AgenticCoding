---
title: Ejemplos de uso
---

# Ejemplos de uso

## Ejemplo 1: Una issue con PR

**Entrada del usuario:**
Completa la issue DNT-101 y crea el PR.

**Flujo esperado:**
1. `get_issue(DNT-101)` → `update_issue(DNT-101, "In Progress")`
2. Implementar solución
3. `git commit` + `git push`
4. `gh pr create` (obligatorio después del push)
5. `update_issue(DNT-101, "In Review")`
6. `create_comment` con firma obligatoria
7. No marcar "Done" sin aprobación explícita

## Ejemplo 2: Múltiples issues

**Entrada del usuario:**
Necesito resolver DNT-201, DNT-202 y DNT-203.

**Flujo esperado:**
1. Detectar múltiples issues
2. Invocar subagente por issue:
   - `subagente.issue-completer(DNT-201)`
   - `subagente.issue-completer(DNT-202)`
   - `subagente.issue-completer(DNT-203)`
3. Esperar finalización
4. Consolidar resultados en un reporte único
5. Solicitar acción del usuario si hay bloqueos

## Ejemplo 3: Issue sin cambios de código

**Entrada del usuario:**
Actualiza la issue DNT-301 con documentación. No requiere cambios de código.

**Flujo esperado:**
1. `get_issue` → `update_issue("In Progress")`
2. Realizar tareas sin Git
3. Saltar commit/push/PR
4. `update_issue("In Review")` (obligatorio)
5. `create_comment` con firma
6. No marcar "Done" sin aprobación

## Ejemplo 4: Comentario final con firma

```
## Trabajo Completado

- Descripción breve de cambios
- PR: https://github.com/org/repo/pull/123

---
_Hecho por Cursor_
```
