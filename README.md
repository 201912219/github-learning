# GitHub 完整学习教程

> 专为新手设计，从零开始掌握 GitHub

---

## 学习路线图

```
第1章 ──→ 第2章 ──→ 第3章 ──→ 第4章 ──→ 第5章 ──→ 第6章
基础      仓库      分支      协作      进阶      实战
```

---

## 目录

| 章节 | 主题 | 内容 | 状态 |
|------|------|------|------|
| [第1章](#第1章-git-基础) | Git 基础 | 安装、配置、核心概念 | ⏳ 待学习 |
| [第2章](#第2章-仓库操作) | 仓库操作 | 创建、克隆、上传项目 | ⏳ 待学习 |
| [第3章](#第3章-日常操作) | 日常操作 | 修改、提交、更新代码 | ✅ 进行中 |
| [第4章](#第4章-分支管理) | 分支管理 | 创建、切换、合并分支 | ⏳ 待学习 |
| [第5章](#第5章-协作开发) | 协作开发 | Fork、PR、Code Review | ⏳ 待学习 |
| [第6章](#第6章-实战项目) | 实战项目 | 完整项目上传流程 | ⏳ 待学习 |

---

## 第1章 Git 基础

### 1.1 什么是 Git 和 GitHub？

| 概念 | 说明 |
|------|------|
| **Git** | 版本控制工具（软件），记录文件的每次修改 |
| **GitHub** | 代码托管平台（网站），存储和分享代码 |

**类比理解：**
- Git = 你的本地编辑器（记录每次修改）
- GitHub = 云端网盘（同步+分享）

### 1.2 核心概念

```
工作目录(你编辑文件的地方)
    │
    ▼ git add
暂存区(准备提交的文件)
    │
    ▼ git commit
本地仓库(本地的版本历史)
    │
    ▼ git push
远程仓库(GitHub上的仓库)
```

### 1.3 必会命令速查

| 命令 | 作用 | 示例 |
|------|------|------|
| `git init` | 初始化仓库 | `git init` |
| `git clone` | 克隆远程仓库 | `git clone URL` |
| `git status` | 查看状态 | `git status` |
| `git add` | 添加到暂存区 | `git add .` |
| `git commit` | 提交更改 | `git commit -m "说明"` |
| `git push` | 推送到远程 | `git push` |
| `git pull` | 拉取更新 | `git pull` |

---

## 第2章 仓库操作

### 2.1 创建仓库的三种方式

#### 方式一：在 GitHub 网页创建
1. 登录 GitHub → 点击 `+` → `New repository`
2. 填写仓库名（如：`my-project`）
3. 勾选 `Add a README file`
4. 点击 `Create repository`

#### 方式二：用命令行创建
```bash
# 创建本地仓库
mkdir my-project
cd my-project
git init

# 创建 README 文件
echo "# 我的项目" > README.md

# 提交
git add .
git commit -m "初始化项目"

# 连接远程仓库并推送
git remote add origin https://github.com/你的用户名/my-project.git
git push -u origin main
```

#### 方式三：用 GitHub CLI 创建
```bash
gh repo create my-project --public --clone
```

### 2.2 项目标准结构

```
my-project/
├── README.md          # 项目说明（必需）
├── .gitignore         # 忽略文件（推荐）
├── LICENSE            # 开源协议（可选）
├── docs/              # 文档目录
│   └── guide.md
├── src/               # 源代码目录
│   ├── main.py
│   └── utils.py
├── tests/             # 测试目录
│   └── test_main.py
└── requirements.txt   # 依赖列表（Python）
```

### 2.3 README.md 写法

```markdown
# 项目名称

简短描述你的项目是做什么的

## 安装

\`\`\`bash
pip install -r requirements.txt
\`\`\`

## 使用方法

\`\`\`bash
python main.py
\`\`\`

## 功能

- 功能1
- 功能2

## 作者

你的名字
```

---

## 第3章 日常操作

### 3.1 修改代码的标准流程

```bash
# 1. 查看当前状态
git status

# 2. 查看具体修改
git diff

# 3. 添加修改到暂存区
git add 文件名        # 添加单个文件
git add .            # 添加所有修改

# 4. 提交修改
git commit -m "简短描述你做了什么"

# 5. 推送到 GitHub
git push
```

### 3.2 提交信息的写法

**好的提交信息：**
```
✅ 添加用户登录功能
✅ 修复首页显示bug
✅ 更新README文档
✅ 优化数据库查询性能
```

**不好的提交信息：**
```
❌ 修改
❌ 更新
❌ 111
❌ asdfasdf
```

**提交类型前缀：**
| 前缀 | 用途 |
|------|------|
| `feat:` | 新功能 |
| `fix:` | 修复bug |
| `docs:` | 文档更新 |
| `style:` | 代码格式调整 |
| `refactor:` | 重构代码 |

### 3.3 拉取最新代码

```bash
# 在开始工作前，先拉取最新代码
git pull

# 如果有冲突，解决后再提交
```

---

## 第4章 分支管理

### 4.1 什么是分支？

```
main ────●────●────●────●
              ╲
feature ───────●────●────●
```

分支让你可以：
- 在不影响主分支的情况下开发新功能
- 多人同时开发不同功能
- 安全地实验新想法

### 4.2 分支操作

```bash
# 查看所有分支
git branch

# 创建新分支
git branch feature-login

# 切换分支
git checkout feature-login

# 创建并切换（推荐）
git checkout -b feature-login

# 合并分支（先切换到 main）
git checkout main
git merge feature-login

# 删除分支
git branch -d feature-login
```

### 4.3 分支命名规范

| 分支名 | 用途 |
|--------|------|
| `main` | 主分支，稳定版本 |
| `develop` | 开发分支 |
| `feature/xxx` | 新功能开发 |
| `bugfix/xxx` | 修复bug |
| `hotfix/xxx` | 紧急修复 |

---

## 第5章 协作开发

### 5.1 Fork 工作流

```
原作者仓库 ──Fork──→ 你的仓库 ──PR──→ 原作者仓库
     │                   │
     └─── Clone ─────────┘
```

### 5.2 Pull Request 流程

1. **Fork** 他人的仓库
2. **Clone** 到本地
3. **创建分支** 进行修改
4. **Commit & Push** 更改
5. **创建 PR** 请求合并
6. **等待审核** 和合并

### 5.3 Issues 使用

Issues 用于：
- 报告 bug
- 提出新功能建议
- 讨论问题

**好的 Issue 模板：**
```markdown
## 问题描述
简要描述遇到的问题

## 复现步骤
1. 打开...
2. 点击...
3. 看到...

## 期望结果
应该...

## 实际结果
实际...

## 环境
- 操作系统：Windows 10
- 浏览器：Chrome 120
```

---

## 第6章 实战项目

### 6.1 上传完整项目的步骤

```bash
# 1. 在 GitHub 创建空仓库（不要勾选 README）

# 2. 在本地项目目录初始化
cd my-project
git init

# 3. 创建 .gitignore（排除不需要上传的文件）
```

### 6.2 .gitignore 模板

```gitignore
# Python
__pycache__/
*.pyc
.env
venv/

# Node.js
node_modules/
dist/

# IDE
.vscode/
.idea/
*.swp

# 系统文件
.DS_Store
Thumbs.db

# 敏感文件
config.local
secrets.json
*.key
```

### 6.3 完整上传流程

```bash
# 1. 初始化
git init

# 2. 添加所有文件
git add .

# 3. 首次提交
git commit -m "Initial commit: 项目初始化"

# 4. 连接远程仓库
git remote add origin https://github.com/用户名/项目名.git

# 5. 推送（首次需要 -u）
git push -u origin main
```

### 6.4 日常更新流程

```bash
# 每次修改后
git add .
git commit -m "描述你的修改"
git push
```

---

## 练习目录

| 练习 | 文件 | 难度 | 状态 |
|------|------|------|------|
| 练习1 | `exercises/exercise-1.md` | ⭐ | ✅ 已完成 |
| 练习2 | `exercises/exercise-2.md` | ⭐⭐ | ⏳ 待完成 |
| 练习3 | `exercises/exercise-3.md` | ⭐⭐ | ⏳ 待完成 |
| 练习4 | `exercises/exercise-4.md` | ⭐⭐⭐ | ⏳ 待完成 |

---

## 常见问题

### Q: 提示 "fatal: not a git repository"？
**A:** 你需要先运行 `git init` 初始化仓库

### Q: 推送失败提示 "Permission denied"？
**A:** 检查是否已登录：`gh auth status`

### Q: 如何撤销最后一次提交？
```bash
git reset --soft HEAD~1  # 撤销提交，保留更改
git reset --hard HEAD~1  # 撤销提交，丢弃更改
```

### Q: 如何查看历史记录？
```bash
git log                 # 详细历史
git log --oneline       # 简洁历史
```

---

## 下一步

1. 完成所有练习
2. 创建自己的项目仓库
3. 参与开源项目

祝你学习愉快！有问题随时问。
