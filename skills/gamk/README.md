# Gamk

Git 快捷操作 - 暂存 / 提交 / 撤销提交。

## Install

```bash
# 1. 添加 marketplace 源（首次需要）
/plugin marketplace add nannianz/skills

# 2. 安装到当前项目
/plugin install gamk --scope project

# 3. 激活
/reload-plugins
```

## Uninstall

```bash
/plugin uninstall gamk
```

## Usage

| 命令 | 作用 | 等效 Git |
|------|------|----------|
| `/gamk` | 暂存所有变更 | `git add .` |
| `/gamk c 提交信息` | 暂存并提交 | `git add . && git commit -m "提交信息"` |
| `/gamk r` | 撤销上次提交（保留更改） | `git reset --soft HEAD~1` |

> **注意：** 安装后需要重启 Claude Code 才能生效。
