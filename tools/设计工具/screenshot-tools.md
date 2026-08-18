# 截图和文档工具 / Screenshot & Documentation Tools

> 美观的截图和文档能让你的项目更专业。这些工具帮你轻松创建高质量的视觉内容。

## Overview

开发者需要截图工具的场景：

- **Bug 报告** - 清晰标注问题截图
- **技术文档** - 配图说明操作步骤
- **社交媒体** - 分享代码片段和成果
- **演示材料** - 产品截图和 UI 展示

## Comparison Table

| Tool | 平台 | 核心功能 | 价格 | 推荐度 |
|------|------|----------|------|--------|
| **CleanShot X** | macOS | 全功能截图 + 录屏 | $29 买断 | ⭐⭐⭐⭐⭐ |
| **Shottr** | macOS | 轻量截图 + 标注 | 免费 | ⭐⭐⭐⭐ |
| **Kap** | macOS | 开源录屏 | 免费 | ⭐⭐⭐⭐ |
| **ScreenStudio** | macOS | 精美录屏 | $29/年 | ⭐⭐⭐⭐⭐ |
| **carbon.now.sh** | Web | 代码截图美化 | 免费 | ⭐⭐⭐⭐⭐ |
| **ray.so** | Web | 代码截图美化 | 免费 | ⭐⭐⭐⭐ |
| **ShareX** | Windows | 全功能截图工具 | 免费 | ⭐⭐⭐⭐⭐ |
| **Flameshot** | Linux | Linux 截图标注 | 免费 | ⭐⭐⭐⭐ |

## Quick Start

### CleanShot X（macOS 首选）

```bash
# 购买和下载
# https://cleanshot.com
# 一次性买断 $29，物超所值
```

**核心功能：**

```
截图功能：
  ⌘+Shift+4      区域截图
  ⌘+Shift+3      全屏截图
  ⌘+Shift+6      滚动截图（长页面）
  ⌘+Shift+5      窗口截图（带阴影）

标注功能：
  - 箭头、矩形、圆形、线条
  - 文字、序号标注
  - 高亮、模糊（隐藏敏感信息）
  - 马赛克、像素化

特色功能：
  - 自动隐藏桌面图标
  - 自定义背景（渐变/纯色）
  - 滚动截图（捕获长网页）
  - 录屏（GIF/MP4）
  - OCR 文字识别
  - 云端上传分享
```

### Shottr（macOS 免费替代）

```bash
# 下载
# https://shottr.cc
# 免费使用

# 快捷键
⌘+Shift+4      区域截图
⌘+Shift+3      全屏截图
# 截图后自动进入标注模式
```

**特色功能：**
- 像素级标注工具
- 滚动截图
- 长截图拼接
- 颜色拾取器
- 尺寸标注
- 完全免费

### Kap（macOS 录屏）

```bash
# 安装
brew install --cask kap

# 使用
# 点击菜单栏图标 → 选择录制区域 → 开始录制
# 支持导出：GIF / MP4 / WebM / APNG
```

**配置：**
- 帧率：30fps / 60fps
- 格式：GIF（文档）、MP4（演示）
- 快捷键：`⌘+Shift+5` 开始/停止录制

### ScreenStudio（精美录屏）

```bash
# 下载
# https://screenstudio.com
# $29/年
```

**核心功能：**
- 自动生成精美背景
- 自动缩放和聚焦
- 鼠标高亮效果
- 键盘快捷键显示
- 自定义窗口样式
- 一键导出高质量视频

**使用场景：**
- 产品演示视频
- 教程录制
- 社交媒体分享
- 会议展示

### carbon.now.sh（代码截图）

```
# 访问 https://carbon.now.sh

# 使用步骤：
1. 粘贴代码
2. 选择语言（自动检测）
3. 选择主题（Dracula、Monokai 等）
4. 选择背景色
5. 调整字体和字号
6. 导出 PNG/SVG

# 支持的语言：几乎所有主流语言
# 支持的导出：PNG、SVG
```

**高级用法：**

```bash
# URL 参数直接生成
https://carbon.now.sh/?bg=rgba(255,255,255,0)&t=dracula&l=javascript&code=...

# VS Code 扩展
code --install-extension adpyke.codesnap
# 选中代码 → Ctrl+Shift+P → "CodeSnap" → 复制截图
```

### ray.so（简洁代码截图）

```
# 访问 https://ray.so

# 使用步骤：
1. 粘贴代码
2. 选择主题（Raycast 风格）
3. 选择背景样式
4. 导出 PNG

# 特色：更简洁的界面，Raycast 设计风格
```

### ShareX（Windows 首选）

```powershell
# 安装
winget install ShareX.ShareX
# 或从 https://getsharex.com 下载
```

**核心功能：**

```
截图：
  Print Screen      全屏截图
  Alt+Print Screen  窗口截图
  Shift+Print Screen 区域截图
  Ctrl+Print Screen 滚动截图

标注：
  - 箭头、矩形、圆形
  - 文字、序号
  - 高亮、模糊
  - 步骤标注

高级功能：
  - 录屏（GIF/MP4）
  - OCR 文字识别
  - 屏幕拾色器
  - 尺子工具
  - 自动上传（Imgur、自定义服务器）
  - 图片编辑器
```

### Flameshot（Linux 首选）

```bash
# 安装
sudo apt install flameshot
# 或
brew install flameshot

# 启动截图
flameshot gui

# 快捷键配置（GNOME）
# Settings → Keyboard → Custom Shortcuts
# Command: flameshot gui
# Shortcut: Print Screen
```

**标注工具：**
- 画笔、箭头、线条
- 矩形、圆形
- 文字标注
- 马赛克模糊
- 自动上传到 Imgur

## Configuration

### 代码截图美化工具对比

| 工具 | 平台 | 特色 | 推荐场景 |
|------|------|------|----------|
| carbon.now.sh | Web | 主题丰富，功能全面 | 社交媒体分享 |
| ray.so | Web | 简洁美观，Raycast 风格 | 快速分享 |
| CodeSnap | VS Code | 编辑器内直接截图 | 技术文档 |
| Polacode | VS Code | 精美代码截图 | 博客配图 |

### VS Code 代码截图配置

```json
// CodeSnap 扩展设置
{
  "codesnap.backgroundColor": "#1e1e2e",
  "codesnap.boxShadow": "none",
  "codesnap.containerPadding": "0",
  "codesnap.roundedCorners": true,
  "codesnap.showWindowControls": true,
  "codesnap.showWindowTitle": true,
  "codesnap.showLineNumbers": true,
  "codesnap.realLineNumbers": true,
  "codesnap.transparentBackground": false
}
```

### 截图最佳实践

```
1. 背景选择
   - 浅色背景：适合文档和博客
   - 渐变背景：适合社交媒体
   - 透明背景：适合嵌入设计稿

2. 主题选择
   - Dracula：紫色调，最受欢迎
   - One Dark：Atom 风格
   - Tokyo Night：深蓝色调
   - GitHub Light：适合文档

3. 尺寸建议
   - 社交媒体：1200x630px（Open Graph 标准）
   - 博客文章：800-1200px 宽度
   - 技术文档：根据内容自适应

4. 标注原则
   - 少即是多，不要过度标注
   - 使用红色箭头指向关键位置
   - 模糊处理敏感信息（密码、邮箱、token）
   - 添加序号标注步骤
```

## Tips

1. **macOS 用户必装 CleanShot X** - 一站式截图方案，$29 买断超值
2. **Windows 用户用 ShareX** - 免费且功能全面，替代系统截图
3. **代码截图用 carbon** - 分享代码片段最优雅的方式
4. **录屏用 ScreenStudio** - 自动生成精美效果，省去后期编辑
5. **敏感信息必模糊** - 截图前检查是否有密码、token、个人信息
6. **统一风格** - 同一文档/项目的截图使用相同的主题和背景

## See Also

- [设计工具](./design-for-developers.md) - 设计和图表工具
- [VS Code 扩展](../编辑器/vscode-extensions.md) - VS Code 代码截图扩展

---

## 中文版本

### 使用场景

- Bug 报告需要清晰标注的问题截图
- 技术文档需要配图说明操作步骤
- 社交媒体分享代码片段和成果
- 产品演示和 UI 展示截图

### 核心步骤

1. **macOS 首选** — CleanShot X（$29 买断）一站式截图方案，支持滚动截图、录屏、OCR
2. **Windows 首选** — ShareX 免费且功能全面，支持截图、标注、录屏、自动上传
3. **代码截图** — carbon.now.sh 或 ray.so 将代码片段美化为可分享的图片
4. **录屏** — ScreenStudio 自动生成精美背景和缩放效果，Kap 开源免费
5. **敏感信息处理** — 截图前检查是否有密码、token、个人信息，使用模糊/马赛克工具处理

### 模板说明

- CleanShot X 功能 — 区域截图、滚动截图、窗口截图、标注工具、录屏
- carbon.now.sh 用法 — 粘贴代码、选择语言/主题/背景、导出 PNG/SVG
- VS Code CodeSnap 配置 — 编辑器内直接截图的扩展设置
- 截图最佳实践 — 背景选择、主题选择、尺寸建议、标注原则

### 常见陷阱

1. **截图含敏感信息** — 密码、API key、个人信息务必模糊处理后再分享
2. **截图风格不统一** — 同一文档/项目应使用相同的主题和背景保持一致性
3. **分辨率不当** — 社交媒体用 1200x630px（Open Graph 标准），博客用 800-1200px 宽度
4. **标注过多** — 少即是多，使用红色箭头指向关键位置，不要过度标注
5. **录屏帧率选择** — 文档用 GIF（30fps），演示用 MP4（60fps），根据用途选择格式
