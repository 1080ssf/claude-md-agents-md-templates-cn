# Claude Code CLAUDE.md / Codex AGENTS.md 中文模板库

> 开箱即用的 **CLAUDE.md、AGENTS.md 项目指令模板**、**自定义斜杠命令（slash commands）**和**省 token 技巧**，适用于 Claude Code、Codex CLI、Cursor、Cline 等 AI 编程工具。全部中文，复制到项目里改两行就能用。
>
> Chinese templates for CLAUDE.md / AGENTS.md, Claude Code slash commands and token-saving tips for AI coding agents.

## 为什么要写 CLAUDE.md / AGENTS.md

AI 编程工具每次开新会话都「失忆」。项目根目录的 `CLAUDE.md`（Claude Code 读）或 `AGENTS.md`（Codex、Cursor 等读）会在每次会话开头自动加载，相当于给 AI 的「项目说明书 + 团队规矩」。写好它能明显减少：

- 用错命令、改错目录、引入你不想要的依赖；
- 每次都要重复解释项目结构；
- 越改越乱、不跑测试就说「已完成」。

## 模板目录

| 模板 | 适合 | 文件 |
|---|---|---|
| 通用版 | 任何项目，先从这个开始 | [templates/general.md](templates/general.md) |
| 前端（React / Vue + TypeScript） | Web 前端 | [templates/frontend.md](templates/frontend.md) |
| 后端（Go / Java / Node 服务） | API 服务 | [templates/backend.md](templates/backend.md) |
| Python 脚本与数据处理 | 爬虫、数据分析、自动化 | [templates/python.md](templates/python.md) |
| 全局个人偏好 | `~/.claude/CLAUDE.md`，对所有项目生效 | [templates/global.md](templates/global.md) |

用法：

```bash
# Claude Code
cp templates/general.md 你的项目/CLAUDE.md
# Codex / Cursor / 其他读 AGENTS.md 的工具
cp templates/general.md 你的项目/AGENTS.md
```

两个文件内容可以完全一样；只用一个工具就只放一个。

## 斜杠命令（Claude Code）

把 [`commands/`](commands/) 里的文件放进项目的 `.claude/commands/`，在 Claude Code 里输入 `/文件名` 就能调用：

| 命令 | 作用 |
|---|---|
| `/handoff` | 把当前会话压缩成交接说明，开新会话继续（省 token 的关键） |
| `/review` | 按清单审查当前改动：正确性、边界、安全、测试 |
| `/commit` | 看完改动后写一条规范的提交信息（不会自动推送） |
| `/plan` | 动手前先出计划和验证方式，等你确认 |

## 省 token、提速技巧

见 [tips.md](tips.md)：长会话为什么越来越慢越来越贵、怎么分阶段、什么时候换小模型。

## 配合第三方 API 使用

这些模板与模型无关。想用 DeepSeek、GLM、Kimi 等第三方 API 跑 Claude Code / Codex，配置方法见姊妹项目：
👉 [claude-code-codex-api-config-cn](https://github.com/1080ssf/claude-code-codex-api-config-cn)

示例服务商：[Imagio](https://imagio.site)（DeepSeek / GLM / Kimi，OpenAI 与 Anthropic 协议兼容）。

## 交流群

QQ 群：**1125429694**

## 贡献

欢迎 PR 补充更多技术栈的模板（Rust、Flutter、Spring Boot、小程序……）。模板要求：短、具体、可执行，不写空话。

## 许可

MIT
