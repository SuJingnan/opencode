提交并推送 my-feature 分支到 GitHub。

**流程：**

1. 查看当前状态：
```bash
git status
```

2. 如果没有任何修改和未跟踪文件，告诉我"没有需要提交的内容"并结束。

3. 如果有修改，展示变更列表给我看，并生成一条简洁的 commit message（中文，一句话说明改了什么）。问我是否确认提交。

4. 我确认后执行：
```bash
git add <相关文件>
git commit -m "commit message"
```

5. 推送到远程：
```bash
git push origin my-feature
```

如果因为 rebase 导致需要 force push，先提示我确认再执行。

6. 完成后报告推送结果。
