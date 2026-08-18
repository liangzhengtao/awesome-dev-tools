# 终端模拟器 / Terminal Emulators

> 选择合适的终端模拟器可以极大提升开发体验。本文对比主流终端工具，帮助你找到最适合自己的那一款。

## Overview

终端是开发者每天接触最多的工具之一。一个好的终端模拟器应该具备：

- **高性能** - 快速渲染，低延迟
- **可定制** - 主题、字体、快捷键自由配置
- **跨平台** - 支持 macOS / Linux / Windows
- **现代化功能** - GPU 加速、多标签、分屏、图片预览

## Comparison Table

| Feature | Warp | Alacritty | Kitty | WezTerm | iTerm2 | Windows Terminal |
|---------|------|-----------|-------|---------|--------|-----------------|
| **GPU 加速** | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ |
| **跨平台** | ✅ | ✅ | ✅ | ✅ | ❌ macOS | ❌ Windows |
| **内置 AI** | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **分屏** | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ |
| **图片预览** | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ |
| **配置方式** | GUI | TOML | conf | Lua | GUI/JSON | JSON |
| **Shell 集成** | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ |
| **字体连字** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **开源** | 部分 | ✅ | ✅ | ✅ | ✅ | ✅ |
| **资源占用** | 中等 | 极低 | 低 | 低 | 中等 | 中等 |

## Quick Start

### Warp

```bash
# macOS / Linux
brew install --cask warp

# 首次启动会引导配置
# 支持团队协作、AI 命令建议
```

**亮点：** 内置 AI 辅助、现代化 UI、块级命令输出、团队协作功能。

### Alacritty

```bash
# macOS
brew install --cask alacritty

# Linux (Ubuntu/Debian)
sudo apt install alacritty

# Windows
winget install Alacritty.Alacritty
```

**配置文件路径：** `~/.config/alacritty/alacritty.toml`

```toml
[window]
padding = { x = 8, y = 8 }
opacity = 0.95

[font]
size = 14.0

[font.normal]
family = "JetBrainsMono Nerd Font"
style = "Regular"

[colors.primary]
background = "#1a1b26"
foreground = "#c0caf5"
```

### Kitty

```bash
# macOS
brew install --cask kitty

# Linux
curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin

# 配置文件
mkdir -p ~/.config/kitty
```

**配置文件路径：** `~/.config/kitty/kitty.conf`

```conf
font_family      JetBrainsMono Nerd Font
font_size        14.0
background_opacity 0.95
cursor_shape     beam

# 快捷键分屏
map ctrl+shift+d launch --location=vsplit
map ctrl+shift+e launch --location=hsplit

# 主题
include current-theme.conf
```

### WezTerm

```bash
# macOS
brew install --cask wezterm

# Linux
# 从 GitHub Releases 下载 .deb / .rpm

# Windows
winget install wez.wezterm
```

**配置文件路径：** `~/.wezterm.lua`

```lua
local wezterm = require 'wezterm'
local config = wezterm.config_builder()

config.font = wezterm.font('JetBrainsMono Nerd Font')
config.font_size = 14.0
config.color_scheme = 'Tokyo Night'
config.window_background_opacity = 0.95
config.enable_tab_bar = true

-- 快捷键
config.keys = {
  { key = 'd', mods = 'CTRL|SHIFT', action = wezterm.action.SplitHorizontal },
  { key = 'e', mods = 'CTRL|SHIFT', action = wezterm.action.SplitVertical },
}

return config
```

### iTerm2

```bash
# 仅 macOS
brew install --cask iterm2
```

**推荐配置：**
- Preferences → Profiles → Colors → 导入主题
- Preferences → Profiles → Text → 使用 Nerd Font
- 开启 GPU 渲染：Preferences → Profiles → Terminal → GPU Rendering
- 安装 Shell Integration：`curl -L https://iterm2.com/shell_integration/zsh -o ~/.iterm2_shell_integration.zsh`

### Windows Terminal

```powershell
# 通过 Microsoft Store 安装（推荐）
# 或使用 winget
winget install Microsoft.WindowsTerminal
```

**配置文件路径：** `%LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json`

```json
{
  "profiles": {
    "defaults": {
      "fontFace": "JetBrainsMono Nerd Font",
      "fontSize": 14,
      "opacity": 95,
      "colorScheme": "Tokyo Night"
    }
  },
  "schemes": [
    {
      "name": "Tokyo Night",
      "background": "#1A1B26",
      "foreground": "#C0CAF5"
    }
  ]
}
```

## Configuration Tips

### 通用字体推荐

```bash
# 安装 Nerd Font（图标字体，支持各种开发符号）
brew install font-jetbrains-mono-nerd-font
# 或
brew install font-fira-code-nerd-font
```

### 通用主题推荐

| 主题 | 风格 | 链接 |
|------|------|------|
| Tokyo Night | 深蓝暗色 | [theme](https://github.com/enkia/tokyo-night-vscode-theme) |
| Catppuccin | 柔和暖色 | [theme](https://github.com/catppuccin/catppuccin) |
| Dracula | 紫色暗色 | [theme](https://draculatheme.com) |
| Gruvbox | 复古暖色 | [theme](https://github.com/morhetz/gruvbox) |
| One Dark | Atom 风格 | [theme](https://github.com/atom/atom/blob/master/packages/one-dark-syntax) |

### 性能优化

```bash
# Alacritty / Kitty / WezTerm 都支持 GPU 渲染
# 确保显卡驱动是最新的

# 减少终端启动时间
# - 避免在 shell rc 中加载过多插件
# - 使用 lazy loading（懒加载）
# - zsh: 使用 zinit 的 ice 模式
```

## Tips

1. **跨平台首选：** WezTerm（Lua 配置，功能全面）或 Alacritty（极简高性能）
2. **macOS 首选：** Kitty（功能丰富）或 iTerm2（生态成熟）
3. **追求新体验：** Warp（AI 集成，现代化交互）
4. **Windows 首选：** Windows Terminal（系统集成）或 WezTerm
5. **极简主义者：** Alacritty（配置简单，启动极快）
6. **多路复用：** 配合 tmux 使用，终端崩溃不丢失会话

## See Also

- [Shell 工具](./shell-tools.md) - Shell 和命令行增强工具
- [CLI 效率工具](./cli-productivity.md) - 提升命令行效率的工具

---

## 中文版本

### 使用场景

- 需要选择一款适合日常开发的终端模拟器
- 想要 GPU 加速、多标签、分屏等现代化功能
- 需要跨平台支持（macOS/Linux/Windows）
- 希望终端支持 AI 辅助和团队协作

### 核心步骤

1. **选择终端** — 跨平台首选 WezTerm 或 Alacritty；macOS 首选 Kitty 或 iTerm2；Windows 首选 Windows Terminal
2. **安装 Nerd Font** — `brew install font-jetbrains-mono-nerd-font` 确保图标正确显示
3. **配置主题** — 推荐 Tokyo Night、Catppuccin、Dracula 等暗色主题
4. **启用 GPU 渲染** — 确保显卡驱动最新，Alacritty/Kitty/WezTerm 均支持
5. **优化启动速度** — shell rc 中使用 lazy loading 避免加载过多插件

### 模板说明

- Alacritty 配置 — TOML 格式，包含窗口透明度、字体、颜色主题
- Kitty 配置 — conf 格式，包含分屏快捷键和主题引用
- WezTerm 配置 — Lua 格式，包含分屏快捷键、主题、字体
- Windows Terminal 配置 — JSON 格式，包含字体、透明度、颜色方案

### 常见陷阱

1. **字体未安装** — 未安装 Nerd Font 导致图标显示为方块
2. **shell 插件过多** — rc 文件加载过多插件拖慢终端启动，使用 lazy loading
3. **GPU 渲染异常** — 显卡驱动过旧导致 GPU 加速终端渲染异常
4. **透明度导致可读性差** — 过度透明影响文字可读性，建议 opacity 0.9-0.95
5. **忽略 tmux 配合** — 终端崩溃会丢失会话，配合 tmux 使用可保持会话持久化
