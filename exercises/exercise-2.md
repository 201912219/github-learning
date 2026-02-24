# 练习 2：上传自己的项目

## 目标
学会如何将本地项目上传到 GitHub

## 准备工作

在本地创建一个测试项目：

```bash
# 创建项目目录
mkdir my-first-project
cd my-first-project

# 创建几个文件
echo "# 我的第一个项目" > README.md
echo "print('Hello GitHub!')" > main.py
echo "__pycache__/" > .gitignore
```

## 任务步骤

### 步骤 1：初始化 Git 仓库

```bash
git init
```

### 步骤 2：查看状态

```bash
git status
```

观察：你应该看到 3 个未跟踪的文件

### 步骤 3：添加文件到暂存区

```bash
git add .
```

### 步骤 4：提交

```bash
git commit -m "Initial commit: 项目初始化"
```

### 步骤 5：在 GitHub 创建仓库

方式一（网页）：
1. 打开 https://github.com/new
2. 仓库名填：`my-first-project`
3. **不要勾选** "Add a README file"
4. 点击 "Create repository"

方式二（命令行）：
```bash
gh repo create my-first-project --public
```

### 步骤 6：连接远程仓库并推送

```bash
git remote add origin https://github.com/201912219/my-first-project.git
git branch -M main
git push -u origin main
```

## 完成标志

- [ ] 本地项目已创建
- [ ] GitHub 上能看到新仓库
- [ ] 能看到 README.md 和 main.py 文件

## 常见错误

| 错误 | 解决方法 |
|------|----------|
| `fatal: not a git repository` | 先运行 `git init` |
| `fatal: remote origin already exists` | 运行 `git remote remove origin` 再重试 |
| 推送失败 | 检查 `gh auth status` |

## 完成后

在下面打勾确认：
- [ ] 我已完成练习 2
- 我的 GitHub 仓库地址是：_______________________
