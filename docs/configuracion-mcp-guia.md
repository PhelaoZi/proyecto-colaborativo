# Configuración MCP (Model Context Protocol)

## 📁 Archivo: `configuracion-mcp.json`

Este archivo contiene la configuración para usar MCP (Model Context Protocol) servers con acceso al sistema de archivos.

## 🎯 ¿Qué hace esta configuración?

La configuración permite que Claude tenga acceso a:
- **Desktop:** `C:\Users\tu_usuario\Desktop`
- **Downloads:** `C:\Users\tu_usuario\Downloads`

## 🛠️ Cómo usar este archivo:

### Paso 1: Personalizar las rutas
**IMPORTANTE:** Antes de usar, debes cambiar `tu_usuario` por tu nombre de usuario real de Windows.

Por ejemplo, si tu usuario es "Juan", cambiar:
```json
"C:\\Users\\tu_usuario\\Desktop"
```
Por:
```json
"C:\\Users\\Juan\\Desktop"
```

### Paso 2: Ubicación del archivo
Este archivo de configuración debe colocarse en la ubicación específica que requiera tu aplicación de Claude o MCP client.

### Paso 3: Instalación de dependencias
El comando usa `npx` para instalar automáticamente:
```bash
@modelcontextprotocol/server-filesystem
```

## 📝 Estructura explicada:

```json
{
  "mcpServers": {                    // Configuración de servidores MCP
    "filesystem": {                  // Nombre del servidor (filesystem)
      "command": "npx",              // Comando para ejecutar
      "args": [                      // Argumentos del comando
        "-y",                        // Auto-confirmar instalación
        "@modelcontextprotocol/server-filesystem",  // Paquete a instalar
        "C:\\Users\\tu_usuario\\Desktop",          // Carpeta 1 con acceso
        "C:\\Users\\tu_usuario\\Downloads"        // Carpeta 2 con acceso
      ]
    }
  }
}
```

## ⚠️ Consideraciones de seguridad:
- Solo da acceso a las carpetas especificadas
- Asegúrate de que las rutas sean correctas
- No incluyas carpetas sensibles sin necesidad

## 🔧 Personalización:
Puedes agregar más carpetas añadiendo rutas adicionales en el array `args`:

```json
"args": [
  "-y",
  "@modelcontextprotocol/server-filesystem",
  "C:\\Users\\tu_usuario\\Desktop",
  "C:\\Users\\tu_usuario\\Downloads",
  "C:\\Users\\tu_usuario\\Documents\\MiProyecto"
]
```

---
*Última actualización: Junio 2025*