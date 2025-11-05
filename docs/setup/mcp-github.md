# Configuración MCP de GitHub

Guía rápida para configurar el MCP (Model Context Protocol) de GitHub en Cursor para sincronización con repositorios, gestión de PRs y issues.

## Requisitos Previos

- Cursor instalado
- Cuenta de GitHub activa
- Token de acceso personal de GitHub (PAT) con permisos apropiados

## Pasos de Configuración

### 1. Obtener Token de GitHub

1. Ve a GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Genera un nuevo token con los siguientes permisos:
   - `repo` (acceso completo a repositorios)
   - `workflow` (para CI/CD workflows)
   - `read:org` (si trabajas con organizaciones)
   - `read:user` (información de usuario)
3. Copia el token (solo se muestra una vez)

### 2. Instalar MCP de GitHub

1. Ve al [directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
2. Busca "GitHub" en la lista de MCPs disponibles
3. Haz clic en el botón de instalación para añadir automáticamente el MCP de GitHub

### 3. Configurar Token de API

1. Abre la configuración de Cursor (Settings)
2. Navega a **Features** → **Model Context Protocol**
3. Busca la configuración de "GitHub" y añade tu token:
   - En el campo `GITHUB_TOKEN`, pega el token que copiaste en el paso 1

### 4. Configurar Repositorio (Opcional)

Si trabajas principalmente con un repositorio específico:

1. En la configuración del MCP de GitHub, añade:
   - `GITHUB_REPO`: `owner/repo` (ej: `usuario/mi-proyecto`)
   - `GITHUB_OWNER`: `owner` (ej: `usuario`)

## Verificación

1. Reinicia Cursor
2. Abre un chat nuevo
3. Prueba el comando: `@github list repositories`
4. Deberías ver tus repositorios de GitHub

## Funcionalidades Disponibles

### Gestión de Issues

- Crear issues desde código o errores
- Listar y buscar issues
- Actualizar estados de issues
- Comentar en issues

### Gestión de Pull Requests

- Crear PRs desde Linear issues
- Listar PRs abiertos
- Revisar cambios en PRs
- Comentar en PRs

### Sincronización con Linear

- Crear issues de GitHub desde Linear issues
- Sincronizar estados entre Linear y GitHub
- Vincular PRs con Linear issues

## Workflows de Sincronización

### Crear PR desde Linear Issue

```
Workflow: Crear PR desde Linear Issue

1. Obtener issue de Linear: @linear get issue ISSUE_ID
2. Crear branch desde el issue: @github create branch "feature/ISSUE_ID-descripcion"
3. Desarrollar código
4. Crear PR: @github create pull request "title" --body "description" --base "main"
5. Vincular con Linear: @linear update issue ISSUE_ID --description "PR: [link]"
```

### Sincronizar Issues

```
Workflow: Sincronizar Issues Linear ↔ GitHub

1. Crear issue en Linear: @linear create issue "title"
2. Crear issue correspondiente en GitHub: @github create issue "title"
3. Vincular ambos issues en descripciones
4. Actualizar estados en ambos sistemas cuando cambien
```

## Comandos Útiles

### Issues

- `@github list issues` - Listar issues del repositorio
- `@github create issue "title"` - Crear nuevo issue
- `@github get issue ISSUE_NUMBER` - Obtener detalles de issue
- `@github update issue ISSUE_NUMBER` - Actualizar issue

### Pull Requests

- `@github list pull requests` - Listar PRs
- `@github create pull request "title"` - Crear PR
- `@github get pull request PR_NUMBER` - Obtener detalles de PR
- `@github merge pull request PR_NUMBER` - Fusionar PR

### Repositorios

- `@github list repositories` - Listar repositorios
- `@github get repository` - Información del repositorio actual
- `@github list branches` - Listar ramas

## Solución de Problemas

### El MCP no se conecta

- Verifica que el token tenga los permisos correctos
- Revisa que el token no haya expirado
- Reinicia Cursor completamente

### No puedo crear PRs

- Verifica permisos de escritura en el repositorio
- Asegúrate de que el token tenga permisos `repo`
- Comprueba que estás trabajando con el repositorio correcto

### Issues no se sincronizan

- Verifica que ambos MCPs (Linear y GitHub) estén configurados
- Revisa los formatos de los IDs de issues
- Asegúrate de tener permisos en ambos sistemas

## Referencias

- [Directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
- [Documentación oficial de GitHub MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/github)
- [GitHub Personal Access Tokens](https://github.com/settings/tokens)
- [Guía de MCP de Cursor](https://cursor.sh/docs/mcp)

