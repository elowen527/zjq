# git-commit-push

提交当前项目并推送到 Gitee 远程仓库。

## 远程仓库

- URL: https://gitee.com/elowen527/zjq213
- 平台: Gitee

## 执行步骤

### 1. 检查当前状态

```powershell
git status
git remote -v
```

### 2. 添加远程仓库（如果尚未设置）

检查远程仓库是否已配置，如果没有则添加：

```powershell
git remote add origin https://gitee.com/elowen527/zjq213.git
```

如果 `origin` 已存在但 URL 不同，则更新：

```powershell
git remote set-url origin https://gitee.com/elowen527/zjq213.git
```

### 3. 添加文件并提交

```powershell
git add -A
git commit -m "提交项目：前端练习作品集"
```

如果提交信息需要自定义，询问用户想要的提交信息。

### 4. 推送到远程仓库

```powershell
git push -u origin master
```

如果远程分支不是 `master`，则调整为实际的分支名（如 `main`）。

## 注意事项

- 如果 push 被拒绝（远程仓库非空），先执行 `git pull --rebase origin master` 后再 push
- 确认用户已配置 git 用户名和邮箱（`git config user.name` / `git config user.email`）
- 如遇认证问题，提示用户在 Gitee 上生成并使用 Personal Access Token 作为密码
