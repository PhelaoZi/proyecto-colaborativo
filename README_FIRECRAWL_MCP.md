# 🔥 Configuración MCP Firecrawl para Claude Desktop

## 👋 Para SCartens

Este repositorio contiene la configuración necesaria para instalar **MCP Firecrawl** en Claude Desktop.

---

## 📁 Archivos Incluidos

- **`claude_desktop_config_firecrawl.json`**: Configuración completa JSON para copiar y pegar

---

## 🚀 Instrucciones de Instalación

### **Paso 1: Obtener API Key de Firecrawl**
1. Ve a: https://www.firecrawl.dev/app/api-keys
2. Crea una cuenta gratuita
3. Genera una nueva API key (comenzará con `fc-`)

### **Paso 2: Localizar tu archivo de configuración**
Busca el archivo `claude_desktop_config.json` en:
- **Windows**: `%userprofile%\AppData\Roaming\Claude\claude_desktop_config.json`
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`

Puedes acceder rápido en Windows con:
1. Presiona `Windows + R`
2. Escribe: `%userprofile%\AppData\Roaming\Claude`
3. Enter

### **Paso 3: Agregar Firecrawl**

**Si YA tienes otros MCPs configurados:**
1. Abre tu archivo `claude_desktop_config.json` actual
2. Agrega SOLO esta sección dentro de `mcpServers`:

```json
"firecrawl": {
  "command": "npx",
  "args": ["-y", "firecrawl-mcp"],
  "env": {
    "FIRECRAWL_API_KEY": "fc-YOUR_API_KEY_HERE"
  }
}
```

**Ejemplo de cómo debe quedar:**
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/username/Desktop"]
    },
    "firecrawl": {
      "command": "npx",
      "args": ["-y", "firecrawl-mcp"],
      "env": {
        "FIRECRAWL_API_KEY": "fc-TU_API_KEY_AQUI"
      }
    }
  }
}
```

**Si NO tienes ningún MCP configurado:**
- Copia todo el contenido de `claude_desktop_config_firecrawl.json` de este repositorio

### **Paso 4: Reemplazar la API Key**
- Busca: `fc-YOUR_API_KEY_HERE`
- Reemplaza con tu API key real de Firecrawl

### **Paso 5: Guardar y reiniciar**
1. Guarda el archivo JSON
2. Cierra completamente Claude Desktop
3. Abre Claude Desktop nuevamente
4. Busca el ícono de herramientas MCP (slider icon)

---

## ✅ Verificación

1. Abre Claude Desktop
2. Busca el ícono deslizador en la interfaz
3. Deberías ver las herramientas de Firecrawl disponibles
4. Prueba con: *"Usa Firecrawl para buscar información sobre inteligencia artificial"*

---

## 🎯 ¿Qué te permite hacer Firecrawl?

- 🌐 **Scraping web** con JavaScript rendering
- 🔍 **Búsqueda inteligente** en internet  
- 📊 **Extracción de datos** estructurados
- 🚀 **Crawling completo** de sitios web
- 🧠 **Investigación profunda** automatizada
- 📱 **Análisis de contenido** en tiempo real

---

## 🔧 Solución de Problemas

### Si no funciona:
1. Verifica que Node.js esté instalado: `node --version`
2. Revisa los logs en: `%userprofile%\AppData\Roaming\Claude\logs\`
3. Prueba manualmente: `npx -y firecrawl-mcp`

### Mensaje de error común en Windows:
Si ves errores de variables de entorno, usa:
```cmd
cmd /c "set FIRECRAWL_API_KEY=tu-api-key && npx -y firecrawl-mcp"
```

---

## 📞 Contacto

Si tienes problemas con la instalación, contacta a PhelaoZi.

---

**✨ ¡Listo para usar Firecrawl con Claude Desktop! ✨**