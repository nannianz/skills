# Skills 发布、下载、更新指南

## 目录结构

```
claude-code-plugin/
├── .claude-plugin/
│   └── marketplace.json   # Marketplace 入口配置
├── README.md              # 项目首页，Skills 列表
├── summary.md             # 本文档
└── skills/
    ├── ga/                # npx 安装方式
    │   ├── SKILL.md
    │   └── README.md
    └── gamk/              # Marketplace 安装方式
        ├── .claude-plugin/
        │   └── plugin.json
        ├── commands/
        │   └── gamk.md    # 用户可调用的 /gamk 命令
        └── README.md
```

## 发布流程

### 1. 创建 Skill

在 `skills/` 下新建目录，放入 `SKILL.md` 文件：

```bash
mkdir -p skills/my-skill
npx skills init my-skill
```

`SKILL.md` 必须包含 `name` 和 `description` 字段：

```yaml
---
name: my-skill
description: 技能描述
user-invocable: true
allowed-tools:
  - Bash
---
```

### 2. 更新首页 README

在 `README.md` 的 Skills 表格中添加新条目。

### 3. 提交并推送

```bash
git add -A
git commit -m "feat: add my-skill"
git push origin master
```

## 下载安装

所有方式均为**项目级安装**（仅当前项目可用），需在目标项目目录下运行。

### Gamk（Marketplace）

```bash
# 1. 添加 marketplace 源（首次需要）
/plugin marketplace add nannianz/skills

# 2. 安装到当前项目
/plugin install gamk --scope project

# 3. 激活
/reload-plugins
```

卸载：

```bash
/plugin uninstall gamk
```

### Ga（npx）

```bash
# 安装
npx skills add nannianz/skills --path skills/ga

# 更新
npx skills update ga

# 卸载
npx skills remove ga

# 查看仓库中有哪些 Skills
npx skills add nannianz/skills --list
```

## 更新

```bash
# 更新指定 Skill
npx skills update ga

# 更新所有已安装的 Skills
npx skills update

# 非交互式（自动检测范围）
npx skills update -y
```

> **注意：** 更新后需要重启 Claude Code 才能生效。
