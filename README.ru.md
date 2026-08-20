[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🛠️ Awesome Dev Tools

**Набор инструментов разработчика, о которых вы бы хотели узнать раньше. Более 50 инструментов, organized по категориям.**

Тщательно подобранная коллекция потрясающих инструментов разработчика для повышения продуктивности.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## До и После

```
❌ Без этих инструментов:                  ✅ С этими инструментами:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (медленно, рекурсивно, без цвета)          (в 10 раз быстрее, с цветом, учитывает .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (verboseный синтаксис, запоминание флагов)   (интуитивный, умные настройки по умолчанию)

$ git diff                                  $ git diff (delta)
  (обычный текст, сложно читать)              (подсветка синтаксиса, сравнение рядом)

$ cat config.json                           $ bat config.json
  (без подсветки синтаксиса)                  (подсветка синтаксиса + номера строк)

$ cd /very/long/path/to/project             $ z project
  (вводить полный путь каждый раз)            (умный переход к часто используемым директориям)
```

## 🚀 Быстрый старт: Если установить только 5 инструментов

Если времени мало, начните с этих пяти — они дают наибольший прирост продуктивности:

| # | Инструмент | Почему | Установка |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | Нечёткий поиск всего — файлов, истории, процессов | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git становится визуальным и интуитивным | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | Поиск кода в 10 раз быстрее grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | Автодополнение кода на основе ИИ | Установите расширение VS Code |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | Красивый и информативный промпт оболочки | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 Обзор инструментов

| Категория | Описание | Инструменты | Ссылка |
|----------|-------------|-------|------|
| 🔤 **Эмулятор терминала** | Эмуляторы терминала | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Инструменты Shell** | Улучшение оболочки | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **Продуктивность CLI** | Продуктивность командной строки | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | Расширения VS Code | Топ-20 расширений для языков, git, ИИ, тем, продуктивности | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Настройка Neovim | LazyVim, AstroNvim, NvChad, LSP, плагины, привязки клавиш | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **ИИ-ассистенты для кода** | ИИ-помощники в кодировании | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **ИИ-инструменты продуктивности** | Продуктивность с ИИ | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **Локальный ИИ** | Настройка локального ИИ | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Инструменты Git** | Продуктивность Git | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **Инструменты API** | Разработка API | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **Инструменты дизайна** | Дизайн для разработчиков | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **Скриншоты** | Скриншоты и документация | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 Избранные рекомендации

### Лучшая настройка терминала

```
Terminal:  WezTerm (cross-platform, Lua config)
Shell:     zsh + oh-my-zsh + zsh-autosuggestions
Prompt:    starship
Search:    fzf + ripgrep + fd
Modern:    bat + eza + delta
```

### Лучший стек ИИ-кодирования

```
Editor:    Cursor (or VS Code + Copilot)
CLI:       Claude Code / Kimi Code
Search:    Perplexity
Prototype: v0.dev
Local:     Ollama + Continue
```

### Лучший стек продуктивности

```
Git:       lazygit + pre-commit + commitlint
API:       Bruno (GUI) + httpie (CLI)
Shell:     tmux + direnv + asdf
Diagram:   Excalidraw + Mermaid
Screenshot: CleanShot X (macOS) / ShareX (Windows)
```

## 📖 Как использовать этот репозиторий

1. **Просматривайте по категориям** — нажимайте на ссылки в таблице выше
2. **Читайте сравнения** — в каждом файле есть таблица сравнения
3. **Быстрый старт** — следуйте инструкциям по установке
4. **Настройте** — скопируйте рекомендуемые конфигурации
5. **Итерируйте** — добавляйте по одному инструменту, освойте его перед добавлением нового

## 🤝 Участие

Приветствуются вклады! Пожалуйста, прочтите [Руководство по вкладу](CONTRIBUTING.md) сначала.

- 🐛 Сообщить об ошибке
- 💡 Предложить новый инструмент
- 📖 Улучшить документацию
- 🔧 Исправить опечатку

## 📄 Лицензия

Проект распространяется под лицензией MIT — подробности в файле [LICENSE](LICENSE).

## 🔗 Также посмотрите

Ознакомьтесь с этими родственными проектами:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** — Коллекция ИИ-навыков
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** — Правила и промпты для ИИ
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** — Проверьте «настроение» вашего проекта
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** — Сообщения коммитов на основе ИИ
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** — Коллекция MCP-серверов

---

<div align="center">

**[⬆ Наверх](#-awesome-dev-tools)**

</div>

---
