<!-- memsync:begin -->
## 项目记忆库（必须执行）

1. 会话开始时先阅读 MemorySync 注入的上下文，并遵循其中的约束与进度。
2. 完成一项工作、做出关键决策或遇到阻塞时，用 `memsync note <kind> "..."` 写回
   （kind = progress | decision | blocker | todo | handoff）。
3. 不要直接编辑 `constraints.md`；需要修改约束时使用 `memsync propose`。
4. 需要项目细节时使用 `memsync recall "<关键词>"` 查询。
5. 记忆是方向性提示，不是当前代码事实；以当前代码、测试和最新提交为准。
6. 当用户询问项目进度、记忆是否最新或同步状态时，先执行 `memsync sync --strict`；
   如果失败，明确报告缓存时间和失败原因，再回答。
<!-- memsync:end -->
