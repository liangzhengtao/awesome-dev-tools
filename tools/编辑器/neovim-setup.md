# Neovim 配置指南 / Neovim Setup Guide

> Neovim 是 Vim 的现代化分支，支持 Lua 配置、内置 LSP、异步插件。本文帮你从零搭建高效的 Neovim 开发环境。

## Overview

Neovim 的优势：

- **极速** - 启动时间 < 50ms，操作无延迟
- **终端原生** - 不离开终端即可完成所有开发工作
- **Lua 配置** - 比 VimScript 更快、更易维护
- **内置 LSP** - 代码补全、跳转、重构开箱即用
- **高度可定制** - 每一个按键、每一个行为都可以自定义

## Starter Distributions Comparison

| Distribution | 定位 | 配置复杂度 | 学习曲线 | 适合人群 |
|-------------|------|-----------|---------|---------|
| **LazyVim** | 全功能预配置 | 低 | 低 | 从 VS Code 迁移 |
| **AstroNvim** | 美观 + 功能 | 中 | 中 | 追求开箱即用 |
| **NvChad** | 极简 + 快速 | 中 | 中 | 喜欢自定义 |
| **从零开始** | 完全自定义 | 高 | 高 | 深度定制需求 |

## Quick Start

### 安装 Neovim

```bash
# macOS
brew install neovim

# Linux (从 GitHub Releases 下载最新版)
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz
sudo tar -C /opt -xzf nvim-linux64.tar.gz
sudo ln -s /opt/nvim-linux64/bin/nvim /usr/local/bin/nvim

# Windows
winget install Neovim.Neovim

# 验证版本（需要 >= 0.9.0）
nvim --version
```

### LazyVim（推荐新手）

```bash
# 备份现有配置
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak

# 克隆 LazyVim starter
git clone https://github.com/LazyVim/starter ~/.config/nvim
rm -rf ~/.config/nvim/.git

# 启动 Neovim
nvim
# 首次启动会自动安装所有插件
```

**LazyVim 目录结构：**

```
~/.config/nvim/
├── init.lua                 # 入口文件
├── lua/
│   ├── config/
│   │   ├── autocmds.lua     # 自动命令
│   │   ├── keymaps.lua      # 快捷键
│   │   ├── lazy.lua         # 插件管理器配置
│   │   └── options.lua      # 选项设置
│   └── plugins/             # 插件配置目录
│       ├── *.lua            # 每个文件配置一组插件
```

### AstroNvim

```bash
# 备份现有配置
mv ~/.config/nvim ~/.config/nvim.bak

# 克隆 AstroNvim
git clone --depth 1 https://github.com/AstroNvim/AstroNvim ~/.config/nvim

# 启动
nvim
```

### NvChad

```bash
# 备份现有配置
mv ~/.config/nvim ~/.config/nvim.bak

# 克隆 NvChad starter
git clone https://github.com/NvChad/starter ~/.config/nvim

# 启动
nvim
```

## Essential Plugins

### 插件管理器 (lazy.nvim)

```lua
-- lua/config/lazy.lua（LazyVim 已内置）
local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
if not vim.loop.fs_stat(lazypath) then
  vim.fn.system({
    "git", "clone", "--filter=blob:none",
    "https://github.com/folke/lazy.nvim.git",
    "--branch=stable", lazypath,
  })
end
vim.opt.rtp:prepend(lazypath)
```

### 核心插件列表

```lua
-- lua/plugins/editor.lua
return {
  -- 文件搜索
  { "nvim-telescope/telescope.nvim", dependencies = { "nvim-lua/plenary.nvim" } },

  -- 文件树
  { "nvim-neo-tree/neo-tree.nvim", dependencies = { "nvim-lua/plenary.nvim", "nvim-tree/nvim-web-devicons" } },

  -- 语法高亮
  { "nvim-treesitter/nvim-treesitter", build = ":TSUpdate" },

  -- Git 集成
  { "lewis6991/gitsigns.nvim" },

  -- 状态栏
  { "nvim-lualine/lualine.nvim" },

  -- 自动补全
  { "hrsh7th/nvim-cmp" },
  { "hrsh7th/cmp-nvim-lsp" },
  { "hrsh7th/cmp-buffer" },
  { "hrsh7th/cmp-path" },
  { "L3MON4D3/LuaSnip" },

  -- 注释
  { "numToStr/Comment.nvim", config = true },

  -- 包围符号编辑
  { "kylechui/nvim-surround", config = true },

  -- 自动配对
  { "windwp/nvim-autopairs", config = true },
}
```

## LSP Setup

### 通过 Mason 安装 LSP

```lua
-- lua/plugins/lsp.lua
return {
  -- LSP 管理器
  { "williamboman/mason.nvim", config = true },
  { "williamboman/mason-lspconfig.nvim" },

  -- LSP 配置
  { "neovim/nvim-lspconfig" },
}
```

```vim
" 在 Neovim 中安装 LSP 服务器
:Mason
" 选择并安装：
" - lua-language-server (Lua)
" - pyright (Python)
" - typescript-language-server (TypeScript/JavaScript)
" - rust-analyzer (Rust)
" - gopls (Go)
" - clangd (C/C++)
```

### LSP 配置示例

```lua
-- lua/config/lsp.lua
local lspconfig = require("lspconfig")

-- Python
lspconfig.pyright.setup({
  settings = {
    python = {
      analysis = {
        typeCheckingMode = "basic",
        autoSearchPaths = true,
        useLibraryCodeForTypes = true,
      },
    },
  },
})

-- TypeScript/JavaScript
lspconfig.ts_ls.setup({})

-- Rust
lspconfig.rust_analyzer.setup({
  settings = {
    ["rust-analyzer"] = {
      checkOnSave = { command = "clippy" },
    },
  },
})

-- Go
lspconfig.gopls.setup({})

-- Lua (for Neovim config)
lspconfig.lua_ls.setup({
  settings = {
    Lua = {
      diagnostics = { globals = { "vim" } },
      workspace = { library = vim.api.nvim_get_runtime_file("", true) },
    },
  },
})
```

## Key Bindings Reference

### LazyVim 默认快捷键

```lua
-- 文件操作
<leader>ff    -- 查找文件（Telescope）
<leader>fg    -- 全局搜索（grep）
<leader>fb    -- Buffer 列表
<leader>fr    -- 最近文件
<leader>fn    -- 新建文件

-- 窗口操作
<C-h>         -- 切换到左边窗口
<C-j>         -- 切换到下面窗口
<C-k>         -- 切换到上面窗口
<C-l>         -- 切换到右边窗口
<C-Up>        -- 增大窗口高度
<C-Down>      -- 减小窗口高度

-- Buffer 操作
<S-h>         -- 上一个 Buffer
<S-l>         -- 下一个 Buffer
<leader>bb    -- 切换 Buffer
<leader>bd    -- 关闭 Buffer

-- 代码操作
gd            -- 跳转到定义
gr            -- 查找引用
K             -- 显示文档
<leader>ca    -- 代码操作
<leader>rn    -- 重命名
<leader>cf    -- 格式化
<leader>xx    -- 诊断列表

-- Git
<leader>gg    -- 打开 Lazygit
<leader>gb    -- Git blame
<leader>gd    -- Git diff

-- 终端
<C-/>         -- 打开/关闭终端
<leader>ft    -- 浮动终端

-- 搜索替换
<leader>sr    -- 搜索替换（Spectre）
```

### 自定义快捷键

```lua
-- lua/config/keymaps.lua
local map = vim.keymap.set

-- 更好的缩进
map("v", "<", "<gv")
map("v", ">", ">gv")

-- 移动选中的行
map("v", "J", ":m '>+1<CR>gv=gv")
map("v", "K", ":m '<-2<CR>gv=gv")

-- 保持光标居中
map("n", "<C-d>", "<C-d>zz")
map("n", "<C-u>", "<C-u>zz")
map("n", "n", "nzzzv")
map("n", "N", "Nzzzv")

-- 粘贴不覆盖寄存器
map("x", "<leader>p", '"_dP')

-- 快速保存
map("n", "<C-s>", "<cmd>w<CR>")

-- 清除搜索高亮
map("n", "<Esc>", "<cmd>noh<CR>")
```

## Configuration

### 选项设置

```lua
-- lua/config/options.lua
local opt = vim.opt

opt.number = true              -- 显示行号
opt.relativenumber = true      -- 相对行号
opt.tabstop = 2                -- Tab 宽度
opt.shiftwidth = 2             -- 缩进宽度
opt.expandtab = true           -- 用空格替代 Tab
opt.smartindent = true         -- 智能缩进
opt.wrap = false               -- 不换行
opt.ignorecase = true          -- 搜索忽略大小写
opt.smartcase = true           -- 智能大小写
opt.cursorline = true          -- 高亮当前行
opt.termguicolors = true       -- 真彩色
opt.signcolumn = "yes"         -- 始终显示符号列
opt.scrolloff = 8              -- 滚动时保留 8 行
opt.updatetime = 250           -- 减少更新延迟
opt.clipboard = "unnamedplus"  -- 共享系统剪贴板
opt.undofile = true            -- 持久化撤销历史
```

### 自动命令

```lua
-- lua/config/autocmds.lua
local autocmd = vim.api.nvim_create_autocmd

-- 保存时自动格式化
autocmd("BufWritePre", {
  pattern = { "*.lua", "*.py", "*.js", "*.ts", "*.rs", "*.go" },
  callback = function()
    vim.lsp.buf.format({ async = false })
  end,
})

-- 高亮复制的文本
autocmd("TextYankPost", {
  callback = function()
    vim.highlight.on_yank({ higroup = "IncSearch", timeout = 200 })
  end,
})

-- 打开文件时恢复光标位置
autocmd("BufReadPost", {
  callback = function()
    local mark = vim.api.nvim_buf_get_mark(0, '"')
    local line_count = vim.api.nvim_buf_line_count(0)
    if mark[1] > 0 and mark[1] <= line_count then
      pcall(vim.api.nvim_win_set_cursor, 0, mark)
    end
  end,
})
```

## Tips

1. **先用 LazyVim** - 熟悉后再逐步自定义，不要一上来就从零配置
2. **学习 vim motions** - `hjkl` 移动、`w/b/e` 词移动、`/` 搜索，这是效率的核心
3. **用 which-key** - LazyVim 内置，按 `<leader>` 后会显示可用快捷键提示
4. **分阶段迁移** - 第一周只用 Neovim 做简单编辑，第二周加入 LSP，逐步替代 VS Code
5. **善用 Telescope** - 几乎所有搜索功能都通过 Telescope 实现
6. **定期更新插件** - `:Lazy update` 保持插件最新

## See Also

- [VS Code 扩展](./vscode-extensions.md) - 如果你更喜欢 GUI 编辑器
- [终端模拟器](../终端工具/terminal-emulators.md) - 选择合适的终端
- [Shell 工具](../终端工具/shell-tools.md) - 配套的 Shell 增强工具
