一站式同步流程：从上游拉取最新代码，同步到 dev，然后让我选择性合入 my-feature。

**流程：**

1. 拉取上游最新并同步 dev：
```bash
git fetch upstream
git checkout dev
git merge upstream/dev
git push origin dev
```

2. 切回 my-feature，列出还没有的 commit：
```bash
git checkout my-feature
git log my-feature..dev --oneline
```

3. 如果没有新 commit，告诉我"已经是最新"。如果有新 commit：
   - 把结果展示给我，每条 commit 前标上序号
   - 对每条 commit 用 `git show --stat <hash>` 简要说明涉及的文件和改动

4. 然后问我想怎么处理，给我以下选项：
   - **全部同步**：执行 `git rebase dev`
   - **选择特定 commit**：我指定序号或 commit hash，按时间顺序执行 `git cherry-pick <commits>`
   - **跳过**：什么都不做

5. 如果有冲突，暂停并告诉我冲突详情，让我决定怎么处理。

6. 最终报告 my-feature 的当前状态。
