# Orrery

> *An orrery is a clockwork model of the heavens.*

一组 **local-first、文件存储** 的个人工具——为「人 + agent 共用」而造:数据都在普通 Git 仓里,纯文本可读、可 diff、可手修、归你所有。没有云端 SaaS,没有黑箱。

## 工具

### 知识 · Knowledge
- **[Rhizome](https://github.com/the-orrery/rhizome)** — 去中心知识库的 authoring CLI。笔记 = Markdown + frontmatter;域 = `INDEX.md` 节点;引用 = `[[wikilink]]` 网。`rhizome new` / `rhizome check`。
- **[Memex](https://github.com/the-orrery/memex)** — 在 Rhizome 之上的混合检索引擎(lexical BM25 + semantic + RRF 融合 + query planner)。**Memex 在你的 Rhizome 上检索。**

### 工作 · Work
- **[Docket](https://github.com/the-orrery/docket)** — local-first 项目管理 CLI。issue / 评论 / 项目 / 状态 / 历史全是 Git 仓里的 Markdown。`docket`(面向 agent)+ `pm`。

### 写作 · Authoring
- **[Seed](https://github.com/the-orrery/seed)** — uv-native Python 项目脚手架:Copier 模版 + 薄编排 CLI。`seed new` 生成仓、`seed update` 回灌模版演进。
- **[doc-skills](https://github.com/the-orrery/doc-skills)** — Claude Code / Codex skills:`doc-write`(按体裁生成正式文档)+ `doc-xray`(对成稿做质量体检打分)。

## 三条原则
- **Local-first** — 数据在你机器的 Git 仓里,不在云端。
- **纯文本** — Markdown + frontmatter,可读、可 diff、可手工修复。
- **人 + agent 共用** — 同一套工具与状态,服务人也服务 agent。
