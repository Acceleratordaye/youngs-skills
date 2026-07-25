# Young's Skills

一个用于整理和公开个人 Agent Skills 的仓库，当前主要收录各平台创作者账号研究工作流。

## Skills

### 抖音技术账号深度调查助手

路径：[`account-research-skills/douyin-technical-account-research`](./account-research-skills/douyin-technical-account-research)

用于研究已登录抖音账号中的技术类创作者，支持：

- 账号身份与关联账号核查
- `scan → classify → deep dive` 内容研究流程
- 视频、图文和高价值评论研究
- 教程步骤与技术原理提炼
- 作者宣传、作者教程、用户反馈、作者回复四层证据模型
- TradingView、交易指标、量化软件和自动交易工具专项分析
- 主动停止条件与浏览额度控制
- 中文研究记录和最终报告模板
- 网页端、桌面端与移动端交互差异处理

## 目录结构

```text
account-research-skills/
└── douyin-technical-account-research/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── assets/
        ├── research-notes-template.md
        └── final-report-template.md
```

## 安装

### Codex

可让 Codex 从本仓库安装以下 Skill 目录：

```text
https://github.com/Acceleratordaye/youngs-skills/tree/main/account-research-skills/douyin-technical-account-research
```

也可以下载仓库后，将完整的 `douyin-technical-account-research` 目录复制到个人 Skills 目录。

## 使用

安装后，在任务中明确调用：

```text
使用 $douyin-technical-account-research 调查当前内置浏览器中打开的抖音技术账号。
```

开始调查前，应先在支持的浏览器环境中登录抖音并打开目标账号主页。遇到登录失效、验证码或安全验证时，Skill 会暂停并等待用户处理。

## 设计边界

这是纯工作流 Skill：

- 不包含 Plugin
- 不创建外部 API
- 不创建工具连接
- 不包含批量抓取或绕过平台验证的逻辑

默认优先使用 ChatGPT Desktop built-in browser；未经用户明确允许，不自动切换其他浏览器环境。
