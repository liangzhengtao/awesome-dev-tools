# Shell 工具 / Shell Tools

> Shell 是开发者与系统交互的核心界面。通过以下工具，你可以将默认 shell 打造成高效、美观、智能的开发环境。

## Overview

默认的 bash/zsh 只是起点。通过组合现代 shell 工具，你可以获得：

- **智能补全** - 命令、路径、选项自动补全
- **模糊搜索** - 模糊匹配文件、命令历史、进程
- **现代替代** - 更好的 `ls`、`cat`、`grep`、`find`
- **美观提示符** - 显示 git 状态、语言版本、执行时间

## Comparison Table

| Tool | 替代 | 核心功能 | 语言 | 性能 |
|------|------|----------|------|------|
| **zsh + oh-my-zsh** | bash | 框架 + 插件生态 | Shell | 中 |
| **fish** | bash/zsh | 开箱即用的智能 shell | Rust/C++ | 快 |
| **starship** | PS1/PROMPT | 跨 shell 提示符 | Rust | 极快 |
| **zoxide** | cd | 智能目录跳转 | Rust | 极快 |
| **fzf** | - | 模糊搜索一切 | Go | 极快 |
| **ripgrep** | grep | 更快的文本搜索 | Rust | 极快 |
| **fd** | find | 更友好的文件查找 | Rust | 极快 |
| **bat** | cat | 带语法高亮的 cat | Rust | 快 |
| **eza** | ls | 现代化的 ls | Rust | 快 |
| **delta** | diff | 美观的 diff 查看器 | Rust | 快 |
| **bottom** | top/htop | 系统监控仪表盘 | Rust | 快 |

## Quick Start

### zsh + oh-my-zsh

```bash
# 安装 zsh（macOS 已预装）
sudo apt install zsh  # Ubuntu/Debian

# 安装 oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# 推荐插件
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-completions
```

**配置 `~/.zshrc`：**

```zsh
ZSH_THEME="powerlevel10k/powerlevel10k"

plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
  zsh-completions
  z
  docker
  kubectl
)
```

### fish (Friendly Interactive Shell)

```bash
# 安装
brew install fish          # macOS
sudo apt install fish      # Ubuntu/Debian

# 设为默认 shell
chsh -s /usr/local/bin/fish

# 安装 Fisher（插件管理器）
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher

# 推荐插件
fisher install jethrokuan/z          # 目录跳转
fisher install PatrickF1/fzf.fish    # fzf 集成
fisher install ilancosman/tide       # 类似 starship 的提示符
```

**fish 特色：**

```fish
# 自动建议 - 根据历史和补全实时提示
# 输入部分命令，灰色建议自动出现，按 → 接受

# 语法高亮 - 内置，无需插件
# 命令有效=绿色，无效=红色

# Web 配置界面
fish_config
```

### starship prompt

```bash
# 安装
curl -sS https://starship.rs/install.sh | sh

# 添加到 shell
# bash ~/.bashrc
# zsh ~/.zshrc
eval "$(starship init bash)"
eval "$(starship init zsh)"
# fish ~/.config/fish/config.fish
starship init fish | source
```

**配置 `~/.config/starship.toml`：**

```toml
format = """
$username\
$hostname\
$directory\
$git_branch\
$git_status\
$python\
$nodejs\
$rust\
$docker_context\
$cmd_duration\
$line_break\
$character"""

[character]
success_symbol = "[❯](bold green)"
error_symbol = "[❯](bold red)"

[directory]
truncation_length = 3
style = "bold cyan"

[git_branch]
symbol = " "
style = "bold purple"

[git_status]
style = "bold red"

[cmd_duration]
min_time = 2_000
format = "took [$duration]($style) "
```

### zoxide (Smart cd)

```bash
# 安装
brew install zoxide         # macOS
sudo apt install zoxide     # Ubuntu/Debian

# 添加到 shell
eval "$(zoxide init zsh)"   # zsh
eval "$(zoxide init bash)"  # bash
zoxide init fish | source   # fish
```

**使用：**

```bash
# 传统方式：cd /very/long/path/to/project
# zoxide 方式：
z project              # 跳转到包含 "project" 的最常用目录
z dev web              # 模糊匹配 "dev" 和 "web"
zi                     # 交互式选择

# 替代 cd
export _ZO_ECHO=1      # 跳转后显示路径
```

### fzf (Fuzzy Finder)

```bash
# 安装
brew install fzf

# 启用 key bindings 和 fuzzy completion
$(brew --prefix)/opt/fzf/install

# 或手动配置
source /usr/share/fzf/key-bindings.bash  # Linux
source <(fzf --zsh)                       # zsh
```

**常用场景：**

```bash
# 模糊搜索文件并用 vim 打开
vim $(fzf)

# 搜索命令历史 | Ctrl+R
# 模糊搜索进程并 kill
kill -9 $(ps aux | fzf | awk '{print $2}')

# 模糊搜索 git 分支并切换
git checkout $(git branch | fzf)

# 模糊搜索并预览文件内容
fzf --preview 'bat --color=always {}'
```

**配置 `~/.fzf.zsh`：**

```zsh
export FZF_DEFAULT_OPTS="
  --height 60%
  --layout=reverse
  --border
  --info=inline
  --color='bg+:#293739,bg:#1B1D1E,border:#808080,fg:#D8DEE9'
  --bind='ctrl-/:toggle-preview'"

export FZF_DEFAULT_COMMAND='fd --type f --hidden --follow --exclude .git'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
```

### ripgrep (rg)

```bash
# 安装
brew install ripgrep

# 基本使用
rg "pattern"                  # 当前目录搜索
rg "pattern" -t py            # 仅搜索 Python 文件
rg "pattern" -g "*.md"        # glob 过滤
rg "pattern" --type-add 'web:*.{html,css,js}' -t web
rg -i "pattern"               # 忽略大小写
rg -c "pattern"               # 统计匹配行数
rg -l "pattern"               # 只显示文件名
rg "pattern" --replace "new"  # 替换预览

# 与 grep 对比
# rg 比 grep 快 2-10 倍
# 自动忽略 .gitignore 中的文件
# 默认递归搜索
# 支持 .gitignore 和 .rgignore
```

### fd (find alternative)

```bash
# 安装
brew install fd

# 基本使用
fd "pattern"                 # 模糊搜索文件名
fd -e py                     # 按扩展名
fd -t f                      # 仅文件
fd -t d                      # 仅目录
fd -H                        # 包含隐藏文件
fd -s "Pattern"              # 大小写敏感
fd --changed-within 1d       # 最近 1 天修改的文件
fd "config" /etc             # 指定目录搜索

# 与 find 对比
# fd 比 find 快 2-5 倍
# 语法更简洁：fd "py$" vs find . -name "*.py"
# 默认忽略 .gitignore
# 彩色输出
```

### bat (cat alternative)

```bash
# 安装
brew install bat

# 基本使用
bat file.py                  # 语法高亮查看
bat -n file.py               # 显示行号
bat -A file.py               # 显示不可见字符
bat --diff file1 file2       # 差异对比
bat -l json                  # 指定语言
bat --style=numbers,changes  # 自定义样式

# 作为 man pager
export MANPAGER="sh -c 'col -bx | bat -l man -p'"

# 作为 git pager（配合 delta 更好）
git show HEAD:file | bat -l diff
```

### eza (ls alternative)

```bash
# 安装
brew install eza

# 基本使用
eza                          # 基础列表
eza -la                      # 长格式 + 隐藏文件
eza --icons                  # 显示文件图标
eza --tree                   # 树形视图
eza --tree --level=2         # 限制深度
eza -l --git                 # 显示 git 状态
eza -l --git-ignore          # 忽略 gitignore 文件
eza --sort=modified          # 按修改时间排序
eza --group-directories-first # 目录优先

# 添加别名
alias ls="eza --icons --group-directories-first"
alias ll="eza -la --icons --git --group-directories-first"
alias tree="eza --tree --icons --level=3"
```

### delta (diff alternative)

```bash
# 安装
brew install git-delta

# 配置 git 使用 delta
git config --global core.pager delta
git config --global interactive.diffFilter 'delta --color-only'
git config --global delta.navigate true
git config --global merge.conflictStyle diff3
```

**配置 `~/.gitconfig`：**

```ini
[delta]
    navigate = true
    line-numbers = true
    side-by-side = true
    syntax-theme = "Dracula"

[delta "decorations"]
    commit-decoration-style = bold yellow box ul
    file-style = bold yellow ul
    file-decoration-style = none
```

### bottom (System Monitor)

```bash
# 安装
brew install bottom

# 启动
btm

# 常用参数
btm --basic                 # 精简模式
btm --battery               # 显示电池
btm --network               # 网络流量
btm --process_command       # 显示完整命令

# 键位
# 1-4: 切换面板
# Tab: 切换进程/磁盘/CPU
# /: 搜索进程
# p: 按进程名排序
# Ctrl+e: 展开当前面板
```

## Configuration

### 一键安装脚本 (macOS)

```bash
#!/bin/bash
# install-shell-tools.sh

brew install \
  zsh starship zoxide fzf ripgrep fd bat eza git-delta bottom

# fish shell
brew install fish

# 安装 oh-my-zsh 插件
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM}/plugins/zsh-syntax-highlighting

# fzf 集成
$(brew --prefix)/opt/fzf/install

echo "✅ Shell tools installed! Restart your terminal."
```

### 一键安装脚本 (Ubuntu/Debian)

```bash
#!/bin/bash
# install-shell-tools.sh

sudo apt update && sudo apt install -y zsh fzf

# 安装 Rust 工具链（如果还没有）
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# 通过 cargo 安装
cargo install starship zoxide ripgrep fd-find bat eza git-delta bottom

# 通过官方脚本安装 starship
curl -sS https://starship.rs/install.sh | sh
```

## Tips

1. **fzf + fd + bat = 完美组合** - fzf 用 fd 做后端搜索，用 bat 做预览
2. **alias 是关键** - 为常用命令设置短别名，如 `alias g=git`
3. **不要替换太多** - 别名覆盖系统命令可能导致脚本兼容问题，建议用函数包装
4. **增量采用** - 不要一次装全部工具，每周引入一个，熟悉后再加下一个
5. **备份配置** - 用 dotfiles 仓库管理你的 shell 配置

## See Also

- [终端模拟器](./terminal-emulators.md) - 选择合适的终端应用
- [CLI 效率工具](./cli-productivity.md) - 更多命令行效率工具

---

## 中文版本

### 使用场景

- 将默认 bash/zsh 打造为高效、美观、智能的开发环境
- 替换传统命令行工具为现代化 Rust 实现
- 需要智能补全、模糊搜索、语法高亮等功能
- 想要美观的命令行提示符显示 git 状态和语言版本

### 核心步骤

1. **配置 zsh + oh-my-zsh** — 安装 zsh-autosuggestions、zsh-syntax-highlighting 插件，使用 powerlevel10k 主题
2. **安装 starship** — 跨 shell 提示符，显示 git 分支、语言版本、命令耗时
3. **安装现代替代工具** — eza（替代 ls）、bat（替代 cat）、fd（替代 find）、ripgrep（替代 grep）
4. **配置 fzf** — 模糊搜索文件、命令历史、git 分支，配合 fd 做后端搜索、bat 做预览
5. **配置 zoxide** — 智能目录跳转，`z project` 直接跳转到最常用的 project 目录

### 模板说明

- zshrc 配置 — oh-my-zsh 插件列表和主题配置
- starship.toml — 提示符格式和各模块样式配置
- fzf 配置 — 默认选项、颜色方案、快捷键绑定
- 一键安装脚本 — macOS 和 Ubuntu 的完整安装脚本

### 常见陷阱

1. **别名覆盖系统命令** — 别名覆盖系统命令可能导致脚本兼容问题，建议用函数包装
2. **一次性装全部工具** — 建议每周引入一个工具，熟悉后再加下一个
3. **fzf + fd + bat 需要配合配置** — 单独安装不配置集成无法发挥最大效果
4. **zoxide 未替换 cd** — 需要在 shell 配置中将 `z` 设为 `cd` 的别名才能无缝使用
5. **delta 未配置 git** — 安装后需配置 `git config --global core.pager delta` 才能生效
