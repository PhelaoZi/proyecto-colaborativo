# Configuración GitHub MCP para Claude Desktop

Este archivo contiene la configuración necesaria para conectar Claude Desktop con GitHub usando Model Context Protocol (MCP).

## 📋 Prerrequisitos

1. **Claude Desktop** instalado y actualizado
2. **Node.js** instalado en tu sistema
3. **Token de GitHub** con permisos apropiados

## 🔑 Crear Token de GitHub

1. Ve a GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Clic en "Generate new token (classic)"
3. Selecciona estos permisos:
   - ✅ `repo` (acceso completo a repositorios)
   - ✅ `read:org` (leer organizaciones)
   - ✅ `user` (acceso a perfil de usuario)
4. Copia el token generado

## ⚙️ Instalación

### Paso 1: Ubicar archivo de configuración
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

### Paso 2: Configuración
Copia el contenido de `claude_desktop_config_github.json` y:

1. Reemplaza `"TU_TOKEN_AQUI"` por tu token real de GitHub
2. Guarda el archivo

### Paso 3: Reiniciar Claude Desktop
1. Cierra completamente Claude Desktop
2. Abre Claude Desktop
3. Busca el ícono de herramientas (🔨) en la parte inferior

## 🛠️ Funcionalidades Disponibles

Una vez instalado, tendrás acceso a estas herramientas:

### Repositorios
- `search_repositories` - Buscar repositorios
- `create_repository` - Crear nuevos repositorios
- `fork_repository` - Hacer fork de repositorios

### Archivos
- `get_file_contents` - Leer contenido de archivos
- `create_or_update_file` - Crear/actualizar archivos
- `push_files` - Subir múltiples archivos

### Ramas
- `create_branch` - Crear nuevas ramas
- `list_commits` - Ver historial de commits

### Issues y Pull Requests
- `create_issue` - Crear issues
- `create_pull_request` - Crear pull requests
- `list_issues` - Listar issues
- `get_pull_request` - Ver detalles de PR

### Búsqueda
- `search_code` - Buscar código
- `search_issues` - Buscar issues/PRs
- `search_users` - Buscar usuarios

## 💡 Ejemplos de Uso

```
# Buscar repositorios
"Busca mis repositorios en GitHub"

# Crear repositorio
"Crea un nuevo repositorio llamado 'mi-proyecto'"

# Ver archivo
"Muéstrame el contenido del README.md de mi repo 'proyecto-colaborativo'"

# Crear issue
"Crea un issue para agregar documentación"

# Buscar código
"Busca archivos Python en mis repositorios"
```

## 🔧 Configuración Combinada

Si quieres usar múltiples servidores MCP (GitHub + otros), puedes combinarlos:

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "tu_token_github"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/ruta/a/tu/directorio"]
    }
  }
}
```

## ⚠️ Notas de Seguridad

- **NUNCA** compartas tu token de GitHub
- Usa tokens con permisos mínimos necesarios
- Revoca tokens que no uses

## 🐛 Solución de Problemas

1. **No aparece el ícono de herramientas**:
   - Verifica la sintaxis JSON
   - Revisa que el token sea válido
   - Reinicia Claude Desktop completamente

2. **Error de conexión**:
   - Verifica que Node.js esté instalado
   - Prueba: `npx -y @modelcontextprotocol/server-github`

3. **Token inválido**:
   - Regenera el token en GitHub
   - Verifica los permisos seleccionados

---

📁 **Archivo de configuración**: `claude_desktop_config_github.json`  
📖 **Documentación oficial**: [Model Context Protocol](https://modelcontextprotocol.io/)
