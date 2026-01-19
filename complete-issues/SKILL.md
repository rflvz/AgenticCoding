---
name: complete-issues
description: Completa issues en Linear siguiendo un workflow estricto, usando subagentes cuando hay múltiples issues, creando PRs y actualizando estados. Úsala cuando el usuario pida completar issues, mover estados en Linear o coordinar varias issues a la vez.
---

# Complete Issues (Linear)

## Quick start

1. Leer `/mnt/project/project-context.md` antes de iniciar.
2. Si hay más de una issue → usar subagente `issue-completer` por cada issue.
3. Seguir el workflow completo hasta "In Review".
4. Crear comentario final con firma obligatoria.
5. Nunca marcar "Done" sin aprobación explícita del usuario.

## Decisión de arquitectura (subagentes)

```
IF cantidad_de_issues > 1 THEN
  llamar_subagente_issue_completer(issue_id) por cada issue
  consolidar_resultados()
  presentar_reporte_unificado()
ELSE
  ejecutar_workflow_directo()
```

## Pasos no omitibles

```
1. Después de push → ejecutar `gh pr create`
2. Después de crear PR → ejecutar `update_issue(state: "In Review")`
```

## Workflow completo

### Fase 1: Inicio

```
get_issue(id)
update_issue(id, state: "In Progress")

VERIFICAR: ¿Estado == "In Progress"? [SI/NO]
IF NO → repetir update_issue
IF SI → continuar
```

Antes de avanzar, verificar:
- Requisitos funcionales claros
- Dependencias resueltas o documentadas
- Contexto técnico suficiente
- Si falta información → preguntar al usuario

### Fase 2: Preparación Git

```
IF requiere_código THEN
  git checkout -b feature/ISSUE-ID-descripcion
ELSE
  saltar a FASE 3
```

### Fase 3: Implementación

```
implementar_solución()

VERIFICAR: ¿Funciona correctamente? [SI/NO]
IF NO → corregir → verificar nuevamente
IF SI → continuar
```

### Fase 4: Commit y Push

```
IF se_usó_git THEN
  git add .
  git commit -m "tipo: descripción"
  git push origin branch
  
  VERIFICAR: ¿Push exitoso? [SI/NO]
  IF NO → resolver error → reintentar
  IF SI → continuar
ELSE
  saltar a FASE 6
```

### Fase 5: Pull Request

```
IF se_usó_git THEN
  gh pr create --title "tipo: ISSUE-ID descripción" \
               --body "Closes #ISSUE-ID" \
               --base main
  
  VERIFICAR: ¿PR creado? [SI/NO]
  IF NO → resolver error → reintentar gh pr create
  IF SI → guardar URL → continuar
ELSE
  saltar a FASE 6
```

### Fase 6: Mover a In Review

```
update_issue(id, state: "In Review")

VERIFICAR: ¿Estado == "In Review"? [SI/NO]
IF NO → ejecutar update_issue nuevamente
IF SI → continuar
```

Obligatorio independientemente de si se usó Git.

### Fase 7: Documentación

```
create_comment(
  issueId: id,
  body: "
    ## Trabajo Completado
    
    [descripción de cambios]
    [URL del PR si aplica]
    
    ---
    _Hecho por Cursor_
  "
)

VERIFICAR: ¿Comentario creado con firma? [SI/NO]
IF NO → crear comentario
IF SI → workflow completado
```

### Fase 8: Esperar aprobación

```
NUNCA ejecutar update_issue(state: "Done") sin aprobación explícita del usuario
```

## Reglas heurísticas

```
IF múltiples_issues THEN usar_subagente_issue_completer()
IF push_completado THEN ejecutar_gh_pr_create()
IF pr_creado THEN ejecutar_update_issue("In Review")
IF trabajo_terminado AND estado != "In Review" THEN ERROR
IF comentario_sin_firma THEN agregar "---\n_Hecho por Cursor_"
IF usuario_no_aprobó THEN NO ejecutar update_issue("Done")
```

## Uso de subagente issue-completer

Patrón de invocación:

```
Usuario solicita: [DNT-101, DNT-102, DNT-103]

Detectar: 3 issues → múltiples

Ejecutar:
  FOR issue IN [DNT-101, DNT-102, DNT-103]:
    subagente.issue-completer(issue)
  END FOR

Consolidar:
  recopilar_estado_de_cada_issue()
  identificar_completados_vs_bloqueados()
  
Reportar:
  DNT-101: estado y resultado
  DNT-102: estado y resultado
  DNT-103: estado y resultado
  
  Issues que requieren atención: [lista]
```

Coordinación de resultados:
1. Esperar completación de todos los subagentes
2. Recopilar estado individual de cada issue
3. Identificar issues bloqueados o con errores
4. Presentar reporte consolidado
5. Solicitar acción del usuario para issues bloqueados

## Herramientas

| Herramienta | Parámetros | Uso |
|-------------|------------|-----|
| `get_issue` | `id` | Obtener detalles |
| `update_issue` | `id`, `state`, `assignee` | Cambiar estado/asignación |
| `create_comment` | `issueId`, `body` | Documentar trabajo |
| `list_issues` | `team`, `state`, `parentId` | Buscar issues |
| `gh pr create` | `--title`, `--body`, `--base` | Crear PR |

## Verificación final

Antes de indicar trabajo completado:

```
□ ¿Múltiples issues? → ¿Se usó subagente issue-completer?
□ ¿Issue en "In Progress" al inicio?
□ ¿Implementación funcional?
□ ¿PR creado? (si Git)
□ ¿Issue en "In Review"?
□ ¿Comentario con firma creado?
□ ¿NO marcado "Done"?
```

Errores más frecuentes:
1. No usar subagente con múltiples issues
2. Olvidar `gh pr create` después de push
3. Olvidar `update_issue(state: "In Review")` después de PR

## Recursos

- Ejemplos: [examples.md](examples.md)
- Referencia detallada: [reference.md](reference.md)
