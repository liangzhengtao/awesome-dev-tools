[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🛠️ Awesome Dev Tools

**더 일찍 알았으면 좋았을 개발자 도구 모음. 카테고리별로 정리된 50개 이상의 도구.**

생산성을 높여주는 엄선된 개발 도구 컬렉션.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-50+-orange.svg)](#-tools-overview)

</div>

---



## Before vs After

```
❌ 이 도구 없이:                        ✅ 이 도구 사용 시:
─────────────────────────                  ─────────────────────────
$ grep -r "TODO" --include="*.py" .        $ rg "TODO" -t py
  (느림, 재귀적, 색상 없음)                   (10배 빠름, 컬러, .gitignore 준수)

$ find . -name "*.ts" -not -path "*/node*"  $ fd -e ts
  (verbose한 구문, 플래그 기억)                (직관적, 스마트 기본값)

$ git diff                                  $ git diff (delta)
  (일반 텍스트, 읽기 어려움)                    (구문 강조, 나란히 비교)

$ cat config.json                           $ bat config.json
  (구문 강조 없음)                              (구문 강조 + 줄 번호)

$ cd /very/long/path/to/project             $ z project
  (매번 전체 경로 입력)                         (자주 쓰는 디렉토리로 스마트 이동)
```

## 🚀 빠른 시작: 5개만 설치한다면

시간이 부족하다면 이 다섯 가지부터 시작하세요 — 가장 큰 생산성 향상을 제공합니다:

| # | 도구 | 이유 | 설치 |
|---|------|-----|---------|
| 1 | **[fzf](tools/终端工具/shell-tools.md#fzf-fuzzy-finder)** | 파일, 히스토리, 프로세스 퍼지 검색 | `brew install fzf` |
| 2 | **[lazygit](tools/终端工具/cli-productivity.md#lazygit)** | Git이 직관적인 비주얼 도구로 변신 | `brew install lazygit` |
| 3 | **[ripgrep](tools/终端工具/shell-tools.md#ripgrep-rg)** | grep보다 10배 빠른 코드 검색 | `brew install ripgrep` |
| 4 | **[GitHub Copilot](tools/AI工具/ai-coding-assistants.md)** | AI 기반 코드 자동 완성 | VS Code 확장 프로그램 설치 |
| 5 | **[starship](tools/终端工具/shell-tools.md#starship-prompt)** | 아름답고 유용한 셸 프롬프트 | `curl -sS https://starship.rs/install.sh \| sh` |

## 📦 도구 개요

| 카테고리 | 설명 | 도구 | 링크 |
|----------|-------------|-------|------|
| 🔤 **터미널 에뮬레이터** | 터미널 에뮬레이터 | Warp, Alacritty, Kitty, WezTerm, iTerm2, Windows Terminal | [→](tools/终端工具/terminal-emulators.md) |
| 🐚 **셸 도구** | 셸 향상 | zsh, fish, starship, zoxide, fzf, ripgrep, fd, bat, eza, delta | [→](tools/终端工具/shell-tools.md) |
| ⚡ **CLI 생산성** | CLI 생산성 도구 | tmux, jq, yq, httpie, lazygit, lazydocker, tldr, navi, direnv, asdf | [→](tools/终端工具/cli-productivity.md) |
| 📝 **VS Code** | VS Code 확장 | 언어, git, AI, 테마, 생산성을 위한 상위 20개 확장 | [→](tools/编辑器/vscode-extensions.md) |
| 💻 **Neovim** | Neovim 설정 | LazyVim, AstroNvim, NvChad, LSP, 플러그인, 키바인딩 | [→](tools/编辑器/neovim-setup.md) |
| 🤖 **AI 코딩 어시스턴트** | AI 코딩 도우미 | Cursor, Copilot, Claude Code, Kimi Code, Windsurf, Cline | [→](tools/AI工具/ai-coding-assistants.md) |
| 🧠 **AI 생산성 도구** | AI 생산성 | ChatGPT, Claude, Perplexity, v0.dev, bolt.new, Replit Agent | [→](tools/AI工具/ai-productivity-tools.md) |
| 🖥️ **로컬 AI** | 로컬 AI 설정 | Ollama, LM Studio, llama.cpp, text-generation-webui | [→](tools/AI工具/local-ai-setup.md) |
| 🔀 **Git 도구** | Git 생산성 | lazygit, gitui, tig, git-flow, pre-commit, husky, commitlint | [→](tools/效率工具/git-tools.md) |
| 🌐 **API 도구** | API 개발 | Bruno, Insomnia, Hoppscotch, httpie | [→](tools/效率工具/api-tools.md) |
| 🎨 **디자인 도구** | 개발자를 위한 디자인 | Excalidraw, tldraw, Figma, Penpot, draw.io, Mermaid | [→](tools/设计工具/design-for-developers.md) |
| 📸 **스크린샷 도구** | 스크린샷 및 문서화 | CleanShot X, Shottr, Kap, ScreenStudio, carbon.now.sh, ray.so | [→](tools/设计工具/screenshot-tools.md) |

## 🔥 추천 선택

### 최고의 터미널 설정

```
Terminal:  WezTerm (cross-platform, Lua config)
Shell:     zsh + oh-my-zsh + zsh-autosuggestions
Prompt:    starship
Search:    fzf + ripgrep + fd
Modern:    bat + eza + delta
```

### 최고의 AI 코딩 스택

```
Editor:    Cursor (or VS Code + Copilot)
CLI:       Claude Code / Kimi Code
Search:    Perplexity
Prototype: v0.dev
Local:     Ollama + Continue
```

### 최고의 생산성 스택

```
Git:       lazygit + pre-commit + commitlint
API:       Bruno (GUI) + httpie (CLI)
Shell:     tmux + direnv + asdf
Diagram:   Excalidraw + Mermaid
Screenshot: CleanShot X (macOS) / ShareX (Windows)
```

## 📖 이 저장소 사용법

1. **카테고리별 탐색** - 위 표의 링크를 클릭하세요
2. **비교 읽기** - 각 파일에 비교표가 있습니다
3. **빠른 시작** - 설치 안내를 따르세요
4. **설정** - 추천 설정을 복사하세요
5. **반복** - 한 번에 하나씩 도구를 추가하고 익숙해진 후 다음으로 넘어가세요

## 🤝 기여

기여를 환영합니다! [기여 가이드](CONTRIBUTING.md)를 먼저 읽어주세요.

- 🐛 버그 제보
- 💡 새 도구 제안
- 📖 문서 개선
- 🔧 오타 수정

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다 — 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 🔗 관련 프로젝트

이러한 관련 프로젝트도 확인해보세요:

- **[awesome-skills](https://github.com/liangzhengtao/awesome-skills)** - 엄선된 AI 스킬 컬렉션
- **[awesome-ai-rules](https://github.com/liangzhengtao/awesome-ai-rules)** - AI 규칙 및 프롬프트
- **[vibe-check](https://github.com/liangzhengtao/vibe-check)** - 프로젝트의 분위기 확인
- **[commit-ai](https://github.com/liangzhengtao/commit-ai)** - AI 기반 커밋 메시지
- **[awesome-mcp-servers](https://github.com/liangzhengtao/awesome-mcp-servers)** - MCP 서버 컬렉션

---

<div align="center">

**[⬆ 맨 위로](#-awesome-dev-tools)**

</div>

---
