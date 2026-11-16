---
description: 强制拉取团队记忆并反馈成功/失败
---

先检查工作区是否存在 `.memsync/wrapper-active` 文件（PowerShell: `Test-Path .memsync\wrapper-active`）。

- 如果存在：说明由 `memsync run codex` 启动，wrapper 已在沙箱外完成同步；不要运行 `memsync sync`，直接报告“记忆已由 wrapper 同步”，再继续回答。
- 如果不存在：在当前项目目录执行 `memsync sync --strict`。

执行 `sync --strict` 时：

- 如果退出码为 0：说明已从远端拉取最新记忆；引用输出的第一行和当前进度，然后继续回答。
- 如果退出码非 0：把 stderr 的错误原样告诉用户；运行 `memsync status`，报告 last sync/缓存时间与 pending push；明确说明当前记忆可能不是最新，不要声称已同步。
- 如果是在 Codex 沙箱内且错误为 `pull failed (timeout)`：不要反复重试，继续使用本地记忆；结束前用 `memsync note` 写回。
- 不要编辑 `constraints.md`。
