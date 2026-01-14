# Sistema de Completacion de Issues en Linear

## PASOS CRITICOS - INICIO OBLIGATORIO

Antes de cualquier accion, lee y memoriza estos dos pasos que NO puedes omitir:

```
PASO CRITICO 1: Despues de push → ejecutar `gh pr create`
PASO CRITICO 2: Despues de crear PR → ejecutar `update_issue(state: "In Review")`
```

Si omites cualquiera de estos pasos, el workflow falla completamente.

---

## CONTEXTO

- Etiqueta de grupo: "DNT"
- Si no se especifica issue: trabajar issues en estado "To Do"
- Leer `project-context.md` antes de iniciar cualquier trabajo
- Firma obligatoria en comentarios: `---\n_Hecho por Cursor_`

---

## WORKFLOW CON VERIFICACION

Ejecutar cada fase en orden. NO avanzar sin completar la verificacion.

### FASE 1: Inicio

```
ACCION: get_issue(id) → update_issue(state: "In Progress")
VERIFICAR: ¿Issue en "In Progress"? [SI/NO]
IF NO → Repetir accion
IF SI → Continuar a FASE 2
```

Analisis requerido:
- Requisitos del issue
- Dependencias o sub-issues
- Contexto tecnico suficiente
- Si faltan datos → preguntar al usuario

### FASE 2: Preparacion Git (si aplica)

```
CONDICION: ¿El trabajo requiere control de versiones?
IF SI → Crear branch: `git checkout -b feature/ISSUE-ID-descripcion`
IF NO → Saltar a FASE 3
```

Nunca trabajar en `main` o `master` directamente.

### FASE 3: Implementacion

```
ACCION: Implementar solucion completa
VERIFICAR: ¿Codigo funciona correctamente? [SI/NO]
IF NO → Corregir hasta que funcione
IF SI → Continuar a FASE 4
```

### FASE 4: Commit y Push (si aplica Git)

```
ACCION: git add . → git commit -m "tipo: descripcion" → git push origin branch
VERIFICAR: ¿Cambios pusheados a remoto? [SI/NO]
IF NO → Resolver errores y reintentar
IF SI → Continuar a FASE 5
```

### FASE 5: Crear Pull Request

```
CONDICION: ¿Se trabajo con Git?
IF SI → EJECUTAR OBLIGATORIAMENTE:
   gh pr create --title "tipo: ISSUE-ID descripcion" --body "Closes #ISSUE-ID" --base main
   
VERIFICAR: ¿PR creado exitosamente? [SI/NO]
IF NO → Resolver error y reintentar `gh pr create`
IF SI → Guardar URL del PR → Continuar a FASE 6

IF NO se trabajo con Git → Saltar a FASE 6
```

### FASE 6: Mover a In Review

```
ACCION OBLIGATORIA: update_issue(id, state: "In Review")
VERIFICAR: ¿Issue en estado "In Review"? [SI/NO]
IF NO → Ejecutar update_issue nuevamente
IF SI → Continuar a FASE 7
```

Esta fase es OBLIGATORIA independientemente de si se uso Git o no.

### FASE 7: Documentar en Linear

```
ACCION: create_comment con:
- Cambios realizados
- URL del PR (si aplica)
- Estado de verificacion
- Firma: ---\n_Hecho por Cursor_

VERIFICAR: ¿Comentario creado con firma? [SI/NO]
IF NO → Crear comentario
IF SI → Workflow completado, esperar aprobacion
```

### FASE 8: Esperar Aprobacion

```
REGLA: NUNCA ejecutar update_issue(state: "Done") sin aprobacion explicita del usuario
```

---

## REFERENCIA DE HERRAMIENTAS

| Herramienta | Uso | Parametros clave |
|-------------|-----|------------------|
| `get_issue` | Obtener detalles | `id` |
| `update_issue` | Cambiar estado/campos | `id`, `state`, `assignee` |
| `create_comment` | Documentar trabajo | `issueId`, `body` (con firma) |
| `list_issues` | Buscar issues | `team`, `state`, `parentId` |
| `gh pr create` | Crear Pull Request | `--title`, `--body`, `--base` |

---

## REGLAS HEURISTICAS

```
IF push_completado THEN ejecutar_gh_pr_create()
IF pr_creado THEN ejecutar_update_issue("In Review")
IF trabajo_terminado AND estado != "In Review" THEN ERROR - ejecutar FASE 6
IF comentario_sin_firma THEN agregar "---\n_Hecho por Cursor_"
IF usuario_no_aprobo THEN NO marcar "Done"
```

---

## ANTES DE FINALIZAR - VERIFICACION OBLIGATORIA

Antes de indicar que el trabajo esta completado, verificar TODOS estos puntos:

```
□ ¿Issue movido a "In Progress" al inicio?
□ ¿Codigo implementado y funcionando?
□ ¿PR creado con `gh pr create`? (si aplico Git)
□ ¿Issue movido a "In Review"?
□ ¿Comentario en Linear con firma "_Hecho por Cursor_"?
□ ¿NO marcado como "Done"? (esperar aprobacion)
```

Si cualquier checkbox es NO, ejecutar la fase correspondiente antes de continuar.

Los dos errores mas frecuentes son:
1. Olvidar `gh pr create` despues del push
2. Olvidar `update_issue(state: "In Review")` despues del PR

Verificar estos dos puntos especificamente antes de finalizar.
