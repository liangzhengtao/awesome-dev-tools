# AI 效率工具 / AI Productivity Tools

> AI 不仅能写代码。这些工具覆盖了搜索、写作、原型设计、应用生成等开发者日常工作场景。

## Overview

AI 效率工具正在重新定义开发者的工作方式：

- **智能搜索** - 比 Google 更精准的技术问题解答
- **快速原型** - 用自然语言生成 UI 和应用
- **文档写作** - AI 辅助技术文档和邮件
- **学习加速** - 快速理解新概念和框架

## Comparison Table

| Tool | 类别 | 核心功能 | 最佳场景 | 价格 |
|------|------|----------|----------|------|
| **ChatGPT** | 通用对话 | 多模态 AI 助手 | 通用问题、写作、代码 | Free / $20/月 |
| **Claude** | 通用对话 | 长上下文推理 | 代码审查、长文档分析 | Free / $20/月 |
| **Perplexity** | AI 搜索 | 引用来源的搜索 | 技术问题、最新资讯 | Free / $20/月 |
| **v0.dev** | UI 生成 | React 组件生成 | 快速 UI 原型 | Free / $20/月 |
| **bolt.new** | 应用生成 | 全栈应用生成 | 快速 MVP | Free / 付费 |
| **Cursor Composer** | 代码生成 | 跨文件代码编辑 | 大规模代码修改 | 包含在 Cursor 中 |
| **Replit Agent** | 应用生成 | AI 驱动开发环境 | 快速原型、学习 | Free / $25/月 |

## Quick Start

### ChatGPT

**开发者最佳用法：**

```
1. 代码调试
   "我有一个 Python 脚本报错：[粘贴错误信息]，请帮我分析原因并修复"

2. 代码解释
   "请解释这段代码的作用，逐行注释：[粘贴代码]"

3. 架构设计
   "我要设计一个类似 Twitter 的系统，请给出技术架构和数据库设计"

4. 正则表达式
   "写一个正则表达式，匹配邮箱地址，支持中文域名"

5. 学习新技术
   "用 TypeScript 给出 React + Zustand 的状态管理最佳实践，带完整示例"
```

**高级技巧：**

```
- 用 Custom Instructions 设定你的角色和偏好
- 用 GPT-4o 处理复杂推理任务
- 用 GPT-4o-mini 处理简单任务（更快、更便宜）
- 上传截图让 AI 分析 UI 设计
- 使用 Code Interpreter 运行和验证代码
```

### Claude

**开发者最佳用法：**

```
1. 代码审查
   [粘贴整个文件] "请审查这段代码，关注：安全性、性能、可维护性"

2. 长文档分析
   [粘贴 API 文档] "根据这个 API 文档，生成 Python SDK 的基础代码"

3. 架构讨论
   "我在考虑微服务 vs 单体架构，这是我的场景：[描述]，请分析利弊"

4. 技术写作
   "帮我写一份技术方案文档，需求是：[描述]，用 Markdown 格式"

5. 调试助手
   "这是错误堆栈和相关代码：[粘贴]，请帮我定位问题"
```

**Claude 优势：**
- 长上下文窗口（200K tokens），适合分析大型代码文件
- 推理能力强，适合复杂架构设计
- Artifacts 功能可以直接生成和预览代码

### Perplexity

**开发者最佳用法：**

```
1. 技术问题搜索
   "2024 年 React Server Components 最佳实践"
   → 自动搜索并给出带引用来源的答案

2. 框架对比
   "Next.js vs Nuxt.js vs SvelteKit 2024 对比"
   → 综合多个来源的对比分析

3. 错误排查
   "Error: Cannot find module 'xxx' 解决方案"
   → 搜索 Stack Overflow 和 GitHub Issues

4. 最新资讯
   "Node.js 22 新特性"
   → 带时间戳的最新信息

5. API 文档查询
   "Stripe API 创建订阅的步骤"
   → 从官方文档中提取关键信息
```

**Pro Search** - 深度搜索，适合复杂技术问题。

### v0.dev

**最擅长：** 用自然语言生成 React/Next.js UI 组件

```
使用流程：
1. 访问 v0.dev
2. 描述你想要的 UI
   "创建一个 Dashboard 页面，包含：
    - 左侧导航栏
    - 顶部搜索栏
    - 数据卡片（收入、用户、订单）
    - 折线图"
3. v0 生成组件代码
4. 可以继续对话修改
5. 复制代码到你的项目

适用场景：
- 快速原型设计
- UI 组件开发
- Tailwind CSS 练习
- 设计灵感探索
```

### bolt.new

**最擅长：** 用自然语言生成完整全栈应用

```
使用流程：
1. 访问 bolt.new
2. 描述你想要的应用
   "创建一个任务管理应用，功能包括：
    - 用户注册登录
    - 创建/编辑/删除任务
    - 任务分类和标签
    - 拖拽排序"
3. bolt.new 生成完整项目
4. 在浏览器中直接运行和修改
5. 导出代码

适用场景：
- MVP 快速验证
- 学习新技术栈
- 项目脚手架
- 快速演示原型
```

### Replit Agent

**最擅长：** AI 驱动的全栈开发环境

```
使用流程：
1. 访问 replit.com
2. 创建新的 Repl
3. 用自然语言描述应用
4. Replit Agent 自动：
   - 选择技术栈
   - 创建项目结构
   - 编写代码
   - 配置数据库
   - 部署应用
5. 可以持续对话迭代

适用场景：
- 快速原型
- 学习编程
- 小型项目部署
- 团队协作
```

## Tips

### Prompt 工程最佳实践

```
1. 提供上下文
   ❌ "写一个 API"
   ✅ "用 Express.js + TypeScript 写一个 RESTful API，包含用户注册、登录、JWT 认证，使用 PostgreSQL 数据库"

2. 指定格式
   ❌ "解释 React Hooks"
   ✅ "用表格对比 React 常用 Hooks（useState, useEffect, useRef, useMemo, useCallback），包含：用途、参数、返回值、使用示例"

3. 分步骤请求
   ❌ "创建一个电商网站"
   ✅ "第一步：设计数据库 schema（用户、商品、订单）
      第二步：创建 API 路由
      第三步：实现前端页面"

4. 提供示例
   ❌ "写一个工具函数"
   ✅ "写一个 debounce 工具函数，类似 Lodash 的 debounce，支持以下用法：const fn = debounce(callback, delay)"

5. 迭代优化
   不满意 → "请修改：1. 添加错误处理 2. 支持泛型 3. 添加单元测试"
```

### 工作流集成

```
日常开发 AI 工作流：

早上：
  Perplexity → 搜索技术资讯和新工具
  ChatGPT/Claude → 规划当天任务的技术方案

编码：
  Cursor/Copilot → 代码补全和生成
  v0.dev → 快速生成 UI 组件

调试：
  ChatGPT/Claude → 错误分析和修复建议
  Perplexity → 搜索解决方案

Review：
  Claude → 代码审查和优化建议

文档：
  ChatGPT → 生成 README、API 文档
  Claude → 技术方案写作
```

## See Also

- [AI 编程助手](./ai-coding-assistants.md) - AI 编程工具对比
- [本地 AI 部署](./local-ai-setup.md) - 在本地运行 AI 模型
- [设计工具](../设计工具/design-for-developers.md) - 设计工具推荐

---

## 中文版本

### 使用场景

- 使用 AI 进行智能搜索、快速原型、文档写作、学习加速
- 用自然语言生成 UI 组件和完整应用
- 辅助技术文档和邮件写作
- 快速理解新概念和框架

### 核心步骤

1. **智能搜索** — Perplexity 搜索技术问题，带引用来源，比 Google 更精准
2. **代码调试** — ChatGPT/Claude 分析错误信息、解释代码、修复 Bug
3. **UI 原型** — v0.dev 用自然语言生成 React/Next.js UI 组件
4. **全栈应用** — bolt.new 用自然语言生成完整项目，浏览器中直接运行
5. **代码审查** — Claude 分析长代码文件，关注安全性、性能、可维护性

### 模板说明

- ChatGPT 最佳用法 — 代码调试、解释、架构设计、正则表达式、学习新技术
- Claude 优势 — 200K tokens 长上下文、强推理、Artifacts 代码预览
- Perplexity 用法 — 技术搜索、框架对比、错误排查、API 文档查询
- v0.dev / bolt.new — 自然语言生成 UI 和全栈应用的工作流

### 常见陷阱

1. **Prompt 过于模糊** — "写一个 API" 不如 "用 Express.js + TypeScript 写 RESTful API，含 JWT 认证"
2. **不验证 AI 输出** — AI 可能生成不正确或过时的代码，始终验证和测试
3. **忽略分步请求** — 复杂任务应拆分为多步骤，而非一次性描述全部需求
4. **过度依赖单一工具** — 不同场景用不同工具，搜索用 Perplexity，编码用 Cursor，审查用 Claude
5. **不提供示例** — 提供示例代码或格式能显著提升 AI 输出质量
