# skill-summarize-to-notebook

当用户提到 **总结并生成笔记** 等字眼时，把总结好的内容通过 MCP 工具 `notebook`（note-book 工具集）提交为一篇笔记，放进 **综合技术笔记** 笔记本。

## 安装

```bash
npx skills add jcleng/skill-summarize-to-notebook -y -g
```

- `-g`：安装到全局（用户级）技能目录。
- `-y`：跳过确认提示（适合 CI / 非交互场景）。

仅安装到当前项目（不加 `-g`）：

```bash
npx skills add jcleng/skill-summarize-to-notebook -y
```

## 更新

按 **skill 名称** 更新（`update` 子命令不支持 `owner/repo` 形式）：

```bash
npx skills update summarize-to-notebook -g -y
```

## 内容

- 触发词：总结并生成笔记 / 总结成笔记 / 整理成笔记 / 生成笔记
- 用 `note_book_create_memo` 提交笔记，正文为 Markdown 结构化总结
- 目标笔记本「综合技术笔记」，按名称定位，缺失时才新建
- 笔记标题自动概括主题，提交后仅简短反馈，不复述全文

## 规范

遵循 [Agent Skills](https://agentskills.io) 规范，根目录 `SKILL.md` 含 `name` 与 `description` 前置字段，可被 `skills` CLI（`vercel-labs/agent-skills`）自动发现。

## License

MIT
