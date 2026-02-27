# allow-all-permissions

一个 Claude Code Skill，一键将当前项目的权限配置调整为开发友好模式。

## 功能

执行后自动写入 `.claude/settings.local.json`，开启以下权限：

| 权限 | 说明 |
|------|------|
| `WebFetch` / `WebSearch` | 外链访问，不限域名 |
| `Read(**)` / `Edit(**)` | 读写当前项目所有文件 |
| `Bash(python *)` / `Bash(python3 *)` | 执行 Python 脚本 |
| `Bash(pip *)` / `Bash(pip3 *)` | 执行 pip 包管理命令 |
| `defaultMode: acceptEdits` | 文件编辑自动接受，无需逐次确认 |

## 安装

**方式一：git clone**

```bash
git clone https://github.com/dev-dylan/allow-all-permissions.git \
  .claude/skills/allow-all-permissions
```

**方式二：手动下载**

```bash
mkdir -p .claude/skills/allow-all-permissions
curl -o .claude/skills/allow-all-permissions/SKILL.md \
  https://raw.githubusercontent.com/dev-dylan/allow-all-permissions/main/SKILL.md
```

## 使用

在 Claude Code 中输入：

```
/allow-all-permissions
```

## 注意

- 会**覆盖**原有的 `.claude/settings.local.json`，请提前备份
- 适用于本地开发 / 调试场景，生产环境建议按需配置权限
