# CLI 效率工具 / CLI Productivity Tools

> 终端不仅仅是输入命令的地方。这些工具让你在终端中完成 Git 操作、Docker 管理、API 调用、环境变量管理等一切工作。

## Overview

命令行效率工具将复杂的操作简化为直观的交互界面，让你：

- **不离开终端** - Git、Docker、API 全部在终端中完成
- **可视化操作** - TUI 界面比纯命令更直观
- **减少记忆负担** - 模糊搜索、智能提示帮你找到命令
- **环境隔离** - 自动管理不同项目的环境变量和运行时版本

## Comparison Table

| Tool | 类别 | 功能 | 语言 | 交互方式 |
|------|------|------|------|----------|
| **tmux** | 会话管理 | 终端多路复用 | C | 键盘 |
| **jq** | 数据处理 | JSON 查询/转换 | C | 命令行 |
| **yq** | 数据处理 | YAML/JSON/XML 处理 | Go | 命令行 |
| **httpie** | API 工具 | 人性化 HTTP 客户端 | Python | 命令行 |
| **lazygit** | Git | Git TUI 界面 | Go | 键盘+鼠标 |
| **lazydocker** | Docker | Docker TUI 界面 | Go | 键盘+鼠标 |
| **tldr** | 文档 | 简化版 man pages | 多语言 | 命令行 |
| **navi** | 文档 | 交互式命令备忘录 | Rust | 交互式 |
| **direnv** | 环境管理 | 目录级环境变量 | Go | 自动 |
| **asdf** | 版本管理 | 统一运行时版本管理 | 多语言 | 命令行 |

## Quick Start

### tmux (Terminal Multiplexer)

```bash
# 安装
brew install tmux          # macOS
sudo apt install tmux      # Ubuntu/Debian
```

**基础操作：**

```bash
# 新建会话
tmux new -s work           # 命名会话
tmux new -s server         # 另一个会话

# 管理会话
tmux ls                    # 列出会话
tmux attach -t work        # 恢复会话
tmux kill-session -t work  # 关闭会话

# 前缀键：Ctrl+B（所有操作都以前缀键开始）
# Ctrl+B %   - 水平分屏
# Ctrl+B "   - 垂直分屏
# Ctrl+B o   - 切换面板
# Ctrl+B c   - 新建窗口
# Ctrl+B n/p - 下/上一个窗口
# Ctrl+B d   - 分离会话（后台运行）
# Ctrl+B z   - 全屏当前面板
```

**配置 `~/.tmux.conf`：**

```bash
# 更友好的前缀键
set -g prefix C-a
unbind C-b
bind C-a send-prefix

# 鼠标支持
set -g mouse on

# 从 1 开始编号
set -g base-index 1
setw -g pane-base-index 1

# vim 风格面板切换
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R

# 更直觉的分屏快捷键
bind | split-window -h -c "#{pane_current_path}"
bind - split-window -v -c "#{pane_current_path}"

# 256 色支持
set -g default-terminal "screen-256color"

# 状态栏
set -g status-style 'bg=#333333 fg=#ffffff'
set -g status-right '#[fg=green]#(cut -d " " -f 1-3 /proc/loadavg)#[default] #[fg=cyan]%H:%M#[default]'
```

### jq (JSON Processor)

```bash
# 安装
brew install jq
sudo apt install jq
```

**常用操作：**

```bash
# 格式化 JSON
echo '{"name":"dev","version":1}' | jq .

# 提取字段
echo '{"name":"dev","tools":["vim","git"]}' | jq '.name'
echo '{"name":"dev","tools":["vim","git"]}' | jq '.tools[0]'

# 数组操作
echo '[{"name":"vim"},{"name":"git"}]' | jq '.[].name'
echo '[{"name":"vim"},{"name":"git"}]' | jq 'length'
echo '[{"name":"vim"},{"name":"git"}]' | jq 'map(.name)'

# 过滤
echo '[{"name":"vim","lang":"lua"},{"name":"git","lang":"c"}]' | jq '.[] | select(.lang == "c")'

# 转换
echo '{"name":"dev","version":1}' | jq '{tool: .name, ver: .version}'

# 实战：解析 GitHub API
curl -s https://api.github.com/repos/jqlang/jq | jq '.stargazers_count, .language, .description'
```

### yq (YAML/JSON/XML Processor)

```bash
# 安装
brew install yq
# 或从 GitHub Releases 下载

# 基本使用
yq '.services.web.image' docker-compose.yml
yq '.metadata.name' k8s-deployment.yaml
yq -o=json '.' config.yaml        # YAML 转 JSON
yq -o=yaml '.' config.json        # JSON 转 YAML

# 修改 YAML 文件
yq -i '.services.web.ports[0] = "8080:80"' docker-compose.yml
yq -i '.spec.replicas = 3' k8s-deployment.yaml

# 合并 YAML
yq eval-all 'select(fileIndex == 0) * select(fileIndex == 1)' base.yaml overlay.yaml
```

### httpie (HTTP Client)

```bash
# 安装
pip install httpie
# 或
brew install httpie
```

**常用操作：**

```bash
# GET 请求
http GET https://api.github.com/repos/httpie/cli

# POST 请求（JSON 自动设置 Content-Type）
http POST https://httpbin.org/post name=dev tools:='["vim","git"]'

# 带认证
http GET https://api.github.com/user Authorization:"Bearer TOKEN"

# 下载文件
http --download https://example.com/file.zip

# 会话管理（保持登录状态）
http --session=dev POST https://api.dev.com/login user=admin pass=secret
http --session=dev GET https://api.dev.com/dashboard

# 查看请求详情
http -v https://httpbin.org/get

# 与 curl 对比
# curl -s https://api.github.com/repos/cli/cli | jq .
# http https://api.github.com/repos/cli/cli  # 自动格式化
```

### lazygit

```bash
# 安装
brew install lazygit
# 或
go install github.com/jesseduffield/lazygit@latest
```

**使用：**

```bash
# 在 git 仓库中启动
lazygit

# 快捷键（启动后）
# 空格: 暂存/取消暂存文件
# c: 提交
# P: 推送
# p: 拉取
# d: 查看差异
# e: 编辑文件
# /: 搜索
# ?: 帮助面板
# 1-5: 切换面板（文件/分支/提交/暂存/stash）
```

**配置 `~/.config/lazygit/config.yml`：**

```yaml
gui:
  showIcons: true
  theme:
    activeBorderColor:
      - '#89b4fa'
      - bold
    selectedLineBgColor:
      - '#313244'

git:
  paging:
    colorArg: always
    pager: delta --dark --paging=never

customCommands:
  - key: "C"
    command: "git cz"
    context: "files"
    description: "commit with commitizen"
```

### lazydocker

```bash
# 安装
brew install lazydocker

# 启动
lazydocker
```

**功能：**
- 可视化查看容器、镜像、网络、卷
- 一键查看容器日志
- 容器资源监控
- 快速进入容器 shell
- 批量操作

### tldr (Simplified Man Pages)

```bash
# 安装
brew install tldr
# 或
npm install -g tldr
```

**使用：**

```bash
# 查看命令用法（比 man 简洁实用）
tldr tar
tldr git
tldr docker

# 示例输出
# tar - Archive utility
# tar -cf archive.tar file1 file2    # Create an archive
# tar -xf archive.tar                 # Extract an archive
# tar -czf archive.tar.gz dir/        # Create gzipped archive
```

### navi (Command Cheatsheet)

```bash
# 安装
brew install navi

# 使用
navi                         # 交互式浏览 cheatsheet
navi --print                 # 只打印命令不执行

# 常用 cheatsheet 仓库
navi repo add denisidoro/cheats
navi repo add nickvdyck/navi-cheats
```

### direnv (Directory Environment)

```bash
# 安装
brew install direnv

# 添加到 shell
eval "$(direnv hook zsh)"   # zsh
eval "$(direnv hook bash)"  # bash
direnv hook fish | source   # fish
```

**使用：**

```bash
# 在项目根目录创建 .envrc
echo 'export API_KEY=dev-key-123' > .envrc
echo 'export DATABASE_URL=postgres://localhost/mydb' >> .envrc

# 激活
direnv allow

# 进入目录时自动加载，离开时自动卸载
cd myproject        # API_KEY 自动设置
cd ..               # API_KEY 自动卸载

# 高级用法
# .envrc 中可以使用 bash
export NODE_VERSION=18
layout python3       # 自动创建 venv
use nvm              # 加载 nvm
dotenv               # 加载 .env 文件
```

### asdf (Version Manager)

```bash
# 安装
brew install asdf

# 添加到 shell
echo '. "$(brew --prefix asdf)/libexec/asdf.sh"' >> ~/.zshrc
```

**使用：**

```bash
# 安装插件
asdf plugin add nodejs
asdf plugin add python
asdf plugin add golang
asdf plugin add rust
asdf plugin add java

# 安装版本
asdf install nodejs 20.11.0
asdf install python 3.12.1
asdf install golang 1.22.0

# 设置全局默认版本
asdf global nodejs 20.11.0
asdf global python 3.12.1

# 设置项目本地版本（创建 .tool-versions 文件）
cd my-project
asdf local nodejs 18.19.0
asdf local python 3.11.7
cat .tool-versions
# nodejs 18.19.0
# python 3.11.7
```

## Workflow Examples

### 全栈开发工作流

```bash
# 1. 用 tmux 创建开发会话
tmux new -s dev

# 2. 分屏：左边代码，右边终端
# Ctrl+B |   水平分屏
# Ctrl+B "   垂直分屏

# 3. 用 asdf 管理项目运行时
cd my-fullstack-app
# .tool-versions 自动加载正确的 node/python 版本

# 4. 用 direnv 管理环境变量
# .envrc 自动加载 API_KEY、DATABASE_URL 等

# 5. 用 lazygit 管理代码版本
lazygit

# 6. 用 httpie 测试 API
http POST localhost:3000/api/users name=test email=test@example.com
```

### API 调试工作流

```bash
# 1. 用 httpie 发送请求
http GET localhost:8080/api/users

# 2. 用 jq 过滤响应
http GET localhost:8080/api/users | jq '.users[] | select(.active == true)'

# 3. 用 yq 处理配置
yq '.environments.staging' config.yaml

# 4. 用 tldr 快速查用法
tldr curl  # 比 man curl 实用多了
```

## Tips

1. **渐进式采用** - 先从 lazygit 和 fzf 开始，体验提升最明显
2. **tmux + SSH** - SSH 断开后 tmux 会话不丢失，恢复工作
3. **jq 是必备技能** - 任何 JSON 处理都离不开它
4. **direnv 保护密钥** - 避免将 API keys 硬编码到代码中
5. **asdf 替代 nvm/rbenv/pyenv** - 一个工具管理所有运行时版本

## See Also

- [Shell 工具](./shell-tools.md) - Shell 增强和现代化替代工具
- [终端模拟器](./terminal-emulators.md) - 选择合适的终端应用
- [Git 工具](../效率工具/git-tools.md) - 更多 Git 效率工具
