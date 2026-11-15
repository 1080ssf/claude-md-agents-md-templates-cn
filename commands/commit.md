---
description: 查看改动后写一条规范的提交信息并提交（不推送）
---

1. 运行 `git status` 和 `git diff`，确认要提交的内容；如果有明显不该提交的文件（.env、构建产物、大文件），先停下来告诉我。
2. 按 Conventional Commits 写英文提交信息：`<type>(<scope>): <summary>`，type 用 feat / fix / refactor / docs / test / chore。正文简要说明为什么改。
3. 把提交信息给我看，我确认后再执行 `git add` 和 `git commit`。
4. **不要执行 `git push`。**
