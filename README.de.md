[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🛠️ Awesome Dev Tools

**Das Entwickler-Toolkit, das Sie gerne früher gekannt hätten. Über 50 Tools, nach Kategorien sortiert.**

Eine kuratierte Sammlung großartiger Entwickler-Tools, die die Produktivität steigern.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## Vorher vs Nachher

```
❌ Ohne diese Tools:                     ✅ Mit diesen Tools:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (langsam, rekursiv, ohne Farbe)            (10x schneller, farbig, respektiert .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (umständliche Syntax, Flags merken)         (intuitive, intelligente Defaults)

$ git diff                                  $ git diff (delta)
  (Nurtext, schwer zu lesen)                  (Syntaxhervorhebung, nebeneinander)

$ cat config.json                           $ bat config.json
  (keine Syntaxhervorhebung)                  (Syntaxhervorhebung + Zeilennummern)

$ cd /very/long/path/to/project             $ z project
  (jedes Mal den vollständigen Pfad eingeben)  (intelligenter Sprung zu häufig genutzten Verzeichnissen)
```

## 🚀 Schnellstart: Wenn Sie nur 5 Tools installieren

Wenn Sie wenig Zeit haben, fangen Sie mit diesen fünf an — sie bieten den größten Produktivitätsgewinn:

| # | Tool | Warum | Installation |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | Fuzzy-Suche über alles — Dateien, Verlauf, Prozesse | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git wird visuell und intuitiv | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | Code-Suche 10x schneller als grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | KI-gestützte Code-Vervollständigung | VS Code-Erweiterung installieren |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | Schöner, informativer Shell-Prompt | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 Tools-Übersicht

| Kategorie | Beschreibung | Tools | Link |
|----------|-------------|-------|------|
| 🔤 **Terminalemulator** | Terminalemulatoren | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Shell-Tools** | Shell-Verbesserung | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **CLI-Produktivität** | CLI-Produktivität | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | VS Code-Erweiterungen | Top-20-Erweiterungen für Sprachen, Git, KI, Themes, Produktivität | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Neovim-Einrichtung | LazyVim, AstroNvim, NvChad, LSP, Plugins, Tastenkürzel | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **KI-Coding-Assistenten** | KI-Coding-Helfer | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **KI-Produktivitätstools** | KI-Produktivität | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **Lokale KI** | Lokale KI-Einrichtung | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Git-Tools** | Git-Produktivität | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **API-Tools** | API-Entwicklung | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **Designtools** | Design für Entwickler | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **Screenshot-Tools** | Screenshots & Dokumentation | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 Empfohlene Auswahl

### Beste Terminal-Einrichtung

```
Terminal:  WezTerm (cross-platform, Lua config)
Shell:     zsh + oh-my-zsh + zsh-autosuggestions
Prompt:    starship
Search:    fzf + ripgrep + fd
Modern:    bat + eza + delta
```

### Bester KI-Coding-Stack

```
Editor:    Cursor (or VS Code + Copilot)
CLI:       Claude Code / Kimi Code
Search:    Perplexity
Prototype: v0.dev
Local:     Ollama + Continue
```

### Bester Produktivitäts-Stack

```
Git:       lazygit + pre-commit + commitlint
API:       Bruno (GUI) + httpie (CLI)
Shell:     tmux + direnv + asdf
Diagram:   Excalidraw + Mermaid
Screenshot: CleanShot X (macOS) / ShareX (Windows)
```

## 📖 Verwendung dieses Repositories

1. **Nach Kategorie durchsuchen** — Klicken Sie auf die Links in der Tabelle oben
2. **Vergleich lesen** — Jede Datei enthält eine Vergleichstabelle
3. **Schnellstart** — Folgen Sie den Installationsanweisungen
4. **Konfigurieren** — Kopieren Sie die empfohlenen Konfigurationen
5. **Iterieren** — Fügen Sie jeweils ein Tool hinzu und meistern Sie es, bevor Sie weitere hinzufügen

## 🤝 Mitwirken

Beiträge sind willkommen! Bitte lesen Sie zuerst den [Beitragsleitfaden](CONTRIBUTING.md).

- 🐛 Einen Fehler melden
- 💡 Ein neues Tool vorschlagen
- 📖 Die Dokumentation verbessern
- 🔧 Einen Tippfehler korrigieren

## 📄 Lizenz

Dieses Projekt steht unter der MIT-Lizenz — Details finden Sie in der Datei [LICENSE](LICENSE).

## 🔗 Siehe auch

Schauen Sie sich diese verwandten Projekte an:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** — Kuratierte KI-Skills-Sammlung
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** — KI-Regeln und Prompts
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** — Überprüfen Sie die Stimmung Ihres Projekts
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** — KI-gesteuerte Commit-Nachrichten
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** — MCP-Server-Sammlung

---

<div align="center">

**[⬆ Zurück nach oben](#-awesome-dev-tools)**

</div>

---
