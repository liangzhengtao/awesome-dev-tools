<div align="center">

# 🛠️ Awesome Dev Tools

**The developer toolkit you wish you knew about earlier. 50+ tools, organized by category.**

A curated collection of awesome developer tools that boost productivity.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

<div align="center">

[English](#english) | [中文](#中文)

</div>

</div>

---

<a name="english"></a>

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

<a name="中文"></a>

<div dir="rtl" align="center">

# 🛠️ 中文版

**你早该知道的开发者工具箱。50+ 工具，分类整理。**

精心策划的开发者工具集合，助你提升生产力。

</div>

---

## 使用前 vs 使用后

```
❌ 没有这些工具：                          ✅ 有了这些工具：
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  （慢，递归，无颜色）                        （快 10 倍，彩色，自动忽略 .gitignore）

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  （语法冗长，需要记参数）                     （直觉化，智能默认值）

$ git diff                                  $ git diff (delta)
  （纯文本，难以阅读）                         （语法高亮，并排对比）

$ cat config.json                           $ bat config.json
  （无语法高亮）                               （语法高亮 + 行号）

$ cd /very/long/path/to/project             $ z project
  （每次都输入完整路径）                        （智能跳转到常用目录）
```

## 🚀 快速开始：如果你只装 5 个工具

如果时间有限，从这五个开始——它们带来的效率提升最大：

| # | 工具 | 为什么选它 | 安装命令 |
|---|------|-----------|----------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | 模糊搜索一切——文件、历史、进程 | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git 操作变得可视化、直觉化 | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | 搜索代码比 grep 快 10 倍 | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | AI 驱动的代码补全 | 安装 VS Code 扩展 |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | 美观、信息丰富的 Shell 提示符 | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 工具总览

| 分类 | 描述 | 工具 | 链接 |
|------|------|------|------|
| 🔤 **终端模拟器** | 终端应用 | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Shell 工具** | Shell 增强 | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **CLI 效率** | 命令行效率 | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | VS Code 扩展 | 20 个必备扩展：语言、Git、AI、主题、效率 | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Neovim 配置 | LazyVim, AstroNvim, NvChad, LSP, 插件, 快捷键 | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **AI 编程助手** | AI 编程工具 | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **AI 效率工具** | AI 生产力 | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **本地 AI** | 本地 AI 部署 | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Git 工具** | Git 效率 | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **API 工具** | API 开发 | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **设计工具** | 开发者设计 | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **截图工具** | 截图和文档 | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 精选推荐

### 最佳终端配置

```
终端：    WezTerm（跨平台，Lua 配置）
Shell：   zsh + oh-my-zsh + zsh-autosuggestions
提示符：  starship
搜索：    fzf + ripgrep + fd
现代化：  bat + eza + delta
```

### 最佳 AI 编程组合

```
编辑器：  Cursor（或 VS Code + Copilot）
CLI：     Claude Code / Kimi Code
搜索：    Perplexity
原型：    v0.dev
本地：    Ollama + Continue
```

### 最佳效率工具组合

```
Git：     lazygit + pre-commit + commitlint
API：     Bruno（GUI）+ httpie（CLI）
Shell：   tmux + direnv + asdf
图表：    Excalidraw + Mermaid
截图：    CleanShot X（macOS）/ ShareX（Windows）
```

## 📖 如何使用本仓库

1. **按分类浏览** - 点击上方表格中的链接
2. **阅读对比** - 每个文件都有对比表格
3. **快速开始** - 按照安装说明操作
4. **配置** - 复制推荐的配置文件
5. **迭代** - 每次只添加一个工具，熟练后再加新的

## 🤝 贡献

欢迎贡献！请先阅读[贡献指南](CONTRIBUTING.md)。

- 🐛 报告 Bug
- 💡 推荐新工具
- 📖 改进文档
- 🔧 修复错别字

## 📄 许可证

本项目基于 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

## 🔗 相关项目

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - 精选 AI 技能集合
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - AI 规则和提示词
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - 检查项目状态
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - AI 驱动的提交信息
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - MCP 服务器集合

---

<div align="center">

**[⬆ 回到顶部](#-中文版)**

Made with ❤️ by [liangzhengtao](https://github.com/liangzhengtao)

</div>
