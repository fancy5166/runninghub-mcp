# 一键安装提示词 / One-click Install Prompt

> 开发者：**AI芳程式** ｜ 问题反馈或建议：**zzdh518**
> Developer: **AI芳程式 (AI Fangchengshi)** ｜ Feedback: **zzdh518**

把对应提示词**整段复制**发给你的对话式 Agent（WorkBuddy / OpenClaw / Codex / Claude Desktop / Cursor 等），它会自动完成技能安装并引导你配置 API Key。

Copy the prompt below into your conversational agent (WorkBuddy / OpenClaw / Codex / Claude Desktop / Cursor, etc.). It will install everything automatically and walk you through the API key setup.

---

## 前置条件 / Prerequisites

1. **API Key** — 在 [RunningHub API 管理页面](https://www.runninghub.cn/enterprise-api/consumerApi) 点击「**新建**」创建
2. **账户余额** — 填邀请码注册即得 **500 RH 币**（可免费生成不少图片和视频）；用完后前往 [RunningHub 官网](https://www.runninghub.cn) 充值。**API 调用需要余额**
3. 邀请注册链接 / Invite registration link：[**点击注册 RunningHub**](https://www.runninghub.cn?inviteCode=zlhtnu0f)（邀请码 / invite code：`zlhtnu0f`）
   🎁 填写邀请码 zlhtnu0f，可得 500 RH 币，可以免费生成不少图片和视频哦！
   Enter invite code zlhtnu0f to get 500 RH coins — enough for quite a few free images and videos!

---

## 中文提示词（复制这段）

```text
请帮我安装并配置 **RunningHub 连接器**（开发者：AI芳程式，反馈：zzdh518），让我之后可以直接用自然语言生成图片/视频/音频。

请按以下步骤执行：
1. 检查本机是否已具备运行环境（Node.js 20 或更高版本），若没有请帮我安装。
2. 帮我安装 RunningHub MCP 连接器，并写入我的 MCP 客户端配置文件（WorkBuddy / OpenClaw / Codex / Claude Desktop / Cursor 等）：
   命令：npx -y runninghub-mcp@latest
   若客户端用 json 配置，请写入：
   {
     "mcpServers": {
       "runninghub": {
         "command": "npx",
         "args": ["-y", "runninghub-mcp@latest"],
         "env": { "RUNNINGHUB_API_KEY": "<稍后填入我的 API Key>" }
       }
     }
   }
3. 引导我配置 API Key（若我已有 Key 请提示我粘贴；若没有请带我完成）：
   - 注册账号（邀请链接）：https://www.runninghub.cn?inviteCode=zlhtnu0f （邀请码 zlhtnu0f）
     💰 填写邀请码 zlhtnu0f 可得 500 RH 币，可以免费生成不少图片和视频哦！
   - 打开 API 管理页面点击「新建」创建 API Key：https://www.runninghub.cn/enterprise-api/consumerApi
     （想要完整能力请选择「企业级-共享」类型；该类 Key 才能调用标准模型 API 与 LLM）
   - API 调用需要账户余额；新用户填邀请码已得 500 RH 币免费额度，用完后可前往官网充值：https://www.runninghub.cn
   - 把 Key 填入上面的配置并重启生效
4. 安装完成后帮我验证连接是否成功（例如列出几个可用模型），并告诉我在哪些地方能看到结果。
5. 以后我说需求时，请自动帮我：搜索合适的模型 → 提交任务 → 等待完成 → 把生成结果（图片/视频/音频链接）给我，必要时下载到本地。
```

---

## English prompt (copy this block)

```text
Please install and configure the **RunningHub connector** for me (developer: AI芳程式 / AI Fangchengshi, feedback: zzdh518) so I can generate images/videos/audio in plain language afterwards.

Steps:
1. Check whether Node.js 20+ is available locally; install it if not.
2. Install the RunningHub MCP connector and write it into my MCP client config (WorkBuddy / OpenClaw / Codex / Claude Desktop / Cursor, etc.):
   Command: npx -y runninghub-mcp@latest
   If my client uses a json config, add:
   {
     "mcpServers": {
       "runninghub": {
         "command": "npx",
         "args": ["-y", "runninghub-mcp@latest"],
         "env": { "RUNNINGHUB_API_KEY": "<my API key, to be filled in later>" }
       }
     }
   }
3. Walk me through the API key setup (if I already have one, just ask me to paste it):
   - Register (invite link): https://www.runninghub.cn?inviteCode=zlhtnu0f (invite code zlhtnu0f)
     💰 Enter invite code zlhtnu0f to get 500 RH coins — enough for quite a few free images and videos!
   - Click "新建" (Create) on the API management page: https://www.runninghub.cn/enterprise-api/consumerApi
     (choose the "Enterprise-Shared" key type to unlock all capabilities, including standard model APIs and LLM)
   - Top up my RunningHub balance — **API calls require balance**: https://www.runninghub.cn
   - Put the key into the config above and restart the client
4. After installation, verify the connection for me (e.g. list a few available models) and tell me where to find results.
5. From then on, when I describe a need, automatically: search for a suitable model → submit the task → wait for completion → give me the result links (and download them locally when asked).
```

---

## 子连接器版本 / Scope variants

图像 / 视频 / 音频专用连接器，把提示词中的命令与配置换成对应 scope 即可：

| 连接器 | 命令 / Command | mcpServers key |
| --- | --- | --- |
| 全能 All-in-one | `npx -y runninghub-mcp@latest` | `runninghub` |
| 图像 Image | `npx -y runninghub-mcp@latest --scope image` | `runninghub-image` |
| 视频 Video | `npx -y runninghub-mcp@latest --scope video` | `runninghub-video` |
| 音频 Audio | `npx -y runninghub-mcp@latest --scope audio` | `runninghub-audio` |

---

## 常见追问 / Follow-up questions you can ask

- 「用 RunningHub 画一张宇航猫，2K 分辨率」
- 「把 D:/照片.jpg 用图生视频做成 5 秒短片」
- 「用 RunningHub 的 TTS 把这段文案读出来」
- 「刚才那个任务好了吗？」
- 「把结果下载到 D:/输出」

- "Draw an astronaut cat with RunningHub at 2K"
- "Turn D:/photos/pic.jpg into a 5-second video"
- "Read this copy out loud with RunningHub TTS"
- "Is my task done yet?"
- "Download the result to D:/output"
