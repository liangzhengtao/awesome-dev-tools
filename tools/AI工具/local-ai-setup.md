# 本地 AI 部署 / Running AI Locally

> 不想将代码发送到云端？本地 AI 模型让你在保护隐私的同时享受 AI 辅助编程。

## Overview

本地运行 AI 模型的优势：

- **隐私保护** - 代码不离开你的电脑
- **无网络依赖** - 离线也能使用
- **无 API 费用** - 一次性投入硬件，长期免费
- **自定义控制** - 选择最适合的模型和参数
- **低延迟** - 本地推理无需网络传输

## Comparison Table

| Tool | 类型 | 易用性 | GPU 支持 | API 兼容 | 模型格式 |
|------|------|--------|----------|----------|----------|
| **Ollama** | 模型运行框架 | ⭐⭐⭐⭐⭐ | ✅ | ✅ OpenAI | GGUF |
| **LM Studio** | GUI 应用 | ⭐⭐⭐⭐⭐ | ✅ | ✅ OpenAI | GGUF |
| **llama.cpp** | 推理引擎 | ⭐⭐⭐ | ✅ | ✅ | GGUF |
| **text-generation-webui** | Web UI | ⭐⭐⭐⭐ | ✅ | ✅ | 多格式 |

## Hardware Requirements

| 配置 | 模型大小 | 推荐显卡 | 内存 | 适用场景 |
|------|----------|----------|------|----------|
| 入门 | 1-3B | 集成显卡 | 8GB | 简单对话、代码补全 |
| 基础 | 7-8B | RTX 3060 12GB | 16GB | 日常编程辅助 |
| 推荐 | 13-14B | RTX 4070 Ti 16GB | 32GB | 高质量代码生成 |
| 高端 | 34-70B | RTX 4090 24GB / A100 | 64GB | 接近 GPT-4 水平 |

**显存需求估算：**
- 4-bit 量化：每 1B 参数约需 0.6GB 显存
- 8-bit 量化：每 1B 参数约需 1.2GB 显存
- FP16：每 1B 参数约需 2GB 显存

## Quick Start

### Ollama（推荐）

```bash
# macOS / Linux 安装
curl -fsSL https://ollama.com/install.sh | sh

# Windows
# 从 https://ollama.com 下载安装包

# 拉取模型
ollama pull codellama:7b          # 代码专用
ollama pull llama3.1:8b           # 通用对话
ollama pull deepseek-coder:6.7b   # DeepSeek 代码模型
ollama pull qwen2.5:7b            # 通义千问
ollama pull mistral:7b            # Mistral

# 运行模型
ollama run codellama:7b
ollama run llama3.1:8b

# 在对话中使用
>>> 写一个 Python 快速排序
>>> 解释这段代码的作用：[粘贴代码]
>>> 帮我修复这个 bug：[粘贴错误]
```

**Ollama API 使用：**

```bash
# 兼容 OpenAI API 格式
curl http://localhost:11434/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "codellama:7b",
    "messages": [
      {"role": "system", "content": "你是一个编程助手"},
      {"role": "user", "content": "写一个 Python 快速排序"}
    ]
  }'

# Python 调用
import openai

client = openai.OpenAI(
    base_url="http://localhost:11434/v1",
    api_key="ollama"  # 任意值
)

response = client.chat.completions.create(
    model="codellama:7b",
    messages=[
        {"role": "user", "content": "写一个 Python 快速排序"}
    ]
)
print(response.choices[0].message.content)
```

**Ollama Modelfile 自定义：**

```dockerfile
# Modelfile.coding
FROM codellama:7b

PARAMETER temperature 0.3
PARAMETER top_p 0.9
PARAMETER num_ctx 4096

SYSTEM """
你是一个专业的编程助手。请用简洁、高效的代码回答问题。
总是提供完整可运行的代码示例。
"""
```

```bash
# 创建自定义模型
ollama create coding -f Modelfile.coding
ollama run coding
```

### LM Studio

```bash
# 1. 下载安装
# https://lmstudio.ai 下载对应平台版本

# 2. 下载模型
# 打开 LM Studio → 搜索模型 → 下载推荐：
# - TheBloke/CodeLlama-7B-Instruct-GGUF
# - TheBloke/Mistral-7B-Instruct-v0.2-GGUF
# - bartowski/DeepSeek-Coder-V2-Lite-Instruct-GGUF

# 3. 启动本地服务器
# Local Server 标签页 → Start Server
# 默认地址：http://localhost:1234/v1

# 4. 使用（兼容 OpenAI API）
curl http://localhost:1234/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{"model":"codellama","messages":[{"role":"user","content":"Hello"}]}'
```

**LM Studio 配置建议：**
- Context Length: 4096（根据显存调整）
- GPU Offload: 尽量多（利用显卡加速）
- Temperature: 0.1-0.3（代码生成用低温度）
- Threads: 设置为 CPU 核心数

### llama.cpp

```bash
# 从源码编译（支持 CUDA/Metal/Vulkan）
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp
make LLAMA_CUDA=1  # NVIDIA GPU
# 或
make LLAMA_METAL=1  # Apple Silicon

# 下载模型
# 从 HuggingFace 下载 GGUF 格式模型

# 运行推理
./llama-cli -m models/codellama-7b.Q4_K_M.gguf \
  -p "写一个 Python 快速排序" \
  -n 512 \
  --temp 0.3

# 启动 API 服务器
./llama-server -m models/codellama-7b.Q4_K_M.gguf \
  --host 0.0.0.0 \
  --port 8080 \
  -ngl 99  # GPU 层数
```

### text-generation-webui

```bash
# 克隆仓库
git clone https://github.com/oobabooga/text-generation-webui
cd text-generation-webui

# 一键安装（自动检测 GPU）
python start_linux.py   # Linux
python start_macos.py   # macOS
python start_windows.py # Windows

# 访问 Web UI
# http://localhost:7860

# 启用 API
# 在 Extensions 标签页启用 API
# API 地址：http://localhost:5000/v1
```

## Model Recommendations

### 代码专用模型

| 模型 | 大小 | 显存需求 | 推荐度 | 说明 |
|------|------|----------|--------|------|
| **DeepSeek-Coder-V2-Lite** | 16B | 12GB | ⭐⭐⭐⭐⭐ | 代码能力极强 |
| **CodeLlama** | 7B-34B | 5-20GB | ⭐⭐⭐⭐ | Meta 代码模型 |
| **Qwen2.5-Coder** | 7B-32B | 5-20GB | ⭐⭐⭐⭐⭐ | 代码能力优秀 |
| **StarCoder2** | 3B-15B | 3-10GB | ⭐⭐⭐⭐ | 多语言代码 |
| **Codestral** | 22B | 14GB | ⭐⭐⭐⭐ | Mistral 代码模型 |

### 通用对话模型

| 模型 | 大小 | 显存需求 | 推荐度 | 说明 |
|------|------|----------|--------|------|
| **Llama 3.1** | 8B-70B | 5-40GB | ⭐⭐⭐⭐⭐ | Meta 最新模型 |
| **Qwen2.5** | 7B-72B | 5-40GB | ⭐⭐⭐⭐⭐ | 中文能力强 |
| **Mistral** | 7B | 5GB | ⭐⭐⭐⭐ | 小而精 |
| **Gemma 2** | 9B-27B | 6-16GB | ⭐⭐⭐⭐ | Google 模型 |
| **Phi-3** | 3.8B-14B | 3-9GB | ⭐⭐⭐⭐ | 微软小模型 |

## API Compatibility

### 与编程工具集成

```python
# 与 Continue (VS Code) 集成
# ~/.continue/config.json
{
  "models": [
    {
      "title": "Ollama CodeLlama",
      "provider": "ollama",
      "model": "codellama:7b",
      "apiBase": "http://localhost:11434"
    }
  ],
  "tabAutocompleteModel": {
    "title": "Ollama StarCoder",
    "provider": "ollama",
    "model": "starcoder2:3b",
    "apiBase": "http://localhost:11434"
  }
}
```

```yaml
# 与 Cline (VS Code) 集成
# 在 Cline 设置中：
# API Provider: OpenAI Compatible
# Base URL: http://localhost:11434/v1
# Model: codellama:7b
# API Key: ollama
```

```json
// 与 Kimi Code 集成
// config.toml
[provider]
name = "openai"
base_url = "http://localhost:11434/v1"
api_key = "ollama"
model = "codellama:7b"
```

## Tips

1. **从小模型开始** - 7B 模型已经很有用，不需要追求大模型
2. **量化是关键** - Q4_K_M 量化几乎不损失质量，但大幅减少显存
3. **Ollama 最简单** - 一条命令安装，一条命令运行，推荐新手
4. **LM Studio 最友好** - GUI 界面，可视化管理模型和参数
5. **CPU 也能跑** - 没有 GPU 也可以用 CPU 运行，只是速度较慢
6. **组合使用** - 日常补全用小模型（快），复杂任务用大模型（准）
7. **关注新模型** - 本地模型进步很快，定期关注 HuggingFace 新发布

## See Also

- [AI 编程助手](./ai-coding-assistants.md) - AI 编程工具对比
- [AI 效率工具](./ai-productivity-tools.md) - 更多 AI 工具
- [Shell 工具](../终端工具/shell-tools.md) - 配套的终端工具
