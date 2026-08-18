[中文版](README.zh.md)

<div align="center">

# 🛠️ Awesome Dev Tools

**The developer toolkit you wish you knew about earlier. 50+ tools, organized by category.**

A curated collection of awesome developer tools that boost productivity.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## Before vs After

```
❌ Without these tools:                    ✅ With these tools:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (slow, recursive, no color)                (10x faster, colored, respects .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (verbose syntax, memorize flags)            (intuitive, smart defaults)

$ git diff                                  $ git diff (delta)
  (plain text, hard to read)                  (syntax-highlighted, side-by-side)

$ cat config.json                           $ bat config.json
  (no syntax highlighting)                    (syntax highlighting + line numbers)

$ cd /very/long/path/to/project             $ z project
  (type full path every time)                 (smart jump to frequently used dirs)
```

## 🚀 Quick Start: If You Only Install 5 Tools

If you're short on time, start with these five — they provide the biggest productivity boost:

| # | Tool | Why | Install |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | Fuzzy search everything — files, history, processes | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git becomes visual and intuitive | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | Search code 10x faster than grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | AI-powered code completion | Install VS Code extension |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | Beautiful, informative shell prompt | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 Tools Overview

| Category | Description | Tools | Link |
|----------|-------------|-------|------|
| 🔤 **终端模拟器** | Terminal emulators | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Shell 工具** | Shell enhancement | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **CLI 效率** | CLI productivity | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | VS Code extensions | Top 20 extensions for language, git, AI, themes, productivity | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Neovim setup | LazyVim, AstroNvim, NvChad, LSP, plugins, keybindings | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **AI 编程助手** | AI coding assistants | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **AI 效率工具** | AI productivity | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **本地 AI** | Local AI setup | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Git 工具** | Git productivity | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **API 工具** | API development | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **设计工具** | Design for developers | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **截图工具** | Screenshot & docs | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 Featured Picks

### Best Terminal Setup

```
Terminal:  WezTerm (cross-platform, Lua config)
Shell:     zsh + oh-my-zsh + zsh-autosuggestions
Prompt:    starship
Search:    fzf + ripgrep + fd
Modern:    bat + eza + delta
```

### Best AI Coding Stack

```
Editor:    Cursor (or VS Code + Copilot)
CLI:       Claude Code / Kimi Code
Search:    Perplexity
Prototype: v0.dev
Local:     Ollama + Continue
```

### Best Productivity Stack

```
Git:       lazygit + pre-commit + commitlint
API:       Bruno (GUI) + httpie (CLI)
Shell:     tmux + direnv + asdf
Diagram:   Excalidraw + Mermaid
Screenshot: CleanShot X (macOS) / ShareX (Windows)
```

## 📖 How to Use This Repo

1. **Browse by category** - Click the links in the table above
2. **Read the comparison** - Each file has a comparison table
3. **Quick start** - Follow the installation instructions
4. **Configure** - Copy the recommended configurations
5. **Iterate** - Add one tool at a time, master it before adding more

## 🤝 Contributing

Contributions are welcome! Please read the [Contributing Guide](CONTRIBUTING.md) first.

- 🐛 Report a bug
- 💡 Suggest a new tool
- 📖 Improve documentation
- 🔧 Fix a typo

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 See Also

Check out these related projects:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - Curated AI skills collection
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - AI rules and prompts
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - Check your project's vibe
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - AI-powered commit messages
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - MCP server collection

---

<div align="center">

**[⬆ Back to top](#-awesome-dev-tools)**

</div>

---
