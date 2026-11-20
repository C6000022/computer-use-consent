# Computer Use 事前确认

一个 Codex 技能，在读取或操作桌面应用或浏览器界面之前先取得用户明确同意。确认涵盖目标、用途、具体操作及是否修改数据。连续操作共用同一范围的同意，扩大范围或开始新任务时重新确认。

## 安装

将仓库克隆到 Codex 的用户技能目录。已有同名技能时，检查现有安装路径并使用同一份副本。

```sh
git clone https://github.com/C6000022/computer-use-consent.git "$HOME/.agents/skills/computer-use-consent"
```

## 启用全局确认

把下面的段落追加到 Codex 的全局 `AGENTS.md`，默认路径为 `~/.codex/AGENTS.md`。如果设置了 `CODEX_HOME`，请使用该目录中的文件。如果存在非空的 `AGENTS.override.md`，请将段落追加到该文件。若技能安装在别处，请把段落中的路径替换成实际路径。

```markdown
## Computer Use 事前确认

准备使用 Computer Use 读取或操作桌面应用或浏览器界面时，先读取 `~/.agents/skills/computer-use-consent/SKILL.md`。无论技能是否已加载，首次初始化、枚举窗口或标签页、截图、读取界面或执行操作之前，必须说明目标、用途和拟执行的操作，并等待用户明确同意。即使原任务已点名 Computer Use，也必须先询问。批准仅适用于当前任务和获准范围。扩大范围或开始新任务时重新询问。通过其他工具或代理完成同样的界面操作时适用同一规则。
```

开启一个新的 Codex 会话后，可要求它用 Computer Use 查看计算器。预期行为是先提出确认，等待同意后再访问界面。

## 适用边界

本方案依赖 Codex 遵循全局指令。它无法在工具层强制拦截调用，Codex 自带的权限提示和交接规则仍适用。普通文件访问、命令行、API 和网页检索可按各自规则使用。

[Codex 技能文档](https://learn.chatgpt.com/docs/build-skills) · [全局 AGENTS.md 说明](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
