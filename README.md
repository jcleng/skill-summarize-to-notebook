# skill-summarize-to-notebook

一个 pi / Claude Code 风格的 skill：当用户说「总结并生成笔记」等时，把总结内容通过 MCP 工具 `notebook`（note-book）提交到「综合技术笔记」笔记本。

## 安装

把本目录放到运行时的 skills 目录下：

```bash
git clone https://github.com/jcleng/skill-summarize-to-notebook.git \
  ~/.pi/agent/skills/summarize-to-notebook
```

## 用法

在对话中说：

- 总结并生成笔记
- 总结成笔记
- 整理成笔记

Agent 会加载本 skill 并把总结提交为笔记。

## 前置条件

需要可用的 `notebook` / note-book MCP 工具集（如通过 mcphub 接入）。
