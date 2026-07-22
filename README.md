<p align="center">
  <img src="assets/app-icon-256.png" alt="鲸灵Git" width="128" height="128" />
</p>

<h1 align="center">鲸灵Git</h1>

<p align="center">
  <strong>现代、轻量的跨平台 Git 桌面客户端</strong>
</p>

<p align="center">
  多仓管理 · 变更与提交 · 分支与同步 · Diff / 历史 · 冲突解决 · 可选 AI（鲸灵）
</p>

<p align="center">
  <a href="https://github.com/DonutGeek/jl-git-releases/releases/latest"><img src="https://img.shields.io/github/v/release/DonutGeek/jl-git-releases?label=Latest&style=flat-square" alt="Latest release" /></a>
  &nbsp;
  <img src="https://img.shields.io/badge/macOS-Apple%20Silicon-black?style=flat-square" alt="macOS" />
  &nbsp;
  <img src="https://img.shields.io/badge/Windows-x64-blue?style=flat-square" alt="Windows" />
  &nbsp;
  <img src="https://img.shields.io/badge/Linux-AppImage-orange?style=flat-square" alt="Linux" />
  &nbsp;
  <img src="https://img.shields.io/badge/Built%20with-Tauri%202-24C8DB?style=flat-square" alt="Tauri" />
</p>

<p align="center">
  <a href="https://github.com/DonutGeek/jl-git-releases/releases/latest"><strong>下载最新版</strong></a>
  &nbsp;·&nbsp;
  <a href="#支持的平台">平台说明</a>
  &nbsp;·&nbsp;
  <a href="#赞助请喝咖啡">赞助</a>
  &nbsp;·&nbsp;
  <a href="#版权与许可">版权</a>
</p>

<p align="center">
  <sub>Copyright © 2026 DonutGeek · All rights reserved</sub>
</p>

---

面向开发者日常本地仓库工作流。基于 **Tauri 2 + React + TypeScript**，追求 **克制、清晰、快**——气质参考 GitHub Desktop、SourceGit、Linear 与 VS Code，而不是视觉炫技或全能 DevOps 控制台。

> **本仓库职责**  
> [jl-git-releases](https://github.com/DonutGeek/jl-git-releases) **仅托管**安装包与线上升级清单（`latest.json`）。  
> 请勿在此提交业务源码。发版由开发仓 GitHub Actions 在打 `v*` tag 时自动上传。

---

## 它因何而生

本地 Git 客户端要么过于臃肿（把 IDE / CI / 看板一并塞进来），要么交互陈旧、跨平台体验割裂。鲸灵Git 想解决的是更窄、也更常见的问题：

- **专注本地 Git**：打开仓库、看清改动、提交与同步，路径短、反馈快  
- **少打断**：用可视化完成高频操作，减少在终端与编辑器之间来回切上下文  
- **可预测**：约定清晰、分层稳定，后续 Diff、Worktree、托管集成与 AI 可以长在同一骨架上，而不推翻重来  
- **体积与性能克制**：桌面壳用 Tauri，安装包与内存占用尽量可控  

**非目标**：替代 IDE、成为 CI/CD 控制台、在应用内重实现完整 Git 对象数据库。

---

## 能做什么

| 领域 | 能力概要 |
|------|----------|
| 项目与标签 | 导入本地仓库、最近打开、多仓库标签切换与持久化 |
| 工作区 | 目录树浏览、状态叠加、外开访达 / 资源管理器 / 文件管理器、编辑器与终端 |
| 变更与提交 | 未暂存 / 已暂存列表，Stage / Unstage，编写提交信息并提交 |
| Diff | 工作区 / 暂存差异预览（含大文件截断与二进制提示） |
| 分支 | 本地 / 远程分支浏览、创建与切换、分支管理与比较等 |
| 历史与标签 | 提交历史浏览、标签创建与删除、文件 / 分支历史子窗等 |
| 同步 | Fetch / Pull / Push（含提交后推送等偏好） |
| 合并与冲突 | Merge 与冲突解决引导（聚焦变更、整文件 / 逐块处理） |
| 应用体验 | 浅色 / 深色 / 跟随系统、中英界面、设置与数据备份、线上升级 |
| AI（鲸灵） | 可选 DeepSeek：提交文案建议、单仓 / 多仓对话等（需自行配置 API Key；**建议 ≠ 自动写库**） |

功能状态以开发仓文档为准；安装包能力随版本递增，请以 [Releases](https://github.com/DonutGeek/jl-git-releases/releases) 说明与应用内版本号为准。

---

## 支持的平台

| 平台 | 架构 | 安装包形态 | 线上升级键（`latest.json`） |
|------|------|------------|------------------------------|
| **macOS** | Apple Silicon（aarch64） | `.dmg`（安装）+ `.app.tar.gz`（升级） | `darwin-aarch64` |
| **Windows** | x64 | NSIS 安装包（`.exe`） | `windows-x86_64` |
| **Linux** | x64 | **AppImage** | `linux-x86_64` |

- Linux 官方参考环境：**Ubuntu 22.04 / 24.04 + GNOME**；其他发行版尽力支持，不承诺全量适配。  
- 系统需已安装 **Git**，且可在 `PATH` 中调用。  
- 窗口装饰：macOS 使用系统 Overlay 交通灯；Windows / Linux 为无边框顶栏 + 自绘窗口控件。

---

## 下载与安装

1. 打开本仓库 [**Releases**](https://github.com/DonutGeek/jl-git-releases/releases)  
2. 选择最新版本中对应平台的安装包  
3. 按系统惯例安装或运行（Linux 请赋予 AppImage 可执行权限后运行）

### 线上升级

客户端通过 updater 读取公开清单（匿名可读）：

```text
https://github.com/DonutGeek/jl-git-releases/releases/latest/download/latest.json
```

清单中的 `platforms` 应包含当前系统键（见上表）。开发模式下的检查更新可能不可用，属预期行为。

---

## 仓库说明（给维护者 / 镜像读者）

| 内容 | 说明 |
|------|------|
| 本仓 | 安装包、签名产物、`latest.json` |
| 开发仓 | 源码、Issue、PR、发版 CI（打 tag 触发上传） |
| 请勿 | 在此提交应用业务代码或密钥 |

---

## 赞助（请喝咖啡）

如果鲸灵Git 对你有帮助，欢迎请作者喝杯咖啡。扫码备注可选「鲸灵Git」——感谢支持。

| 微信支付 | 支付宝 |
|:--------:|:------:|
| ![微信支付收款码](assets/wechat-pay.jpg) | ![支付宝收款码](assets/alipay.jpg) |

赞助为自愿支持，**不绑定**功能解锁或优先技术支持承诺。

---

## 版权与许可

<p align="center">
  <img src="assets/app-icon-256.png" alt="" width="48" height="48" /><br />
  <strong>鲸灵Git</strong><br />
  Copyright © 2026 DonutGeek<br />
  发布方：<a href="https://github.com/DonutGeek">DonutGeek</a>
</p>

本发布仓的安装包与清单文件由 DonutGeek 提供，供用户下载与客户端线上升级使用。源码许可条款以开发仓内 `LICENSE`（若有）为准；若开发仓为私有，则以产品内「关于」及官方说明为准。

第三方组件（Tauri、React、Git 等）遵循各自开源许可。

---

## 隐私与安全提示

- 请仅从本仓库 Releases 或官方文档标明的渠道下载安装包。  
- 线上升级使用签名校验；请勿替换未经验证的 `latest.json` 或安装包。  
- AI 功能需自行配置供应商 API Key；密钥保存在本机，请勿泄露。  
- Git 凭据与 SSH 密钥由本机与系统工具管理，请勿将私钥提交到任何公开仓库。

---

## 联系与反馈

- Releases / 升级问题：优先查看本仓 [Releases](https://github.com/DonutGeek/jl-git-releases/releases) 与 `latest.json` 是否包含你的平台键  
- 产品与开发相关反馈：请前往开发仓（若对你可见）提交 Issue  

---

<p align="center">
  <img src="assets/app-icon-256.png" alt="" width="32" height="32" /><br />
  <sub><strong>鲸灵Git</strong> · Made with care by DonutGeek<br />Copyright © 2026 DonutGeek · All rights reserved</sub>
</p>
