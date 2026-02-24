# 练习 4：日常更新流程

## 目标
掌握日常开发中的代码更新流程

## 场景

假设你每天都要更新代码，这是最常用的工作流程。

## 每日工作流程

### 早上开始工作前

```bash
# 1. 进入项目目录
cd my-first-project

# 2. 拉取最新代码（如果有团队成员也在更新）
git pull
```

### 工作中：修改代码

```bash
# 修改 main.py，添加新功能
# 比如添加一个计算函数
```

### 完成一个小功能后

```bash
# 1. 查看改了什么
git status
git diff

# 2. 添加修改
git add .

# 3. 提交（写清楚做了什么）
git commit -m "feat: 添加计算函数"

# 4. 推送到 GitHub
git push
```

## 任务：模拟一天的工作

### 上午任务：添加一个加法函数

1. 修改 `main.py`，添加：

```python
def add(a, b):
    """加法函数"""
    return a + b

def main():
    print(say_hello("世界"))
    print(f"1 + 2 = {add(1, 2)}")

if __name__ == "__main__":
    main()
```

2. 提交并推送：
```bash
git add .
git commit -m "feat: 添加加法函数"
git push
```

### 下午任务：添加一个减法函数

1. 继续修改 `main.py`：

```python
def add(a, b):
    """加法函数"""
    return a + b

def subtract(a, b):
    """减法函数"""
    return a - b

def main():
    print(say_hello("世界"))
    print(f"1 + 2 = {add(1, 2)}")
    print(f"5 - 3 = {subtract(5, 3)}")

if __name__ == "__main__":
    main()
```

2. 提交并推送：
```bash
git add .
git commit -m "feat: 添加减法函数"
git push
```

## 提交信息模板

| 类型 | 格式 | 示例 |
|------|------|------|
| 新功能 | `feat: 描述` | `feat: 添加用户登录` |
| 修复bug | `fix: 描述` | `fix: 修复登录失败问题` |
| 文档 | `docs: 描述` | `docs: 更新安装说明` |
| 重构 | `refactor: 描述` | `refactor: 优化查询性能` |

## 好习惯

1. **频繁提交** - 每完成一个小功能就提交
2. **写清楚说明** - 让别人（和未来的自己）知道改了什么
3. **先拉后推** - 推送前先 `git pull`
4. **一个提交一个功能** - 不要把多个功能混在一起提交

## 完成标志

- [ ] 完成了上午任务（加法函数）
- [ ] 完成了下午任务（减法函数）
- [ ] GitHub 上能看到 2 个新提交
- [ ] 提交信息写得清晰

## 检查你的提交历史

```bash
git log --oneline
```

应该看到类似：
```
abc1234 feat: 添加减法函数
def5678 feat: 添加加法函数
...
```

## 完成后

在下面打勾确认：
- [ ] 我已完成练习 4
- 我现在明白了日常更新的流程是：_______________________
