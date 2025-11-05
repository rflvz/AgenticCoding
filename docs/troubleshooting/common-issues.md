# Solución de Problemas Comunes

Guía para resolver problemas comunes al usar agentes en Cursor.

## Problemas de Configuración

### 1. MCP no se conecta

**Síntoma**: El MCP no responde o no está disponible.

**Soluciones**:

1. Verifica que el MCP esté instalado:
   - Ve a Settings → Features → Model Context Protocol
   - Verifica que el MCP esté en la lista

2. Verifica el token de API:
   - Asegúrate de que el token sea correcto
   - Verifica que el token no haya expirado
   - Regenera el token si es necesario

3. Reinicia Cursor:
   - Cierra completamente Cursor
   - Vuelve a abrir Cursor
   - Intenta usar el MCP nuevamente

4. Verifica la configuración:
   - Revisa el archivo de configuración del MCP
   - Verifica que los paths sean correctos
   - Verifica que las variables de entorno estén configuradas

### 2. Comandos no disponibles

**Síntoma**: Los comandos del MCP no aparecen o no funcionan.

**Soluciones**:

1. Verifica que el MCP esté habilitado:
   - Ve a Settings → Features → Model Context Protocol
   - Asegúrate de que el MCP esté habilitado

2. Verifica el formato del comando:
   - Usa `@linear` antes de los comandos
   - Verifica que el comando sea correcto
   - Revisa la documentación del MCP

3. Verifica permisos:
   - Asegúrate de que el token tenga los permisos necesarios
   - Verifica que tengas acceso al recurso (equipo, proyecto, etc.)

4. Revisa la consola de Cursor:
   - Abre la consola de Cursor (View → Output)
   - Busca errores relacionados con el MCP
   - Revisa los logs para más información

## Problemas de Agentes

### 3. Agente no entiende el contexto

**Síntoma**: El agente no usa el contexto correctamente o no recuerda información previa.

**Soluciones**:

1. Proporciona contexto explícito:
   - Lee el archivo `.cursor/memory/agent-context.md`
   - Proporciona contexto al iniciar el chat
   - Incluye archivos relevantes en el chat

2. Actualiza el contexto:
   - Actualiza `.cursor/memory/agent-context.md` con información nueva
   - Actualiza `.cursor/memory/shared-context.md` si es relevante
   - Proporciona contexto actualizado al agente

3. Usa archivos de memoria:
   - Crea archivos de memoria para contexto persistente
   - Lee archivos de memoria al iniciar el chat
   - Actualiza archivos de memoria cuando cambie el contexto

### 4. Agente crea issues duplicados

**Síntoma**: El agente crea issues que ya existen.

**Soluciones**:

1. Busca issues similares antes de crear:
   - Pide al agente que busque issues similares primero
   - Usa `@linear search issues` para buscar
   - Verifica que no exista un issue similar

2. Actualiza el contexto:
   - Incluye información sobre issues existentes en el contexto
   - Actualiza `.cursor/memory/shared-context.md` con issues activos
   - Proporciona contexto de issues al agente

3. Usa reglas específicas:
   - Añade reglas al agente para buscar antes de crear
   - Usa `.cursorrules` para reglas específicas
   - Proporciona ejemplos de issues similares

### 5. Agente no sigue las reglas

**Síntoma**: El agente no sigue las reglas establecidas.

**Soluciones**:

1. Verifica las reglas:
   - Revisa `.cursorrules` para asegurarte de que las reglas sean claras
   - Verifica que las reglas estén en el lugar correcto
   - Asegúrate de que las reglas sean específicas

2. Proporciona reglas explícitas:
   - Proporciona reglas al iniciar el chat
   - Refuerza las reglas durante la conversación
   - Actualiza las reglas si es necesario

3. Usa ejemplos:
   - Proporciona ejemplos de cómo seguir las reglas
   - Muestra ejemplos de issues creados correctamente
   - Refiere a documentación con ejemplos

## Problemas de Contexto Compartido

### 6. Contexto compartido no se sincroniza

**Síntoma**: Los agentes no comparten contexto correctamente.

**Soluciones**:

1. Verifica el archivo de contexto compartido:
   - Verifica que `.cursor/memory/shared-context.md` exista
   - Revisa que el archivo esté actualizado
   - Verifica que el formato sea correcto

2. Lee el contexto compartido:
   - Proporciona instrucciones explícitas para leer el contexto
   - Incluye el archivo en el chat
   - Verifica que el agente lea el contexto

3. Actualiza el contexto:
   - Actualiza el contexto cuando cambie algo importante
   - Proporciona instrucciones para actualizar el contexto
   - Verifica que las actualizaciones se guarden

### 7. Contexto compartido está desactualizado

**Síntoma**: El contexto compartido no refleja el estado actual.

**Soluciones**:

1. Actualiza el contexto regularmente:
   - Actualiza cuando cambie el estado de un issue
   - Actualiza cuando se identifique un bloqueo
   - Actualiza cuando se haga una decisión importante

2. Usa instrucciones explícitas:
   - Proporciona instrucciones para actualizar el contexto
   - Verifica que las actualizaciones se realicen
   - Revisa el contexto después de actualizaciones

3. Automatiza actualizaciones:
   - Crea workflows para actualizar el contexto automáticamente
   - Usa agentes para mantener el contexto actualizado
   - Verifica que las actualizaciones se sincronicen

## Problemas de Workflows

### 8. Workflow no funciona correctamente

**Síntoma**: El workflow no se ejecuta como se espera.

**Soluciones**:

1. Verifica las dependencias:
   - Verifica que todas las dependencias estén completas
   - Verifica que los issues estén en el estado correcto
   - Verifica que los agentes estén disponibles

2. Revisa el workflow:
   - Revisa la documentación del workflow
   - Verifica que los pasos sean correctos
   - Ajusta el workflow según sea necesario

3. Verifica el contexto:
   - Verifica que el contexto compartido esté actualizado
   - Verifica que los agentes lean el contexto
   - Verifica que las actualizaciones se sincronicen

### 9. Agentes no coordinan correctamente

**Síntoma**: Los agentes no trabajan juntos como se espera.

**Soluciones**:

1. Usa un agente orquestador:
   - Crea un agente orquestador para coordinar
   - Asigna tareas claramente a cada agente
   - Monitorea el progreso de cada agente

2. Usa contexto compartido:
   - Asegúrate de que todos los agentes lean el contexto compartido
   - Actualiza el contexto cuando cambie algo importante
   - Verifica que las actualizaciones se sincronicen

3. Comunica claramente:
   - Proporciona instrucciones claras a cada agente
   - Establece dependencias claras entre tareas
   - Monitorea y ajusta según sea necesario

## Problemas de Performance

### 10. Agente es lento

**Síntoma**: El agente tarda mucho en responder.

**Soluciones**:

1. Optimiza el contexto:
   - Reduce el tamaño del contexto
   - Elimina información innecesaria
   - Usa contexto específico en lugar de contexto general

2. Divide tareas:
   - Divide tareas complejas en subtareas más pequeñas
   - Usa múltiples agentes para tareas paralelas
   - Optimiza workflows para reducir tiempo

3. Usa archivos de memoria:
   - Usa archivos de memoria para contexto persistente
   - Lee solo el contexto necesario
   - Actualiza el contexto solo cuando sea necesario

## Problemas de Métricas

### 11. Métricas no se registran

**Síntoma**: Las métricas no se están registrando correctamente.

**Soluciones**:

1. Verifica los archivos de métricas:
   - Verifica que `.cursor/metrics/` exista
   - Verifica que los archivos se creen correctamente
   - Verifica que el formato sea correcto

2. Registra métricas manualmente:
   - Registra métricas manualmente si es necesario
   - Usa un agente para registrar métricas
   - Actualiza archivos de métricas regularmente

3. Automatiza el registro:
   - Crea workflows para registrar métricas automáticamente
   - Usa agentes para registrar métricas
   - Verifica que las métricas se registren correctamente

## Debugging

### 12. Debugging de Agentes

**Herramientas**:

1. **Consola de Cursor**:
   - Abre la consola (View → Output)
   - Revisa logs para errores
   - Busca mensajes relacionados con agentes

2. **Archivos de Log**:
   - Revisa archivos de log si existen
   - Busca errores en logs
   - Analiza patrones en logs

3. **Contexto**:
   - Revisa archivos de contexto
   - Verifica que el contexto sea correcto
   - Ajusta el contexto según sea necesario

### 13. Debugging de Workflows

**Herramientas**:

1. **Verificación de Pasos**:
   - Verifica cada paso del workflow
   - Verifica que los pasos se ejecuten correctamente
   - Ajusta pasos según sea necesario

2. **Contexto Compartido**:
   - Verifica que el contexto compartido esté actualizado
   - Verifica que los agentes lean el contexto
   - Verifica que las actualizaciones se sincronicen

3. **Dependencias**:
   - Verifica que las dependencias estén completas
   - Verifica que los issues estén en el estado correcto
   - Verifica que los agentes estén disponibles

## Referencias

- Ver configuración de MCPs en `docs/setup/`
- Ver agentes expertos en `docs/agents/expert-agents.md`
- Ver gestión de memoria en `docs/agentization/memory-management.md`
- Ver workflows en `docs/workflows/`

