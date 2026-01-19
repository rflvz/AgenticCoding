---
name: issue-orchestrator
description: Orquesta el workflow de completado de issues en Linear, usando subagentes para múltiples issues, creando PRs cuando hay Git y moviendo estados. Usar cuando el usuario pide completar una o varias issues, coordinar subagentes o consolidar resultados.
---

# Issue Orchestrator

## Propósito
Coordinar el workflow de completado de issues con decisiones de arquitectura, uso de subagentes y reporte consolidado, siguiendo las reglas de `issue-completer` y `complete-issues`.

## Quick Start
1. Detecta si hay una o múltiples issues.
2. Si hay múltiples: invoca un subagente `issue-completer` por issue y consolida resultados.
3. Si hay una: ejecuta el workflow directo de completado.
4. Verifica checklist final antes de reportar.

## Decisión de arquitectura
```
IF cantidad_de_issues > 1 THEN
  llamar_subagente_issue_completer(issue_id) por cada issue
  consolidar_resultados()
  presentar_reporte_unificado()
ELSE
  ejecutar_workflow_directo()
```

## Workflow directo (una issue)
### Fase 1: Inicio
```
get_issue(id)
update_issue(id, state: "In Progress")

VERIFICAR: ¿Estado == "In Progress"? [SI/NO]
IF NO → repetir update_issue
IF SI → continuar
```

Verificar antes de avanzar:
- Requisitos funcionales claros
- Dependencias resueltas o documentadas
- Contexto técnico suficiente
- Si falta información → preguntar al usuario

### Fase 2: Preparación Git
```
IF requiere_código THEN
  git checkout -b feature/ISSUE-ID-descripcion
ELSE
  saltar a Fase 3
```

### Fase 3: Implementación
```
implementar_solución()

VERIFICAR: ¿Funciona correctamente? [SI/NO]
IF NO → corregir → verificar nuevamente
IF SI → continuar
```

Si existen tests:
```
ejecutar_tests()
documentar_resultados()
```

### Fase 4: Commit y Push (si Git)
```
IF se_usó_git THEN
  git add .
  git commit -m "tipo: descripción"
  git push origin branch

  VERIFICAR: ¿Push exitoso? [SI/NO]
  IF NO → resolver error → reintentar
  IF SI → continuar
ELSE
  saltar a Fase 6
```

### Fase 5: Pull Request (si Git)
```
IF se_usó_git THEN
  gh pr create --title "tipo: ISSUE-ID descripción" \
               --body "Closes #ISSUE-ID" \
               --base main

  VERIFICAR: ¿PR creado? [SI/NO]
  IF NO → resolver error → reintentar gh pr create
  IF SI → guardar URL → continuar
ELSE
  saltar a Fase 6
```

### Fase 6: Mover a In Review
```
update_issue(id, state: "In Review")

VERIFICAR: ¿Estado == "In Review"? [SI/NO]
IF NO → ejecutar update_issue nuevamente
IF SI → continuar
```

### Fase 7: Documentación
```
create_comment(
  issueId: id,
  body: resumen + "\n\n---\n_Hecho por Cursor_"
)

VERIFICAR: ¿Comentario creado con firma? [SI/NO]
IF NO → crear comentario
IF SI → workflow completado
```

### Fase 8: Esperar aprobación
```
NUNCA ejecutar update_issue(state: "Done") sin aprobación explícita del usuario
```

## Uso de subagente `issue-completer` (múltiples issues)
### Patrón de invocación
```
FOR issue IN [DNT-101, DNT-102, DNT-103]:
  subagente.issue-completer(issue)
END FOR
```

### Coordinación de resultados
1. Esperar completación de todos los subagentes.
2. Recopilar estado individual de cada issue.
3. Identificar issues bloqueados o con errores.
4. Presentar reporte consolidado.
5. Solicitar acción del usuario para issues bloqueados.

## Checklist de verificación final
```
□ ¿Múltiples issues? → ¿Se usó subagente issue-completer?
□ ¿Issue en "In Progress" al inicio?
□ ¿Implementación funcional?
□ ¿PR creado? (si Git)
□ ¿Issue en "In Review"?
□ ¿Comentario con firma creado?
□ ¿NO marcado "Done"?
```

## Formato de salida (reporte consolidado)
```
Issue: [ID] - [Título]

Progreso:
□ In Progress: ✓
□ Implementación: ✓
□ Tests: ✓ (X pasaron, Y fallaron)
□ PR creado: ✓ [URL]
□ In Review: ✓
□ Comentario: ✓

Cambios principales:
- [archivo/área]: [cambio]
- [archivo/área]: [cambio]

Tests:
- Comando: [comando]
- Resultado: [resultado]

Pendientes/Riesgos:
- [si aplica]
```
