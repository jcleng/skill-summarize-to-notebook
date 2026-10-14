# 项目说明：skill-summarize-to-notebook

> 本文件汇总 `skill-summarize-to-notebook` 项目的内容、结构与使用方式，供后续维护与复用参考。

---

## 一、项目概述

- **仓库**：`jcleng/skill-summarize-to-notebook`（GitHub 公开仓库）
- **用途**：当用户提到「总结并生成笔记」等字眼时，把总结内容提交为笔记。
- **规范**：遵循 [Agent Skills](https://agentskills.io) 规范，可被 `skills` CLI（`vercel-labs/agent-skills`）自动发现与安装。

---

## 二、目录结构

```
skill-summarize-to-notebook/
├── SKILL.md      # 技能定义文件（含 YAML 前置字段 name/description），核心内容
├── README.md     # 安装与使用说明
├── LICENSE       # MIT 许可证
├── .gitignore
└── agents.md     # 本文件，项目汇总说明
```

---

## 三、SKILL.md 关键字段

```yaml
---
name: summarize-to-notebook
description: Use when 用户要求"总结并生成笔记"、"总结成笔记"、"整理成笔记"、"生成笔记"等，需要把当前对话或指定内容的总结提交为笔记时。
---
```

---

## 四、依赖的 MCP 工具（note-book）

| 工具名称 | 用途 |
| --- | --- |
| `mcp__mcphub__note_book_create_memo` | 提交笔记（主要动作） |
| `mcp__mcphub__note_book_find_notebooks` | 按名称查找目标笔记本 |
| `mcp__mcphub__note_book_create_notebook` | 笔记本不存在时新建 |

> 目标笔记本为「综合技术笔记」，当前 notebookId 为 `nb_1a063d49424244608137c870062109a0`；id 失效时按名称重新定位。

---

## 五、安装方式

```bash
# 全局安装（用户级，推荐搭配 -y 非交互）
npx skills add jcleng/skill-summarize-to-notebook -y -g

# 仅安装到当前项目（不加 -g）
npx skills add jcleng/skill-summarize-to-notebook -y
```

---

## 六、维护说明

- 修改 `SKILL.md` 内容后，提交并 `git push` 到 `main` 分支即可更新。
- 已安装用户更新：**按 skill 名称**执行 `npx skills update summarize-to-notebook -g -y`（`update` 子命令不支持 `owner/repo` 形式）。
- 发布前请确认 `SKILL.md` 的 `name` 与 `description` 字段完整且为合法 YAML。
