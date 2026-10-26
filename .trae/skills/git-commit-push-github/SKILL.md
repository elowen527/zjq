---
name: git-commit-push-github
description: 提交整个项目并推送到 GitHub 远程仓库 elowen527/zjq。当用户要求提交代码、push 到 GitHub、同步项目到 GitHub 时使用。不适用于推送到 Gitee（Gitee 走 origin）。
---

# git-commit-push-github

提交当前项目并推送到 GitHub 远程仓库。

## 远程仓库

- 仓库页面：https://github.com/elowen527/zjq
- SSH 地址：`git@github.com:elowen527/zjq.git`（SSH 公钥已配置）
- 远程名称：`github`（`origin` 已被 Gitee 占用，勿覆盖）
- 平台：GitHub

## 执行步骤

### 1. 检查当前状态

```powershell
git status
git remote -v
git branch --show-current
```

### 2. 添加远程仓库（如果尚未设置）

```powershell
git remote add github git@github.com:elowen527/zjq.git
```

如果 `github` 已存在但 URL 不同，则更新：

```powershell
git remote set-url github git@github.com:elowen527/zjq.git
```

### 3. 添加文件并提交

```powershell
git add -A
git commit -m "提交项目：前端练习作品集"
```

如果提交信息需要自定义，询问用户想要的提交信息。

### 4. 推送到 GitHub

```powershell
git push -u github master
```

分支名以第 1 步查到的实际分支为准（如 `main`）。

## 注意事项

- 本环境为 PowerShell 5，不支持 `&&` 连接命令，必须逐步执行
- **必须先执行** `git config core.sshCommand "C:/Windows/System32/OpenSSH/ssh.exe"`（仓库级）：本机中文用户名导致 git 自带的 MSYS ssh 无法定位 `~/.ssh` 密钥（Permission denied），Windows OpenSSH 不受影响
- 22 端口被网络限制：远程 URL 固定使用 `ssh://git@ssh.github.com:443/elowen527/zjq.git`（443 端口），已验证可用
- 若 push 显示 `Everything up-to-date`，用 `git ls-remote github` 对照远程 HEAD 与本地 `git log --oneline -1` 确认真实状态（传输可能已成功、仅收尾报错）
- 若 push 被拒绝且远程仓库非空，先 `git pull --rebase github <分支>` 再 push；确需覆盖远程历史时必须先征得用户明确同意
- 推送成功以 `git ls-remote github` 中远程分支指向本地最新提交为准，确认后再向用户报告
