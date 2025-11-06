# Configuración MCP de Linear

Guía rápida para configurar el MCP (Model Context Protocol) de Linear en Cursor.

## Requisitos Previos

- Cursor instalado
- Cuenta de Linear activa

## Pasos de Configuración

### Instalar MCP de Linear

1. Ve al [directorio de MCPs de Cursor](https://cursor.com/docs/context/mcp/directory)
2. Busca "Linear" en la lista de MCPs disponibles
3. Haz clic en el botón de instalación para añadir automáticamente el MCP de Linear

El MCP se configurará automáticamente. Cursor manejará el login automáticamente a través de un login en la web cuando instales el MCP desde el directorio de MCPs. **No necesitas obtener ni configurar ningún token manualmente.**

## Verificación

1. Reinicia Cursor
2. Abre un chat nuevo
3. Prueba el comando: `@linear list issues`
4. Deberías ver tus issues de Linear

## Solución de Problemas

### El MCP no se conecta

- Verifica que el login se haya completado correctamente en la web
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

