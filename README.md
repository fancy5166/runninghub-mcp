# runninghub-mcp

> Developer: **AI芳程式** ｜ Feedback & suggestions: **zzdh518**
> 开发者：**AI芳程式** ｜ 问题反馈 / 建议：**zzdh518**

RunningHub 多模态 AI 能力的 **MCP 服务器**（Model Context Protocol，stdio），可接入 WorkBuddy、Claude Desktop、Cursor、OpenClaw 等任意 MCP 客户端。

A stdio MCP server exposing RunningHub's 350+ model APIs (image / video / audio / 3D), ComfyUI workflows, AI apps and LLM chat.

> **30 秒判断要不要用**：你已经在用 Claude Desktop / Cursor / WorkBuddy / OpenClaw，想让它直接会画图、剪片、配音、跑 ComfyUI 工作流——装这一个就够了。
> **30-second check**: you already use an MCP client and want it to actually generate images / videos / audio and run ComfyUI workflows — this is the one to install.
> 下面是它的完整定位、能解决的问题，以及家族里其它 5 个仓库。Below: what this repo is, what it solves, and the other five repos in the family.


## 🧭 本仓库在家族里的位置 / Where this repo fits

| | |
| --- | --- |
| **本仓库 / This repo** | ⚙️ **runninghub-mcp** — 核心 MCP 服务器 |
| **品类 / Category** | 核心引擎 · MCP 服务器（npm 包，非连接器） |
| **形态 / Form** | npm 包 `runninghub-mcp`（stdio MCP 服务器，源码闭源） |
| **独立可用 / Standalone** | ✅ 单独安装即可用，一条 `npx` 命令跑起来（核心引擎经 npm 分发，源码闭源） |
| **联动可用 / Interop** | ✅ 与家族其它 5 个仓库共用同一套 RunningHub 账号与 API Key，可任选组合安装 |
| **适合谁 / Who it's for** | 开发者 / Agent 玩家 / 自己搭工作流的人 |
| **解决的痛点 / Pain it kills** | 想让自己常用的 AI 客户端直接用上 350+ 多模态模型，但每个模型一套 API、每个客户端一套接入方式，胶水代码写不完。 |
| **给你的价值 / What you get** | 一条 npx 命令把 350+ 模型 + ComfyUI 工作流 + AI 应用 + LLM 接到任意 MCP 客户端；零构建零 lock-in，--scope 还能裁成轻量后端。 |

### 🚀 两种用法 / Two ways to use it

**A. 只装这一个（独立部署，最小依赖）** — 你只想在这一个品类上用 AI：

- **WorkBuddy 用户**：在连接器市场搜「RunningHub」，装这一个就行（见下方「安装」）。
- **任意 MCP 客户端 / 开发者**：一条 `npx` 命令，核心引擎经 npm 分发（本仓库是 npm 包的官方落地页）：

```bash
# 方式一：npx 直接跑（推荐，需要 runninghub-mcp 已发布到 npm）
npx -y runninghub-mcp@latest

# 方式二：写进 MCP 客户端配置
# { "command": "npx", "args": ["-y", "runninghub-mcp@latest"] }
```

> `--scope` 让后端只加载本品类模型：启动更快、上下文更省、也更不容易挑错模型。

**B. 家族联动（图 + 视频 + 音频一次到位）** — 你想让 AI 一次干完整条链路：

同一个 API Key 下装多个连接器，或在 WorkBuddy 里直接装**全能连接器** [runninghub-connector](https://github.com/fancy5166/runninghub-connector)——一个顶四个；开发者还可以直接用核心引擎 [runninghub-mcp](https://github.com/fancy5166/runninghub-mcp) 自己拼。

### 🔗 家族全部仓库 / The whole family

| | 仓库 / Repo | 品类 / Category | 一句话 / In one line |
| --- | --- | --- | --- |
| 🏠 | **[runninghub-workbuddy-connectors](https://github.com/fancy5166/runninghub-workbuddy-connectors)** | 家族总入口 · 导航与安装指南 | 6 个包的介绍、安装指南与 4 个可直接上传 WorkBuddy 的连接器 zip，一次看全 |
| 🧰 | **[runninghub-connector](https://github.com/fancy5166/runninghub-connector)** | 全能 · 图 + 视 + 音 + 3D + 工作流 + LLM | 一个连接器顶掉一堆账号：350+ 模型，一句话从出图切到出片再切到配音 |
| 🎨 | **[runninghub-image-connector](https://github.com/fancy5166/runninghub-image-connector)** | 图像 · 90+ 图像模型 | 电商主图、模特换背景、老图 4K 放大，中文提示词直接可用 |
| 🎬 | **[runninghub-video-connector](https://github.com/fancy5166/runninghub-video-connector)** | 视频 · 200+ 视频模型 | 一条片子不用换五个平台，首尾帧与数字人口播全覆盖 |
| 🔊 | **[runninghub-audio-connector](https://github.com/fancy5166/runninghub-audio-connector)** | 音频 · 50+ 音频模型 | 配音、配乐、人声分离一站搞定，不用买音色包 |

> 💡 **不确定装哪个？** 先装全能连接器 [runninghub-connector](https://github.com/fancy5166/runninghub-connector) 一个就够；
> 只做图片就装 [runninghub-image-connector](https://github.com/fancy5166/runninghub-image-connector)，
> 只做视频装 [runninghub-video-connector](https://github.com/fancy5166/runninghub-video-connector)，
> 只做配音/音乐装 [runninghub-audio-connector](https://github.com/fancy5166/runninghub-audio-connector)，
> 要自己二次开发从 [runninghub-mcp](https://github.com/fancy5166/runninghub-mcp) 入手。

> 全部由 **AI芳程式** 开发，问题反馈或建议请联系 **zzdh518**。


> 🔒 **关于源码 / About the source**: 本仓库是 **npm 包 `runninghub-mcp` 的官方落地页**，不包含服务器源码。
> This repo is the official landing page for the npm package `runninghub-mcp` — the server source is not public.

一键安装提示词 / One-click install prompt：[`INSTALL_PROMPT.md`](INSTALL_PROMPT.md)

## 安装 / Install

```bash
npx -y runninghub-mcp@latest                 # 全部能力 / all capabilities
npx -y runninghub-mcp@latest --scope image   # 仅图像 / image only
npx -y runninghub-mcp@latest --scope video   # 仅视频 / video only
npx -y runninghub-mcp@latest --scope audio   # 仅音频 / audio only
```

MCP 客户端配置示例 / Client config:

```json
{
  "mcpServers": {
    "runninghub": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "runninghub-mcp@latest"],
      "env": { "RUNNINGHUB_API_KEY": "你的 API Key / your API key" }
    }
  }
}
```

## 前置条件 / Prerequisites

1. **API Key** — 在 [RunningHub API 管理页面](https://www.runninghub.cn/enterprise-api/consumerApi) 点「**新建**」创建
2. **账户余额** — 用邀请码注册即送 **500 RH 币**（可免费生成不少图片和视频）；用完后到 [RunningHub 官网](https://www.runninghub.cn) 充值
3. 还没有账号？[**RunningHub 邀请注册链接**](https://www.runninghub.cn?inviteCode=zlhtnu0f) —— **填写邀请码 `zlhtnu0f`，可得 500 RH 币，可以免费生成不少图片和视频哦！**

## 工具 / Tools

| Tool | 说明 |
| --- | --- |
| `runninghub_search_models` | 搜索 350+ 模型目录，返回 endpoint 与说明 |
| `runninghub_list_models` | 按类别浏览模型（image / video / audio / other） |
| `runninghub_submit_task` | 提交标准模型任务（可选自动等待） |
| `runninghub_query_task` | 查询任务状态与结果（v2 / legacy） |
| `runninghub_wait_task` | 轮询等待任务完成，返回结果 URL |
| `runninghub_upload_file` | 上传本地文件（图片 / 视频 / 音频 / 压缩包） |
| `runninghub_download_file` | 下载结果文件到本地 |
| `runninghub_run_workflow` | 运行 ComfyUI 工作流任务 |
| `runninghub_run_ai_app` | 运行 AI 应用（WebApp）任务 |
| `runninghub_get_app_nodes` | 获取应用 / 工作流可修改节点 |
| `runninghub_cancel_task` | 取消工作流任务 |
| `runninghub_llm_chat` | LLM 对话（OpenAI 兼容协议） |

一键安装提示词 / One-click install prompt：[`INSTALL_PROMPT.md`](INSTALL_PROMPT.md)

## 环境变量 / Environment variables

| 变量 | 默认值 | 说明 |
| --- | --- | --- |
| `RUNNINGHUB_API_KEY` | — | 必填 / required |
| `RH_API_BASE` | `https://www.runninghub.cn` | API 域名 |
| `RH_LLM_BASE` | `https://llm.runninghub.cn` | LLM 域名 |
| `RH_SCOPE` | `all` | `all` / `image` / `video` / `audio` |

## 常见问题 / FAQ

**Q: 这个仓库怎么没有代码？/ Where is the code?**
引擎（MCP 服务器本体）以 **npm 包 `runninghub-mcp`** 的形式分发，源码闭源。本仓库只承载安装说明、文档与家族导航。
The MCP server is distributed as the npm package `runninghub-mcp` (closed source). This repo hosts docs only.

**Q: 不想用 npm 怎么办？**
安装下面 5 个 WorkBuddy 连接器包即可——它们内置引导，无需接触任何代码。

## 许可证 / License

[MIT](LICENSE) © AI芳程式
