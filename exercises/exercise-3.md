# 练习 3：分支操作

## 目标
学会创建、切换、合并分支

## 背景

分支让你可以在不影响主分支的情况下开发新功能。

## 任务步骤

### 步骤 1：进入你的项目目录

```bash
cd my-first-project
```

### 步骤 2：查看当前分支

```bash
git branch
```

你应该看到 `* main`，表示当前在 main 分支

### 步骤 3：创建并切换到新分支

```bash
git checkout -b feature-hello
```

这会创建一个名为 `feature-hello` 的新分支并切换过去

### 步骤 4：在新分支上修改文件

修改 `main.py`：

```python
def say_hello(name):
    return f"你好, {name}！"

def main():
    print(say_hello("世界"))

if __name__ == "__main__":
    main()
```

### 步骤 5：提交更改

```bash
git add main.py
git commit -m "feat: 添加 say_hello 函数"
```

### 步骤 6：切换回 main 分支

```bash
git checkout main
```

观察：`main.py` 又变回了原来的内容！

### 步骤 7：合并分支

```bash
git merge feature-hello
```

现在 main 分支也有了新功能！

### 步骤 8：删除已合并的分支

```bash
git branch -d feature-hello
```

### 步骤 9：推送到 GitHub

```bash
git push origin main
```

## 分支操作速查

| 命令 | 作用 |
|------|------|
| `git branch` | 查看所有分支 |
| `git branch 分支名` | 创建分支 |
| `git checkout 分支名` | 切换分支 |
| `git checkout -b 分支名` | 创建并切换 |
| `git merge 分支名` | 合并分支到当前分支 |
| `git branch -d 分支名` | 删除分支 |

## 完成标志

- [ ] 成功创建了新分支
- [ ] 在新分支上做了修改
- [ ] 成功合并到 main 分支
- [ ] 推送到 GitHub

## 完成后

在下面打勾确认：
- [ ] 我已完成练习 3
- 我学到了：_______________________
