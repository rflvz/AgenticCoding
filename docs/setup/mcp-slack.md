# Configuración MCP de Slack/Discord

Guía rápida para configurar el MCP (Model Context Protocol) de Slack o Discord en Cursor para notificaciones automáticas y reportes de issues.

## Requisitos Previos

- Cursor instalado
- Cuenta de Slack workspace o servidor de Discord
- Permisos para crear bots o webhooks

## Opción 1: Slack

### Configuración de Slack

#### 1. Crear Slack App

1. Ve a [api.slack.com/apps](https://api.slack.com/apps)
2. Clic en "Create New App" → "From scratch"
3. Nombre: "Cursor Agent Notifications"
4. Selecciona tu workspace

#### 2. Configurar Permisos OAuth

1. En la app, ve a "OAuth & Permissions"
2. Añade los siguientes Bot Token Scopes:
   - `chat:write` - Enviar mensajes
   - `chat:write.public` - Enviar mensajes a canales públicos
   - `channels:read` - Listar canales
   - `channels:join` - Unirse a canales

#### 3. Instalar App en Workspace

1. Ve a "Install App" en el menú lateral
2. Clic en "Install to Workspace"
3. Autoriza los permisos
4. Copia el "Bot User OAuth Token" (empieza con `xoxb-`)

#### 4. Instalar MCP de Slack en Cursor

1. Ve al [directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
2. Busca "Slack" en la lista de MCPs disponibles
3. Haz clic en el botón de instalación

#### 5. Configurar Token

1. Abre la configuración de Cursor (Settings)
2. Navega a **Features** → **Model Context Protocol**
3. Busca la configuración de "Slack" y añade:
   - `SLACK_BOT_TOKEN`: El token que copiaste (xoxb-...)
   - `SLACK_CHANNEL`: ID o nombre del canal (ej: `#dev-notifications`)

### Verificación

1. Reinicia Cursor
2. Abre un chat nuevo
3. Prueba: `@slack send message "Test desde Cursor"`

## Opción 2: Discord

### Configuración de Discord

#### 1. Crear Discord Bot

1. Ve a [discord.com/developers/applications](https://discord.com/developers/applications)
2. Clic en "New Application"
3. Nombre: "Cursor Agent Notifications"
4. Ve a "Bot" en el menú lateral
5. Clic en "Add Bot"
6. Copia el "Token" (bot token)

#### 2. Configurar Permisos del Bot

1. En "Bot", scroll hasta "Privileged Gateway Intents"
2. Habilita "MESSAGE CONTENT INTENT" (si necesitas leer mensajes)
3. En "OAuth2" → "URL Generator":
   - Selecciona scope: `bot`
   - Selecciona permisos: `Send Messages`, `Read Message History`
   - Copia la URL generada e invita el bot a tu servidor

#### 3. Instalar MCP de Discord en Cursor

1. Ve al [directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
2. Busca "Discord" en la lista de MCPs disponibles
3. Haz clic en el botón de instalación

#### 4. Configurar Token

1. Abre la configuración de Cursor (Settings)
2. Navega a **Features** → **Model Context Protocol**
3. Busca la configuración de "Discord" y añade:
   - `DISCORD_BOT_TOKEN`: El token del bot
   - `DISCORD_CHANNEL_ID`: ID del canal donde enviar notificaciones

### Verificación

1. Reinicia Cursor
2. Abre un chat nuevo
3. Prueba: `@discord send message "Test desde Cursor"`

## Funcionalidades Disponibles

### Notificaciones Automáticas

- Notificar cuando se crean issues en Linear
- Notificar cuando se completan issues
- Notificar cuando se crean PRs
- Reportes diarios/semanales de progreso

### Comandos de Mensajería

- Enviar mensajes personalizados
- Enviar reportes formateados
- Enviar actualizaciones de estado

## Workflows de Notificaciones

### Notificar Creación de Issue

```
Workflow: Notificar Issue Creado

1. Crear issue en Linear: @linear create issue "title"
2. Enviar notificación: @slack send message "✅ Nuevo issue creado: [title]\nLink: [url]"
```

### Reporte Diario

```
Workflow: Reporte Diario

1. Listar issues completados: @linear list issues --state "Done" --updated-after "today"
2. Generar reporte formateado
3. Enviar a Slack/Discord: @slack send message "[reporte formateado]"
```

### Notificar PR Listo para Review

```
Workflow: PR Listo para Review

1. Crear PR: @github create pull request "title"
2. Enviar notificación: @slack send message "🔍 PR listo para review: [title]\nLink: [url]"
```

## Agentes Especializados en Notificaciones

### Agente Notificador de Linear

```
Eres un agente especializado en notificaciones de Linear.

Tu función es:
- Monitorear cambios en issues de Linear
- Enviar notificaciones a Slack/Discord cuando:
  - Se crea un nuevo issue
  - Se completa un issue
  - Un issue cambia de prioridad
  - Se asignan issues

Reglas:
- Formatea mensajes de forma clara y legible
- Incluye links a los issues
- Usa emojis apropiados (✅, 🔍, ⚠️, etc.)
- Agrupa notificaciones cuando sea posible
```

### Agente de Reportes

```
Eres un agente especializado en generar reportes.

Tu función es:
- Generar reportes diarios/semanales de progreso
- Enviar reportes a Slack/Discord
- Formatear reportes de forma clara y visual

Reglas:
- Incluye métricas clave (issues completados, en progreso, bloqueados)
- Usa formato markdown para mejor legibilidad
- Destaca logros importantes
- Identifica bloqueos o problemas
```

## Comandos Útiles

### Slack

- `@slack send message "text"` - Enviar mensaje
- `@slack send message "text" --channel "#channel"` - Enviar a canal específico
- `@slack list channels` - Listar canales disponibles

### Discord

- `@discord send message "text"` - Enviar mensaje
- `@discord send message "text" --channel "channel_id"` - Enviar a canal específico
- `@discord list channels` - Listar canales disponibles

## Solución de Problemas

### El bot no envía mensajes

- Verifica que el token sea correcto
- Asegúrate de que el bot esté en el canal/servidor
- Verifica permisos del bot (debe tener permisos de escritura)
- Revisa que el nombre del canal sea correcto

### No puedo encontrar el canal

- Usa el ID del canal en lugar del nombre
- Verifica que el bot tenga acceso al canal
- En Slack, asegúrate de invitar el bot al canal

### Mensajes no se formatean correctamente

- Usa formato markdown estándar
- Verifica que el MCP soporte el formato que intentas usar
- Revisa la documentación del MCP específico

## Referencias

- [Directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
- [Slack API Documentation](https://api.slack.com/)
- [Discord Developer Portal](https://discord.com/developers/docs/intro)
- [Guía de MCP de Cursor](https://cursor.sh/docs/mcp)

