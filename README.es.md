[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🛠️ Awesome Dev Tools

**La caja de herramientas de desarrollador que desearías haber conocido antes. 50+ herramientas, organizadas por categoría.**

Una colección curada de herramientas de desarrollo que impulsan la productividad.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## Antes vs Después

```
❌ Sin estas herramientas:                 ✅ Con estas herramientas:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (lento, recursivo, sin color)              (10x más rápido, con color, respeta .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (sintaxis verbosa, memorizar flags)          (intuitivo, valores predeterminados inteligentes)

$ git diff                                  $ git diff (delta)
  (texto plano, difícil de leer)               (resaltado de sintaxis, vista lado a lado)

$ cat config.json                           $ bat config.json
  (sin resaltado de sintaxis)                  (resaltado de sintaxis + números de línea)

$ cd /very/long/path/to/project             $ z project
  (escribir ruta completa cada vez)            (salto inteligente a directorios frecuentes)
```

## 🚀 Inicio rápido: si solo instalas 5 herramientas

Si tienes poco tiempo, empieza con estas cinco — son las que más productividad aportan:

| # | Herramienta | Por qué | Instalación |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | Búsqueda difusa de todo — archivos, historial, procesos | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git se vuelve visual e intuitivo | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | Búsqueda de código 10x más rápida que grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | Autocompletado de código con IA | Instalar extensión de VS Code |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | Prompt de shell elegante e informativo | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 Resumen de herramientas

| Categoría | Descripción | Herramientas | Enlace |
|----------|-------------|-------|------|
| 🔤 **Emuladores de terminal** | Aplicaciones de terminal | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Herramientas Shell** | Mejora del shell | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **Productividad CLI** | Productividad en línea de comandos | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | Extensiones de VS Code | Top 20 extensiones para lenguaje, git, IA, temas, productividad | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Configuración de Neovim | LazyVim, AstroNvim, NvChad, LSP, plugins, atajos de teclado | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **Asistentes IA de código** | Herramientas de programación IA | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **Herramientas IA de productividad** | Productividad con IA | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **IA local** | Configuración de IA local | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Herramientas Git** | Productividad Git | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **Herramientas API** | Desarrollo de API | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **Herramientas de diseño** | Diseño para desarrolladores | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **Capturas de pantalla** | Capturas y documentación | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 Selecciones destacadas

### Mejor configuración de terminal

```
Terminal : WezTerm (multiplataforma, configuración Lua)
Shell :    zsh + oh-my-zsh + zsh-autosuggestions
Prompt :   starship
Búsqueda : fzf + ripgrep + fd
Moderno :  bat + eza + delta
```

### Mejor stack de IA para código

```
Editor :    Cursor (o VS Code + Copilot)
CLI :       Claude Code / Kimi Code
Búsqueda :  Perplexity
Prototipo : v0.dev
Local :     Ollama + Continue
```

### Mejor stack de productividad

```
Git :       lazygit + pre-commit + commitlint
API :       Bruno (GUI) + httpie (CLI)
Shell :     tmux + direnv + asdf
Diagrama :  Excalidraw + Mermaid
Captura :   CleanShot X (macOS) / ShareX (Windows)
```

## 📖 Cómo usar este repositorio

1. **Explorar por categoría** - Haz clic en los enlaces de la tabla superior
2. **Leer la comparación** - Cada archivo tiene una tabla comparativa
3. **Inicio rápido** - Sigue las instrucciones de instalación
4. **Configurar** - Copia las configuraciones recomendadas
5. **Iterar** - Añade una herramienta a la vez, domínala antes de añadir otra

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Por favor lee primero la [Guía de contribución](CONTRIBUTING.md).

- 🐛 Reportar un bug
- 💡 Sugerir una nueva herramienta
- 📖 Mejorar la documentación
- 🔧 Corregir un error tipográfico

## 📄 Licencia

Este proyecto está bajo la licencia MIT — ver el archivo [LICENSE](LICENSE) para más detalles.

## 🔗 Ver también

Consulta estos proyectos relacionados:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - Colección de habilidades IA
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - Reglas y prompts de IA
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - Verifica el estado de tu proyecto
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - Mensajes de commit con IA
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - Colección de servidores MCP

---

<div align="center">

**[⬆ Volver arriba](#-awesome-dev-tools)**

</div>

---
