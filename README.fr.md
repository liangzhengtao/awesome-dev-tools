[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🛠️ Awesome Dev Tools

**La boîte à outils de développeur que vous auriez aimé découvrir plus tôt. 50+ outils, organisés par catégorie.**

Une collection soigneusement sélectionnée d'outils de développement pour booster votre productivité.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## Avant vs Après

```
❌ Sans ces outils :                       ✅ Avec ces outils :
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (lent, récursif, sans couleur)             (10x plus rapide, coloré, respecte .gitignore)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (syntaxe verbose, mémoriser les flags)       (intuitif, paramètres intelligents)

$ git diff                                  $ git diff (delta)
  (texte brut, difficile à lire)               (coloration syntaxique, côte à côte)

$ cat config.json                           $ bat config.json
  (pas de coloration syntaxique)               (coloration syntaxique + numéros de ligne)

$ cd /very/long/path/to/project             $ z project
  (taper le chemin complet à chaque fois)       (saut intelligent vers les répertoires fréquents)
```

## 🚀 Démarrage rapide : installez seulement 5 outils

Si vous manquez de temps, commencez par ceux-ci — ce sont les plus efficaces :

| # | Outil | Pourquoi | Installation |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | Recherche floue sur tout — fichiers, historique, processus | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git devient visuel et intuitif | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | Recherche de code 10x plus rapide que grep | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | Complétion de code par IA | Installer l'extension VS Code |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | Prompt shell élégant et informatif | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 Aperçu des outils

| Catégorie | Description | Outils | Lien |
|----------|-------------|-------|------|
| 🔤 **Émulateurs de terminal** | Applications terminal | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **Outils Shell** | Amélioration du shell | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **Productivité CLI** | Productivité en ligne de commande | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | Extensions VS Code | Top 20 extensions pour langage, git, IA, thèmes, productivité | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Configuration Neovim | LazyVim, AstroNvim, NvChad, LSP, plugins, raccourcis | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **Assistants IA de code** | Outils de programmation IA | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **Outils IA de productivité** | Productivité IA | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **IA locale** | Configuration IA locale | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Outils Git** | Productivité Git | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **Outils API** | Développement API | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **Outils de design** | Design pour développeurs | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **Capture d'écran** | Capture et documentation | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 Sélections phares

### Meilleure configuration terminal

```
Terminal :  WezTerm (multiplateforme, config Lua)
Shell :     zsh + oh-my-zsh + zsh-autosuggestions
Prompt :    starship
Recherche : fzf + ripgrep + fd
Moderne :   bat + eza + delta
```

### Meilleure pile IA de code

```
Éditeur :  Cursor (ou VS Code + Copilot)
CLI :      Claude Code / Kimi Code
Recherche : Perplexity
Prototype : v0.dev
Local :    Ollama + Continue
```

### Meilleure pile de productivité

```
Git :       lazygit + pre-commit + commitlint
API :       Bruno (GUI) + httpie (CLI)
Shell :     tmux + direnv + asdf
Diagramme : Excalidraw + Mermaid
Capture :   CleanShot X (macOS) / ShareX (Windows)
```

## 📖 Comment utiliser ce dépôt

1. **Parcourir par catégorie** - Cliquez sur les liens dans le tableau ci-dessus
2. **Consulter les comparaisons** - Chaque fichier contient un tableau comparatif
3. **Démarrage rapide** - Suivez les instructions d'installation
4. **Configurer** - Copiez les configurations recommandées
5. **Itérer** - Ajoutez un outil à la fois, maîtrisez-le avant d'en ajouter un autre

## 🤝 Contribuer

Les contributions sont les bienvenues ! Veuillez d'abord lire le [guide de contribution](CONTRIBUTING.md).

- 🐛 Signaler un bug
- 💡 Suggérer un nouvel outil
- 📖 Améliorer la documentation
- 🔧 Corriger une coquille

## 📄 Licence

Ce projet est sous licence MIT — voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 🔗 Voir aussi

Découvrez ces projets connexes :

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - Collection de compétences IA
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - Règles et prompts IA
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - Vérifiez l'état de votre projet
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - Messages de commit par IA
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - Collection de serveurs MCP

---

<div align="center">

**[⬆ Retour en haut](#-awesome-dev-tools)**

</div>

---
