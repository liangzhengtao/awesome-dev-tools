# Git 效率工具 / Git Productivity Tools

> Git 是每个开发者的必备技能，但原生 Git 命令有时不够直观。这些工具让 Git 操作更高效、更安全。

## Overview

Git 效率工具的价值：

- **可视化操作** - TUI 界面比命令行更直观
- **规范化提交** - 自动生成规范的 commit message
- **代码质量** - 提交前自动检查代码
- **工作流自动化** - Git Flow、自动合并、自动发布

## Comparison Table

| Tool | 类型 | 功能 | 语言 | 推荐度 |
|------|------|------|------|--------|
| **lazygit** | TUI 界面 | 全功能 Git TUI | Go | ⭐⭐⭐⭐⭐ |
| **gitui** | TUI 界面 | 轻量 Git TUI | Rust | ⭐⭐⭐⭐ |
| **tig** | TUI 界面 | Git 日志浏览器 | C | ⭐⭐⭐⭐ |
| **git-flow** | 工作流 | Git 分支管理模型 | Shell | ⭐⭐⭐ |
| **pre-commit** | Git Hooks | 提交前代码检查 | Python | ⭐⭐⭐⭐⭐ |
| **husky** | Git Hooks | Node.js Git Hooks | JavaScript | ⭐⭐⭐⭐⭐ |
| **commitlint** | 提交规范 | 检查 commit message | JavaScript | ⭐⭐⭐⭐ |
| **conventional-commits** | 提交规范 | 规范化提交格式 | - | ⭐⭐⭐⭐⭐ |

## Quick Start

### lazygit

```bash
# 安装
brew install lazygit
go install github.com/jesseduffield/lazygit@latest

# 启动
lazygit

# 核心快捷键
# 空格     - 暂存/取消暂存
# c        - 提交
# P        - 推送
# p        - 拉取
# d        - 查看差异（选中的文件）
# e        - 编辑文件
# o        - 在浏览器中打开
# /        - 过滤搜索
# ?        - 帮助面板
# q        - 退出

# 面板切换（数字键）
# 1 - 状态面板
# 2 - 文件面板
# 3 - 分支面板
# 4 - 提交面板
# 5 - 暂存面板
```

**配置 `~/.config/lazygit/config.yml`：**

```yaml
gui:
  showIcons: true
  nerdFontsVersion: "3"
  theme:
    activeBorderColor:
      - "#89b4fa"
      - bold
    selectedLineBgColor:
      - "#313244"

git:
  paging:
    colorArg: always
    pager: delta --dark --paging=never --line-numbers --side-by-side

customCommands:
  - key: "C"
    command: "git cz"
    context: "files"
    description: "Conventional commit"
    subprocess: true
```

### gitui

```bash
# 安装
brew install gitui
cargo install gitui

# 启动
gitui

# 快捷键
# 1-4    - 切换面板
# Enter  - 查看详情
# Space  - 暂存
# c      - 提交
# e      - 编辑
# /      - 搜索
```

### tig

```bash
# 安装
brew install tig
sudo apt install tig

# 使用
tig                    # 日志浏览器
tig status             # 状态视图
tig log                # 提交日志
tig blame file.txt     # 文件 blame
tig diff               # 查看差异

# 快捷键
# j/k    - 上下移动
# Enter  - 查看详情
# q      - 返回/退出
# /      - 搜索
# R      - 刷新
```

### git-flow

```bash
# 安装
brew install git-flow

# 初始化（在 git 仓库中）
git flow init

# 功能分支
git flow feature start new-feature
# ... 开发 ...
git flow feature finish new-feature

# 发布分支
git flow release start v1.0.0
# ... 准备发布 ...
git flow release finish v1.0.0

# 热修复
git flow hotfix start fix-bug
# ... 修复 ...
git flow hotfix finish fix-bug
```

**Git Flow 分支模型：**

```
main ─────●────────────────●─────────●─────
          │                ↑         ↑
          │            release   hotfix
          │                │         │
develop ──●──●──●──●──●──●─●──●──────●─────
          ↑        ↑      │
       feature  feature  merge
```

### pre-commit

```bash
# 安装
pip install pre-commit

# 在项目根目录创建 .pre-commit-config.yaml
```

**配置示例 `.pre-commit-config.yaml`：**

```yaml
repos:
  # 通用检查
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.5.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
      - id: check-json
      - id: check-added-large-files
      - id: check-merge-conflict

  # Python
  - repo: https://github.com/astral-sh/ruff-pre-commit
    rev: v0.2.0
    hooks:
      - id: ruff
        args: [--fix]
      - id: ruff-format

  # JavaScript/TypeScript
  - repo: https://github.com/pre-commit/mirrors-eslint
    rev: v9.0.0
    hooks:
      - id: eslint

  # 提交信息规范
  - repo: https://github.com/commitizen-tools/commitizen
    rev: v3.13.0
    hooks:
      - id: commitizen

  # 安全检查
  - repo: https://github.com/trufflesecurity/trufflehog
    rev: v3.63.0
    hooks:
      - id: trufflehog
```

```bash
# 安装 git hooks
pre-commit install

# 手动运行所有检查
pre-commit run --all-files

# 更新 hooks 版本
pre-commit autoupdate
```

### husky

```bash
# 安装（需要 Node.js 项目）
npm install husky --save-dev

# 初始化
npx husky init

# 添加 pre-commit hook
echo "npx lint-staged" > .husky/pre-commit

# 添加 commit-msg hook
echo "npx --no -- commitlint --edit \$1" > .husky/commit-msg
```

**package.json 配置：**

```json
{
  "scripts": {
    "prepare": "husky"
  },
  "lint-staged": {
    "*.{js,ts,tsx}": ["eslint --fix", "prettier --write"],
    "*.{json,md}": ["prettier --write"]
  }
}
```

### commitlint

```bash
# 安装
npm install --save-dev @commitlint/cli @commitlint/config-conventional

# 创建配置文件 commitlint.config.js
echo "export default { extends: ['@commitlint/config-conventional'] };" > commitlint.config.js
```

**Conventional Commits 格式：**

```
<type>(<scope>): <subject>

[optional body]

[optional footer]

# 示例：
feat(auth): add OAuth2 login support
fix(api): resolve null pointer in user endpoint
docs(readme): update installation instructions
refactor(core): simplify error handling logic
test(auth): add unit tests for login flow
chore(deps): update dependencies to latest
```

**类型说明：**

| Type | 说明 |
|------|------|
| `feat` | 新功能 |
| `fix` | Bug 修复 |
| `docs` | 文档变更 |
| `style` | 代码格式（不影响功能） |
| `refactor` | 重构 |
| `perf` | 性能优化 |
| `test` | 测试 |
| `chore` | 构建/工具变更 |
| `ci` | CI 配置变更 |

## Workflow Examples

### 完整的 Git 工作流

```bash
# 1. 安装工具
brew install lazygit
pip install pre-commit commitizen
npm install husky @commitlint/cli @commitlint/config-conventional --save-dev

# 2. 初始化项目
git init
pre-commit install
npx husky init

# 3. 开发流程
git checkout -b feature/new-api    # 创建分支
# ... 编写代码 ...
lazygit                             # 用 lazygit 暂存和提交
# 或
git add .
cz commit                          # 用 commitizen 规范化提交
git push origin feature/new-api    # 推送

# 4. 创建 PR，代码审查
# 5. 合并到 main，自动部署
```

### Commit Message 生成器

```bash
# 使用 commitizen 交互式提交
npm install -g commitizen cz-conventional-changelog
echo '{ "path": "cz-conventional-changelog" }' > ~/.czrc

# 使用
git add .
cz c    # 交互式选择类型、填写描述
```

## Alias Recommendations

```bash
# 添加到 ~/.gitconfig
[alias]
  co = checkout
  br = branch
  ci = commit
  st = status
  lg = log --oneline --graph --decorate --all
  last = log -1 HEAD --stat
  unstage = reset HEAD --
  amend = commit --amend --no-edit
  squash = rebase -i HEAD~2
  wip = !git add -A && git commit -m "WIP"
  undo = reset --soft HEAD~1
  graph = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'
```

## Tips

1. **lazygit 是必备** - 最好用的 Git TUI，没有之一
2. **pre-commit 必装** - 自动检查代码质量，避免低级错误
3. **规范提交** - Conventional Commits 让 changelog 和版本管理自动化
4. **善用 git stash** - 临时保存未完成的工作
5. **交互式 rebase** - `git rebase -i` 整理提交历史
6. **git bisect** - 二分法定位引入 bug 的提交

## See Also

- [CLI 效率工具](../终端工具/cli-productivity.md) - 更多命令行工具
- [API 工具](./api-tools.md) - API 开发工具

---

## 中文版本

### 使用场景

- 使用 TUI 界面替代纯命令行 Git 操作
- 规范化提交信息（Conventional Commits）
- 提交前自动检查代码质量
- 自动化 Git 工作流（Git Flow、自动合并、自动发布）

### 核心步骤

1. **lazygit 必装** — 最好用的 Git TUI，空格暂存、c 提交、P 推送、d 查看差异
2. **pre-commit hooks** — 安装 pre-commit 框架，配置 trailing-whitespace、check-yaml、ruff 等检查
3. **husky + lint-staged** — Node.js 项目使用 husky 管理 Git hooks，lint-staged 只检查暂存文件
4. **commitlint** — 强制执行 Conventional Commits 格式（feat/fix/docs/refactor）
5. **commitizen** — 交互式规范化提交，选择类型、填写描述、自动生成 changelog

### 模板说明

- lazygit 配置 — 主题、delta pager 集成、自定义 conventional commit 快捷键
- .pre-commit-config.yaml — 通用检查 + Python ruff + ESLint + commitizen + 安全检查
- husky 配置 — pre-commit（lint-staged）和 commit-msg（commitlint）hooks
- Git alias 推荐 — lg（图形日志）、undo（撤销提交）、wip（工作进度提交）

### 常见陷阱

1. **pre-commit 未安装** — 只创建配置文件不执行 `pre-commit install` 不会生效
2. **commitlint 配置缺失** — 需要 `commitlint.config.js` 文件，否则报错
3. **lint-staged 未配置** — husky 只是 hook 管理器，需要配合 lint-staged 执行实际检查
4. **团队不统一** — 工具需要全团队使用才能发挥价值，建议在项目初始化时就配置
5. **交互式 rebase 冲突** — `git rebase -i` 整理提交时可能遇到冲突，需要手动解决
