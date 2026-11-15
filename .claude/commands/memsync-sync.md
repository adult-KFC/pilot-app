---
description: 强制拉取团队记忆并反馈成功/失败
---

在当前项目目录执行 `memsync sync --strict`。

- 如果退出码为 0：说明已从远端拉取最新记忆；引用输出的第一行和当前进度，然后继续回答。
- 如果退出码非 0：把 stderr 的错误原样告诉用户；运行 `memsync status`，报告 last sync/缓存时间与 pending push；明确说明当前记忆可能不是最新，不要声称已同步。
- 不要编辑 `constraints.md`。
