# claude-code-plugin

Claude Code 自定义 Skill 插件集合。

## 安装

### 方式 1：npx 一键安装（推荐）

```bash
npx skills add nannianz/claude-code-plugin
```

更多选项：
```bash
# 查看仓库中有哪些 skills
npx skills add nannianz/claude-code-plugin --list

# 安装到全局（所有项目可用）
npx skills add nannianz/claude-code-plugin -g

# 指定只安装到 Claude Code
npx skills add nannianz/claude-code-plugin -a claude-code
```

### 方式 2：手动安装

**Linux/Mac：**
```bash
mkdir -p ~/.claude/skills/ga
curl -s https://raw.githubusercontent.com/nannianz/claude-code-plugin/master/.claude/skills/ga/SKILL.md > ~/.claude/skills/ga/SKILL.md
```

**Windows PowerShell：**
```powershell
mkdir "$env:USERPROFILE\.claude\skills\ga" -Force
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/nannianz/claude-code-plugin/master/.claude/skills/ga/SKILL.md" -OutFile "$env:USERPROFILE\.claude\skills\ga\SKILL.md"
```

### 方式 3：复制到项目本地

将 `.claude/skills/ga/SKILL.md` 复制到你项目的 `.claude/skills/ga/` 目录下。

## 使用

| 命令 | 作用 | 等效 Git |
|------|------|----------|
| `/ga` | 暂存所有变更 | `git add .` |
| `/ga c 提交信息` | 暂存并提交 | `git add . && git commit -m "提交信息"` |
| `/ga r` | 撤销上次提交（保留更改） | `git reset --soft HEAD~1` |

## 技能列表

| 技能 | 说明 |
|------|------|
| ga | Git 快捷操作 - 暂存 / 提交 / 撤销提交 |
