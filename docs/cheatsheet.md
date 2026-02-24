# GitHub 命令速查卡

> 打印出来放在手边，随时查阅

---

## 初始化配置

```bash
# 配置用户信息（首次使用）
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 登录 GitHub CLI
gh auth login
```

---

## 仓库操作

| 任务 | 命令 |
|------|------|
| 初始化仓库 | `git init` |
| 克隆仓库 | `git clone URL` |
| 创建远程仓库 | `gh repo create 名称 --public` |
| 查看仓库状态 | `git status` |

---

## 日常工作流

```bash
git pull          # 1. 拉取最新
# ... 修改代码 ...
git add .         # 2. 添加修改
git commit -m ""  # 3. 提交
git push          # 4. 推送
```

---

## 提交操作

| 任务 | 命令 |
|------|------|
| 添加所有文件 | `git add .` |
| 添加指定文件 | `git add 文件名` |
| 提交 | `git commit -m "说明"` |
| 查看历史 | `git log --oneline` |
| 查看差异 | `git diff` |

---

## 分支操作

| 任务 | 命令 |
|------|------|
| 查看分支 | `git branch` |
| 创建分支 | `git branch 名称` |
| 切换分支 | `git checkout 名称` |
| 创建+切换 | `git checkout -b 名称` |
| 合并分支 | `git merge 名称` |
| 删除分支 | `git branch -d 名称` |

---

## 远程操作

| 任务 | 命令 |
|------|------|
| 查看远程仓库 | `git remote -v` |
| 添加远程仓库 | `git remote add origin URL` |
| 推送 | `git push origin main` |
| 拉取 | `git pull origin main` |
| 首次推送 | `git push -u origin main` |

---

## 撤销操作

| 任务 | 命令 |
|------|------|
| 撤销工作区修改 | `git checkout -- 文件名` |
| 撤销暂存 | `git reset HEAD 文件名` |
| 撤销最后一次提交 | `git reset --soft HEAD~1` |
| 完全回退 | `git reset --hard HEAD~1` |

---

## GitHub CLI

| 任务 | 命令 |
|------|------|
| 登录状态 | `gh auth status` |
| 创建仓库 | `gh repo create 名称 --public` |
| 查看仓库 | `gh repo view` |
| 打开网页 | `gh repo view --web` |
| 列出仓库 | `gh repo list` |

---

## 常见问题解决

```bash
# 推送被拒绝
git pull --rebase origin main
git push origin main

# 合并冲突
# 1. 手动编辑冲突文件
# 2. git add .
# 3. git commit -m "解决冲突"

# 忘记切换分支就修改了
git stash          # 暂存修改
git checkout 分支  # 切换分支
git stash pop      # 恢复修改
```

---

## 提交信息规范

| 前缀 | 用途 |
|------|------|
| `feat:` | 新功能 |
| `fix:` | 修复 bug |
| `docs:` | 文档 |
| `style:` | 格式 |
| `refactor:` | 重构 |
| `test:` | 测试 |

---

## 文件状态

```
??  未跟踪（新文件）
A   已添加到暂存区
M   已修改
D   已删除
```
