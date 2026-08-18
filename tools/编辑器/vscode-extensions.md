# VS Code 扩展 / Essential VS Code Extensions

> VS Code 是目前最流行的代码编辑器。通过精选扩展，你可以将其打造成强大的开发环境。

## Overview

VS Code 扩展市场有超过 40,000 个扩展，但安装过多会拖慢编辑器。本文精选 **20 个必备扩展**，覆盖语言支持、Git、AI、主题、效率提升五大类别。

## Top 20 Extensions

### 语言支持 (Language Support)

| # | Extension | ID | Description |
|---|-----------|-----|-------------|
| 1 | **Python** | `ms-python.python` | Python 语言支持、调试、linting、格式化 |
| 2 | **Pylance** | `ms-python.vscode-pylance` | Python 高性能语言服务器 |
| 3 | **TypeScript / JavaScript** | 内置 | TS/JS 支持，无需额外安装 |
| 4 | **ESLint** | `dbaeumer.vscode-eslint` | JavaScript/TypeScript 代码检查 |
| 5 | **Prettier** | `esbenp.prettier-vscode` | 多语言代码格式化器 |
| 6 | **Rust Analyzer** | `rust-lang.rust-analyzer` | Rust 语言支持和分析 |
| 7 | **Go** | `golang.go` | Go 语言全套支持 |

**Python 推荐配置：**

```json
{
  "python.defaultInterpreterPath": "${workspaceFolder}/.venv/bin/python",
  "python.analysis.typeCheckingMode": "basic",
  "python.linting.enabled": true,
  "python.linting.pylintEnabled": true,
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.formatOnSave": true
  }
}
```

**Prettier 推荐配置：**

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "prettier.semi": true,
  "prettier.singleQuote": true,
  "prettier.tabWidth": 2,
  "prettier.trailingComma": "es5"
}
```

### Git 工具 (Git)

| # | Extension | ID | Description |
|---|-----------|-----|-------------|
| 8 | **GitLens** | `eamodio.gitlens` | Git 增强：行内 blame、历史、比较 |
| 9 | **Git Graph** | `mhutchie.git-graph` | 可视化 Git 分支图 |
| 10 | **Conventional Commits** | `vivaxy.vscode-conventional-commits` | 规范化提交信息 |

**GitLens 推荐配置：**

```json
{
  "gitlens.hovers.currentLine.over": "line",
  "gitlens.codeLens.enabled": true,
  "gitlens.currentLine.enabled": true,
  "gitlens.hovers.enabled": true
}
```

### AI 工具 (AI)

| # | Extension | ID | Description |
|---|-----------|-----|-------------|
| 11 | **GitHub Copilot** | `GitHub.copilot` | AI 代码补全和生成 |
| 12 | **GitHub Copilot Chat** | `GitHub.copilot-chat` | AI 对话式编程助手 |
| 13 | **Continue** | `Continue.continue` | 开源 AI 编程助手（支持多模型） |
| 14 | **Cody** | `sourcegraph.cody-ai` | Sourcegraph AI 编程助手 |

**Copilot 使用技巧：**

```python
# 1. 写清晰的注释，Copilot 会生成代码
# Calculate the Fibonacci sequence up to n terms
def fibonacci(n):
    # Copilot 会自动补全实现

# 2. 用 Tab 接受建议，Esc 拒绝
# 3. Ctrl+Enter 查看多个建议
# 4. 在 Copilot Chat 中用 /explain 解释代码
# 5. 用 /fix 修复错误
# 6. 用 /tests 生成测试
```

### 主题和外观 (Themes)

| # | Extension | ID | Description |
|---|-----------|-----|-------------|
| 15 | **One Dark Pro** | `zhuangtongfa.material-theme` | Atom 风格暗色主题 |
| 16 | **Catppuccin** | `Catppuccin.catppuccin-vsc` | 柔和暖色主题 |
| 17 | **Tokyo Night** | `enkia.tokyo-night` | 深蓝暗色主题 |

**图标主题推荐：**

```json
{
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorTheme": "Tokyo Night"
}
```

推荐安装 `PKief.material-icon-theme` - Material 图标主题。

### 效率工具 (Productivity)

| # | Extension | ID | Description |
|---|-----------|-----|-------------|
| 18 | **Error Lens** | `usernamehw.errorlens` | 行内显示错误和警告 |
| 19 | **Todo Tree** | `Gruntfuggly.todo-tree` | 高亮和汇总 TODO/FIXME |
| 20 | **Remote - SSH** | `ms-vscode-remote.remote-ssh` | SSH 远程开发 |

**Error Lens 效果：**
- 错误信息直接显示在代码行末尾，无需 hover
- 警告以黄色高亮，错误以红色高亮
- 大幅减少查找错误的时间

## Quick Start

### 一键安装推荐扩展

```bash
# 通过命令行安装所有推荐扩展
code --install-extension ms-python.python
code --install-extension ms-python.vscode-pylance
code --install-extension dbaeumer.vscode-eslint
code --install-extension esbenp.prettier-vscode
code --install-extension rust-lang.rust-analyzer
code --install-extension golang.go
code --install-extension eamodio.gitlens
code --install-extension mhutchie.git-graph
code --install-extension vivaxy.vscode-conventional-commits
code --install-extension GitHub.copilot
code --install-extension GitHub.copilot-chat
code --install-extension zhuangtongfa.material-theme
code --install-extension Catppuccin.catppuccin-vsc
code --install-extension enkia.tokyo-night
code --install-extension PKief.material-icon-theme
code --install-extension usernamehw.errorlens
code --install-extension Gruntfuggly.todo-tree
code --install-extension ms-vscode-remote.remote-ssh
```

### settings.json 完整推荐配置

```json
{
  // 外观
  "workbench.colorTheme": "Tokyo Night",
  "workbench.iconTheme": "material-icon-theme",
  "editor.fontSize": 14,
  "editor.fontFamily": "'JetBrainsMono Nerd Font', 'Fira Code', monospace",
  "editor.fontLigatures": true,
  "editor.lineHeight": 1.6,
  "editor.cursorBlinking": "smooth",
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.smoothScrolling": true,
  "editor.minimap.enabled": false,
  "editor.bracketPairColorization.enabled": true,

  // 编辑
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit",
    "source.organizeImports": "explicit"
  },
  "editor.suggestSelection": "first",
  "editor.wordWrap": "on",
  "editor.tabSize": 2,
  "editor.renderWhitespace": "trailing",

  // 终端
  "terminal.integrated.fontFamily": "'JetBrainsMono Nerd Font'",
  "terminal.integrated.fontSize": 13,
  "terminal.integrated.defaultProfile.linux": "zsh",
  "terminal.integrated.defaultProfile.osx": "zsh",

  // 文件
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 1000,
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,

  // Git
  "git.autofetch": true,
  "git.confirmSync": false,
  "git.enableSmartCommit": true
}
```

## Configuration

### Settings Sync 设置

1. 打开 VS Code
2. `Ctrl+Shift+P` → "Turn on Settings Sync"
3. 选择要同步的内容：
   - ✅ Settings（设置）
   - ✅ Keybindings（快捷键）
   - ✅ Extensions（扩展）
   - ✅ UI State（界面状态）
4. 使用 GitHub 或 Microsoft 账号登录

### Workspace 推荐扩展

在项目根目录创建 `.vscode/extensions.json`：

```json
{
  "recommendations": [
    "esbenp.prettier-vscode",
    "dbaeumer.vscode-eslint",
    "ms-python.python",
    "eamodio.gitlens",
    "usernamehw.errorlens"
  ],
  "unwantedRecommendations": [
    "hookyqr.beautify"
  ]
}
```

## Tips

1. **不要装太多扩展** - 超过 30 个扩展会明显影响启动速度
2. **用 `Ctrl+Shift+P`** - 命令面板是 VS Code 的核心，记住常用命令
3. **多光标编辑** - `Alt+Click` 添加光标，`Ctrl+D` 选择下一个匹配
4. **代码片段** - 创建自定义 snippets 提升编码速度
5. **工作区设置** - 项目级设置覆盖全局设置，适合团队统一配置
6. **性能检查** - `Ctrl+Shift+P` → "Developer: Show Running Extensions" 查看扩展性能

## See Also

- [Neovim 配置指南](./neovim-setup.md) - 如果你想尝试终端编辑器
- [AI 编程助手](../AI工具/ai-coding-assistants.md) - 更多 AI 编程工具

---

## 中文版本

### 使用场景

- 精选 VS Code 必备扩展，避免安装过多拖慢编辑器
- 配置 Python、TypeScript、Rust、Go 等语言支持
- 集成 AI 编程助手（Copilot、Continue、Cody）
- 统一团队的编辑器配置和代码风格

### 核心步骤

1. **语言支持** — Python + Pylance + Black formatter，ESLint + Prettier 用于 JS/TS
2. **Git 工具** — GitLens（行内 blame + 历史）、Git Graph（可视化分支图）、Conventional Commits
3. **AI 工具** — GitHub Copilot（代码补全）+ Copilot Chat（对话式编程），或开源替代 Continue
4. **主题和图标** — Tokyo Night 主题 + Material Icon Theme 图标包
5. **效率工具** — Error Lens（行内显示错误）、Todo Tree（TODO 汇总）、Remote SSH（远程开发）

### 模板说明

- settings.json 完整推荐配置 — 外观、编辑、终端、文件、Git 全面优化
- 一键安装脚本 — 命令行批量安装所有推荐扩展
- .vscode/extensions.json — 工作区推荐扩展配置，统一团队环境

### 常见陷阱

1. **扩展过多** — 超过 30 个扩展会明显影响启动速度
2. **格式化冲突** — Prettier 和 ESLint 格式化规则冲突，需正确配置 `editor.codeActionsOnSave`
3. **Settings Sync 泄露** — 同步设置时可能泄露个人 API key 到其他设备
4. **Copilot 生成代码需审查** — 不要盲目接受 AI 建议，理解每一行代码
5. **Remote SSH 扩展性能** — 网络延迟影响远程开发体验，建议使用稳定网络
