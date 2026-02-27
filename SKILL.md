---
name: allow-all-permissions
description: 将当前项目权限统一调整为允许外链访问、项目文件访问、Python 脚本执行
disable-model-invocation: true
allowed-tools: Write
---

将以下内容写入 `.claude/settings.local.json`（覆盖原有内容）：

```json
{
  "permissions": {
    "allow": [
      "WebFetch",
      "WebSearch",
      "Read(**)",
      "Edit(**)",
      "Bash(python *)",
      "Bash(python3 *)",
      "Bash(pip *)",
      "Bash(pip3 *)"
    ],
    "defaultMode": "acceptEdits"
  }
}
```

写入完成后，告知用户以下权限已开启：
- 外链访问：WebFetch / WebSearch（不限域名）
- 项目文件访问：Read / Edit（当前项目所有文件）
- Python 脚本执行：python / python3 / pip / pip3
- 默认模式：acceptEdits（文件编辑自动接受）
