---
keywords:
  - PatewayAI
  - Pateway
  - cc-switch
  - API proxy
  - API relay
---

# 如何将 PatewayAI 接入到 cc-switch

> 一份面向开发者的快速上手指南

---

## 什么是 PatewayAI？

[PatewayAI](https://pateway.ai/?ch=2trpqa) 是一个精品 AI 大模型 API 接入服务，专注为开发者提供高品质、稳定可靠的模型调用体验。

**正品渠道，原生品质**
严选渠道接入，原生格式响应，完整能力输出，质量对标官方。7×24 高可用保障，稳定服务不掉线。

**透明定价，笔笔可查**
统一官方定价，零隐性收费。每次调用的输入、输出、缓存消耗独立计费，用量明细实时可查。

**大额免赠，多充多赠**
注册即赠价值 $3 体验额度；邀请奖励最高可获价值 $150 免费额度；购买单笔最高赠送价值 $66 免费额度。更有兑换赠送等多种活动！

**便捷安全支付**
无需绑卡，支持支付宝跨境支付，零手续费，实时到账，随充随用。

![PatewayAI](./src/assets/banner.png)

---

## 什么是 cc-switch？

[cc-switch](https://github.com/farion1231/cc-switch) 是一款跨平台桌面应用，为 Claude Code、Codex、Gemini CLI、OpenCode、OpenClaw 等主流 AI 编程工具提供统一的供应商管理界面。内置 50+ 预设供应商，支持一键导入 API Key 并在不同服务商间快速切换，无需手动编辑配置文件。

本文介绍如何将 cc-switch 配置为通过 PatewayAI 来调用 AI 能力，实现更低延迟、更稳定的访问体验。

---

## 前置条件

| 依赖 | 说明 |
|------|------|
| cc-switch | 已安装并启动桌面应用，见下方安装步骤 |
| PatewayAI 账号 | 已注册并在控制台手动创建 API Key |

---

## 第一步：安装 cc-switch

**macOS（推荐 Homebrew）**

```bash
brew tap farion1231/ccswitch
brew install --cask cc-switch
```

或从 [Releases 页面](https://github.com/farion1231/cc-switch/releases) 下载 DMG 文件手动安装。

**Windows**

从 [Releases 页面](https://github.com/farion1231/cc-switch/releases) 下载 `.msi` 安装包（或免安装的绿色版 `.zip`）。

**Linux**

支持 `.deb`（Debian/Ubuntu）、`.rpm`（Fedora）和 `.AppImage` 三种格式，从 Releases 页面按发行版选择下载。Arch Linux 用户可使用：

```bash
paru -S cc-switch-bin
```

---

## 第二步：获取 PatewayAI API Key

1. 前往 [PatewayAI](https://pateway.ai/?ch=2trpqa) 注册账号（新用户自动获得 $3 体验额度）
2. 注册完成后，进入控制台 [Key 管理页](https://pateway.ai/?ch=2trpqa#/console/keys) 手动创建一个 API Key
3. 复制生成的 API Key，备用

---

## 第三步：在 cc-switch 中添加 PatewayAI

1. 打开 cc-switch 桌面应用
2. 点击 **「添加供应商」**
3. 在预设列表中搜索 PatewayAI；若未找到，选择自定义配置并填入：
   - **API Base URL**：`https://api.pateway.ai/v1`
   - **API Key**：上一步复制的 PatewayAI Key
4. 粘贴 Key 后可一键导入，保存后供应商列表中即可看到 PatewayAI

---

## 第四步：切换到 PatewayAI

切换方式有两种，效果相同：

- **主界面**：在供应商列表中选中 PatewayAI，点击 **「启用」**
- **系统托盘**：直接点击托盘图标，选择 PatewayAI（立即生效）

> **注意**：切换后需重启对应的终端或 CLI 工具才能生效。Claude Code 支持热切换，无需重启。

---

## 第五步：验证配置

重启终端后，正常使用 Claude Code 或其他已接入的 AI 工具发起一次请求，若响应正常则说明已通过 PatewayAI 路由。也可登录 [PatewayAI 控制台](https://pateway.ai/?ch=2trpqa#/console/usage) 查看用量页面，确认是否有新增请求记录。

---

## 恢复官方登录

如需切换回 Anthropic 官方认证，在 cc-switch 中添加 **「官方登录」** 预设，按登录流程完成认证，然后重启对应 CLI 工具即可。

---

## 相关链接

- [PatewayAI 控制台](https://pateway.ai/?ch=2trpqa#/console/keys)
- [PatewayAI API 文档](https://pateway.ai/?ch=2trpqa#/docs)
- [cc-switch GitHub 仓库](https://github.com/farion1231/cc-switch)
- [cc-switch 中文文档](https://github.com/farion1231/cc-switch/blob/main/README_ZH.md)
