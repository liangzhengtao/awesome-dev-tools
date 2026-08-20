[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🛠️ Awesome Dev Tools

**O kit de ferramentas para desenvolvedores que você gostaria de ter conhecido antes. Mais de 50 ferramentas, organizadas por categoria.**

Uma coleção curada de ferramentas incríveis para desenvolvedores que impulsionam a produtividade.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## Antes vs Depois

```
❌ Sem essas ferramentas:                  ✅ Com essas ferramentas:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (lento, recursivo, sem cor)                (10x mais rápido, colorido, respeita .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (sintaxe verbosa, decorar flags)            (intuitivo, padrões inteligentes)

$ git diff                                  $ git diff (delta)
  (texto puro, difícil de ler)                (destaque de sintaxe, comparação lado a lado)

$ cat config.json                           $ bat config.json
  (sem destaque de sintaxe)                   (destaque de sintaxe + números de linha)

$ cd /very/long/path/to/project             $ z project
  (digitar caminho completo toda vez)         (salto inteligente para diretórios frequentes)
```

## 🚀 Início Rápido: Se Você Instalar Apenas 5 Ferramentas

Se estiver com pouco tempo, comece com estas cinco — oferecem o maior ganho de produtividade:

| # | Ferramenta | Por quê | Instalar |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | Busca fuzzy em tudo — arquivos, histórico, processos | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git se torna visual e intuitivo | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | Busca de código 10x mais rápida que grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | Autocompletar de código com IA | Instale a extensão do VS Code |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | Prompt de shell bonito e informativo | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 Visão Geral das Ferramentas

| Categoria | Descrição | Ferramentas | Link |
|----------|-------------|-------|------|
| 🔤 **Emulador de Terminal** | Emuladores de terminal | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Ferramentas Shell** | Melhoria do shell | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **Produtividade CLI** | Produtividade CLI | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | Extensões VS Code | Top 20 extensões para linguagens, git, IA, temas, produtividade | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Configuração Neovim | LazyVim, AstroNvim, NvChad, LSP, plugins, atalhos | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **Assistentes de Código IA** | Assistentes de código com IA | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **Ferramentas de Produtividade IA** | Produtividade com IA | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **IA Local** | Configuração de IA local | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Ferramentas Git** | Produtividade Git | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **Ferramentas API** | Desenvolvimento de API | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **Ferramentas de Design** | Design para desenvolvedores | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **Captura de Tela** | Capturas e documentação | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 Destaques

### Melhor Configuração de Terminal

```
Terminal:  WezTerm (cross-platform, Lua config)
Shell:     zsh + oh-my-zsh + zsh-autosuggestions
Prompt:    starship
Search:    fzf + ripgrep + fd
Modern:    bat + eza + delta
```

### Melhor Stack de Código com IA

```
Editor:    Cursor (or VS Code + Copilot)
CLI:       Claude Code / Kimi Code
Search:    Perplexity
Prototype: v0.dev
Local:     Ollama + Continue
```

### Melhor Stack de Produtividade

```
Git:       lazygit + pre-commit + commitlint
API:       Bruno (GUI) + httpie (CLI)
Shell:     tmux + direnv + asdf
Diagram:   Excalidraw + Mermaid
Screenshot: CleanShot X (macOS) / ShareX (Windows)
```

## 📖 Como Usar Este Repositório

1. **Navegue por categoria** - Clique nos links na tabela acima
2. **Leia a comparação** - Cada arquivo tem uma tabela comparativa
3. **Início rápido** - Siga as instruções de instalação
4. **Configure** - Copie as configurações recomendadas
5. **Itere** - Adicione uma ferramenta por vez, domine-a antes de adicionar mais

## 🤝 Contribuindo

Contribuições são bem-vindas! Leia o [Guia de Contribuição](CONTRIBUTING.md) primeiro.

- 🐛 Reportar um bug
- 💡 Sugerir uma nova ferramenta
- 📖 Melhorar a documentação
- 🔧 Corrigir um erro de digitação

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🔗 Veja Também

Confira estes projetos relacionados:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - Coleção curada de habilidades IA
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - Regras e prompts de IA
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - Verifique o clima do seu projeto
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - Mensagens de commit com IA
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - Coleção de servidores MCP

---

<div align="center">

**[⬆ Voltar ao topo](#-awesome-dev-tools)**

</div>

---
