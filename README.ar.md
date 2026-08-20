[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div dir="rtl" align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div dir="rtl" align="center">

# 🛠️ أدوات التطوير الرائعة

**مجموعة أدوات المطورين التي تمنيت لو عرفتها سابقًا. أكثر من 50 أداة، مصنّفة حسب الفئة.**

مجموعة منتقاة من أدوات التطوير الرائعة التي تعزز الإنتاجية.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## قبل وبعد

```
❌ بدون هذه الأدوات:                    ✅ مع هذه الأدوات:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (بطيء، تكراري، بدون ألوان)                (أسرع بـ 10 مرات، ملوّن، يحترم .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (صيغة مطوّلة، احفظ العلامات)               (بديهي، إعدادات ذكية افتراضية)

$ git diff                                  $ git diff (delta)
  (نص عادي، صعب القراءة)                    ((Syntax-highlighted، جنبًا إلى جنب

$ cat config.json                           $ bat config.json
  (بدون تمييز صيغي)                           (تمييز صيغي + أرقام الأسطر)

$ cd /very/long/path/to/project             $ z project
  (اكتب المسار الكامل في كل مرة)            (انتقال ذكي للمجلدات المستخدمة frequently)
```

## 🚀 البدء السريع: إذا كنت ستثبّت 5 أدوات فقط

إذا كنت ضيق الوقت، ابدأ بهذه الخمسة — توفر أكبر قفزة في الإنتاجية:

| # | الأداة | السبب | التثبيت |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | بحث ضبابي شامل — الملفات، السجل، العمليات | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git يصبح بصريًا وبديهيًا | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | بحث في الشفرة أسرع بـ 10 مرات من grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | إكمال شفرة مدعوم بالذكاء الاصطناعي | ثبّت إضافة VS Code |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | موجه شلّ جميل ومفيد | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 نظرة عامة على الأدوات

| الفئة | الوصف | الأدوات | الرابط |
|----------|-------------|-------|------|
| 🔤 **محاكي الطرفية** | محاكيات الطرفية | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **أدوات Shell** | تحسين Shell | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **كفاءة CLI** | إنتاجية واجهة سطر الأوامر | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | إضافات VS Code | أفضل 20 إضافة للغات، git، AI، السمات، الإنتاجية | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | إعداد Neovim | LazyVim, AstroNvim, NvChad, LSP, الإضافات، روابط المفاتيح | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **مساعدو البرمجة بالـ AI** | مساعدو البرمجة بالذكاء الاصطناعي | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **أدوات إنتاجية AI** | إنتاجية الذكاء الاصطناعي | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **AI المحلي** | إعداد AI المحلي | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **أدوات Git** | إنتاجية Git | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **أدوات API** | تطوير API | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **أدوات التصميم** | التصميم للمطورين | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **أدوات لقطات الشاشة** | لقطات الشاشة والتوثيق | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 اختيارات مميزة

### أفضل إعداد للطرفية

```
Terminal:  WezTerm (cross-platform, Lua config)
Shell:     zsh + oh-my-zsh + zsh-autosuggestions
Prompt:    starship
Search:    fzf + ripgrep + fd
Modern:    bat + eza + delta
```

### أفضل حزمة برمجة AI

```
Editor:    Cursor (or VS Code + Copilot)
CLI:       Claude Code / Kimi Code
Search:    Perplexity
Prototype: v0.dev
Local:     Ollama + Continue
```

### أفضل حزمة إنتاجية

```
Git:       lazygit + pre-commit + commitlint
API:       Bruno (GUI) + httpie (CLI)
Shell:     tmux + direnv + asdf
Diagram:   Excalidraw + Mermaid
Screenshot: CleanShot X (macOS) / ShareX (Windows)
```

## 📖 كيفية استخدام هذا المستودع

1. **تصفّح حسب الفئة** - انقر على الروابط في الجدول أعلاه
2. **اقرأ المقارنة** - كل ملف يحتوي على جدول مقارنة
3. **البدء السريع** - اتبع تعليمات التثبيت
4. **الإعداد** - انسخ التوصيات المُعدّة
5. **التكرار** - أضف أداة واحدة في كل مرة، وأتقنها قبل إضافة المزيد

## 🤝 المساهمة

نرحب بالمسايرات! يرجى قراءة [دليل المساهمة](CONTRIBUTING.md) أولاً.

- 🐛 الإبلاغ عن خطأ
- 💡 اقتراح أداة جديدة
- 📖 تحسين التوثيق
- 🔧 تصحيح خطأ إملائي

## 📄 الترخيص

هذا المشروع مرخص بموجب ترخيص MIT - راجع ملف [LICENSE](LICENSE) للتفاصيل.

## 🔗 انظر أيضًا

اطلع على هذه المشاريع ذات الصلة:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - مجموعة مهارات AI منتقاة
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - قواعد ونماذج AI
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - تحقق من أجواء مشروعك
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - رسائل commit مدعومة بالـ AI
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - مجموعة خوادم MCP

---

<div dir="rtl" align="center">

**[⬆ العودة للأعلى](#-awesome-dev-tools)**

</div>

---
