# API 开发工具 / API Development Tools

> API 开发需要高效的测试和调试工具。本文对比主流 API 工具，帮你摆脱 Postman 的臃肿。

## Overview

Postman 曾是 API 测试的王者，但它越来越臃肿（Electron 内存占用高、强制登录、功能膨胀）。现代替代品更轻量、更专注：

- **更快启动** - 原生应用或轻量 Web 应用
- **无需登录** - 开箱即用，无强制账号
- **Git 友好** - 集合以文件形式存储，可版本控制
- **开源优先** - 透明、可自托管

## Comparison Table

| Feature | Bruno | Insomnia | Hoppscotch | httpie | Postman |
|---------|-------|----------|------------|--------|---------|
| **开源** | ✅ | 部分 | ✅ | ✅ | ❌ |
| **GUI** | ✅ | ✅ | ✅ Web | ❌ CLI | ✅ |
| **离线使用** | ✅ | ✅ | ✅ PWA | ✅ | ⚠️ |
| **集合存储** | 文件系统 | 本地/云 | 本地/云 | 无 | 云端 |
| **Git 集成** | ✅ 原生 | ⚠️ | ⚠️ | N/A | ❌ |
| **环境变量** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **脚本/测试** | ✅ JavaScript | ✅ JavaScript | ✅ JavaScript | ❌ | ✅ |
| **GraphQL** | ✅ | ✅ | ✅ | ❌ | ✅ |
| **WebSocket** | ✅ | ✅ | ✅ | ❌ | ✅ |
| **gRPC** | ❌ | ✅ | ❌ | ❌ | ✅ |
| **导入 Postman** | ✅ | ✅ | ✅ | ❌ | N/A |
| **内存占用** | ~80MB | ~150MB | ~50MB | ~10MB | ~500MB |
| **免费功能** | 全部 | 基础 | 全部 | 全部 | 基础 |

## Quick Start

### Bruno（推荐）

```bash
# 安装
brew install bruno
# 或从 https://www.usebruno.com 下载

# 项目结构
my-api-project/
├── bruno.json           # 项目配置
├── environments/
│   ├── dev.bru          # 开发环境变量
│   └── prod.bru         # 生产环境变量
├── Auth/
│   ├── login.bru        # 登录请求
│   └── register.bru     # 注册请求
└── Users/
    ├── get-users.bru    # 获取用户列表
    └── create-user.bru  # 创建用户
```

**请求文件格式 `get-users.bru`：**

```bru
meta {
  name: Get Users
  type: http
  seq: 1
}

get {
  url: {{baseUrl}}/api/users
  body: none
  auth: bearer
}

headers {
  Authorization: Bearer {{token}}
  Content-Type: application/json
}

query {
  page: 1
  limit: 10
}

script:post-response {
  bru.setEnvVar("token", res.body.token);
}

tests {
  test("should return 200", function() {
    expect(res.status).to.equal(200);
  });

  test("should have users array", function() {
    expect(res.body.users).to.be.an('array');
  });
}
```

**环境文件 `dev.bru`：**

```bru
vars {
  baseUrl: http://localhost:3000
  token: your-dev-token
}
```

**Bruno 核心优势：**
- 请求以 `.bru` 文件存储，可直接 Git 管理
- 无云端依赖，数据完全在本地
- 支持 JavaScript 脚本和测试
- 支持导入 Postman / Insomnia 集合

### Insomnia

```bash
# 安装
brew install insomnia
# 或从 https://insomnia.rest 下载
```

**使用流程：**
1. 创建 New Request
2. 选择方法（GET/POST/PUT/DELETE）
3. 输入 URL 和参数
4. 发送请求
5. 查看响应

**特色功能：**
- 环境变量管理（开发/测试/生产）
- 自动生成代码片段（curl、Python、JavaScript 等）
- 设计模式：先设计 API 规范，再生成请求
- 插件系统扩展功能

### Hoppscotch

```bash
# Web 版（推荐）
# 访问 https://hoppscotch.io

# 自托管
docker compose up -d
# 或使用 NPM
npm install -g @hoppscotch/cli
```

**特色功能：**
- PWA 支持，可离线使用
- 极速启动（Web 应用）
- 支持 REST、GraphQL、WebSocket、SSE、Socket.IO
- 请求历史和收藏
- 团队协作

### httpie (CLI)

```bash
# 安装
pip install httpie
brew install httpie

# GET 请求
http GET https://api.github.com/repos/httpie/cli

# POST 请求（JSON）
http POST https://httpbin.org/post \
  name=dev \
  email=dev@example.com \
  tools:='["vim","git"]'

# 带认证
http GET https://api.github.com/user \
  Authorization:"Bearer ghp_xxxxx"

# 文件上传
http --form POST https://httpbin.org/post file@./report.pdf

# 下载文件
http --download https://example.com/file.zip

# 会话管理
http --session=dev POST https://api.dev.com/login user=admin pass=secret
http --session=dev GET https://api.dev.com/dashboard

# 输出格式化
http --print=hHbB https://api.github.com/repos/httpie/cli
# h=响应头 H=请求头 b=响应体 B=请求体

# 与 curl 对比
# curl -s "https://api.github.com/repos/httpie/cli" | jq .
# http https://api.github.com/repos/httpie/cli  # 自动格式化
```

## Collection Sharing

### Bruno 集合共享

```bash
# 方法 1：Git（推荐）
cd my-api-project
git init
git add .
git commit -m "API collection"
git remote add origin https://github.com/your-org/api-collection
git push -u origin main

# 团队成员克隆后直接用 Bruno 打开目录
```

### Postman 迁移

```bash
# 从 Postman 导出集合
# Postman → Collection → Export → Collection v2.1

# Bruno 导入
# Bruno → Import Collection → 选择导出的 JSON 文件

# Insomnia 导入
# Insomnia → Import → 选择导出的 JSON 文件

# Hoppscotch 导入
# Hoppscotch → Import → 选择导出的 JSON 文件
```

## Configuration

### 推荐配置方案

**个人开发者：**
- 主力：Bruno（本地存储 + Git）
- 辅助：httpie（快速 CLI 测试）

**小团队：**
- 主力：Bruno（Git 共享集合）
- 辅助：Hoppscotch（Web 版，零安装）

**大团队/企业：**
- 主力：Insomnia（团队协作 + 云端同步）
- 辅助：httpie（CI/CD 集成）

### CI/CD 集成

```yaml
# GitHub Actions 中使用 httpie 测试 API
name: API Tests
on: [push]
jobs:
  test-api:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Install httpie
        run: pip install httpie

      - name: Run API tests
        run: |
          http --check-status GET ${{ secrets.API_URL }}/health
          http --check-status POST ${{ secrets.API_URL }}/test \
            Authorization:"Bearer ${{ secrets.API_TOKEN }}" \
            data=test
```

## Tips

1. **Bruno 是 Postman 最佳替代** - 本地存储 + Git 原生支持，不再被云端锁定
2. **httpie 是 curl 最佳替代** - 语法直观，自动格式化，开发调试效率翻倍
3. **Hoppscotch 零安装** - 打开浏览器就能用，适合快速测试
4. **环境变量分层** - 使用 dev/staging/prod 环境变量，避免硬编码 URL
5. **测试脚本化** - 在请求中添加测试断言，CI/CD 中自动运行
6. **集合版本控制** - Bruno 的文件格式天然支持 Git，团队协作更方便

## See Also

- [Git 工具](./git-tools.md) - Git 效率工具
- [CLI 效率工具](../终端工具/cli-productivity.md) - 命令行效率工具
- [设计工具](../设计工具/design-for-developers.md) - 设计相关工具

---

## 中文版本

### 使用场景

- 替代臃肿的 Postman 进行 API 测试
- 需要 Git 友好的 API 集合管理
- 轻量级 HTTP 客户端快速调试
- CI/CD 中集成 API 测试

### 核心步骤

1. **选择工具** — 个人开发者用 Bruno（本地存储 + Git），团队用 Bruno + Hoppscotch（Web 版零安装）
2. **Bruno 集合管理** — 请求以 `.bru` 文件存储，直接 Git 版本控制，支持 JavaScript 脚本和测试
3. **httpie CLI 调试** — 语法直观（`http POST url key=value`），自动格式化 JSON 响应
4. **环境变量分层** — dev/staging/prod 环境变量分离，避免硬编码 URL 和 token
5. **Postman 迁移** — 导出 Collection v2.1 JSON，Bruno/Insomnia/Hoppscotch 均支持导入

### 模板说明

- Bruno 项目结构 — bruno.json、environments/、请求目录的组织方式
- .bru 请求格式 — URL、headers、query、script:post-response、tests 的完整示例
- httpie 常用操作 — GET/POST/认证/文件上传/下载/会话管理
- CI/CD 集成 — GitHub Actions 中使用 httpie 测试 API 的 workflow

### 常见陷阱

1. **Postman 强制登录** — Postman 越来越依赖云端账号，Bruno 完全本地无此问题
2. **环境变量未分离** — 将生产 URL 硬编码在请求中，切换环境容易出错
3. **集合未版本控制** — API 集合不纳入 Git 管理，团队协作时版本不一致
4. **测试脚本缺失** — 请求中不添加测试断言，CI/CD 无法自动验证 API 正确性
5. **httpie 的 `:=` 语法** — JSON 数组/对象需要 `:=` 而非 `=`，否则会被当作字符串
