# Configuración MCP de Linear

Guía rápida para configurar el MCP (Model Context Protocol) de Linear en Cursor.

## Requisitos Previos

- Cursor instalado
- Cuenta de Linear activa
- Token de API de Linear

## Pasos de Configuración

### 1. Obtener Token de Linear

1. Ve a Linear → Settings → API
2. Genera un nuevo Personal API Key
3. Copia el token (solo se muestra una vez)

### 2. Instalar MCP de Linear

1. Ve al [directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
2. Busca "Linear" en la lista de MCPs disponibles
3. Haz clic en el botón de instalación para añadir automáticamente el MCP de Linear

El MCP se configurará automáticamente. Solo necesitarás añadir tu token de API en el siguiente paso.

### 3. Configurar Token de API

Una vez instalado el MCP, necesitas configurar tu token de Linear:

1. Abre la configuración de Cursor (Settings)
2. Navega a **Features** → **Model Context Protocol**
3. Busca la configuración de "Linear" y añade tu token:
   - En el campo `LINEAR_API_KEY`, pega el token que copiaste en el paso 1

## Verificación

1. Reinicia Cursor
2. Abre un chat nuevo
3. Prueba el comando: `@linear list issues`
4. Deberías ver tus issues de Linear

## Solución de Problemas

### El MCP no se conecta

- Verifica que el token sea correcto
- Revisa que el path de configuración sea correcto
- Reinicia Cursor completamente

### Comandos no disponibles

- Verifica que el MCP esté habilitado en Settings
- Comprueba la consola de Cursor para errores
- Asegúrate de usar `@linear` antes de los comandos

## Referencias

- [Directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory) - Instala MCPs directamente desde aquí
- [Documentación oficial de Linear MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/linear)
- [Guía de MCP de Cursor](https://cursor.sh/docs/mcp)

